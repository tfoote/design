---
layout: tutorial
title: Create a Joint Position Streaming Interface utilizing TCP Socket Libraries
abstract:
 Walks through the steps and conventions for creating a Unified Robot Description Format (URDF) for an industrial robot
reference_id: ros-i-create-joint-position
skills: [skills, go, here]
required_skills: []
---

# {{ page.title }}

##Table of Contents

* controller code
  - joint position streaming interface
    - joint commands (motion)
    - joint feedback (joint states)
- ROS code


##Controller Code

###Joint Position Streaming Interface

The controller acts as a server for all connections.  All types are 32 bit types (floats and integers, byte order is "Little Endian" (see [[http://code.google.com/p/swri-ros-pkg/issues/detail?id=8&can=1|bug write up]] for more information).

There are two connections, one for joint commands and one of joint feedback.  Here are the details:

####**Joint Commands (Motion)**

> Socket type:  TCP
> 
> Socket port:  11000
> 
> JointMessages (constant values shown in **bold**)
> 
> Client request:  LENGTH(bytes-not including length specifier), **10** (MSG_ID – JOINT MESSAGE), **2** (COMM_TYPE - REQUEST), **0** (REPLY_TYPE – N/A), SEQ_NUMBER(see special values below), JOINT_DATA[10] (in rads (floats))
> 
> Server reply:  LENGTH(bytes), **10**, **3**(COMM_TYPE – RESPONSE), REPLY (1 = SUCCESS, 2 = FAILURE), UNUSED, UNUSED[10]

SEQ_NUMBER – The sequence number is the number assigned by ROS to each of the points (i.e. this is always 0 or positive).  A value of -1 indicates the end of a trajectory, a value of -2 indicates a stop (in both cases the controller stops, **joint data is not valid for these special types**)

**Pseudo-Code**

The client will send joint points one at a time.  When it receives the server response it sends the next point.  This allows the server (controller) to determine the rate at which points are sent and how much buffering is performed.  In practice this results in slower motion than desired, but the point spacing can be adjusted in ROS to account for this. 

Pseudo-code for the controller is shown below (code for specific controllers might look very different given the differences between controllers).

{% raw %}
	while(true)
	  if(tcp.isConnected())
	  {
	    tcp.receive(jointPositionMsg)
	    jointPosition = decode(jointPositionMsg)
	    MoveJ(jointPosition)
	    jointResponseMsg = encode(jointResponse)
	    tcp.send(jointResponseMsg)
	  }
	  else
	  {
	    tcp.connect()
	  }
	}
{% endraw %}

####**Joint Feedback (Joint States)**

> Socket type: TCP
> 
> Socket port: 11002
> 
> JointMessages (constant values shown in **bold**)
> 
> Server streams: LENGTH(bytes), **10**, **1**(COMM_TYPE – TOPIC), **0** (REPLY_TYPE – N/A), UNUSED, JOINT_DATA[10] (in rads (floats))

The Joint States just stream rate is determined by the controller, 10-50Hz is an appropriate range.

**Pseudo-Code**

Pseudo-code for the controller is shown below (code for specific controllers might look very different given the differences between controllers).

{% raw %}
	while(true)
	  if(tcp.isConnected())
	  {
	    jointCurrentMsg = encode(jointCurrent)
	    tcp.send(jointCurrentMsg)
	    sleep(rate)
	  }
	  else
	  {
	    tcp.connect()
	  }
	}
{% endraw %}

##ROS Code

The ROS Code to support this interface can be found in the dx100 package.  This code can be reused for different controllers as it was developed genercially (**TODO: Move this generic code to a package under the ROS-Industrial stack**).


