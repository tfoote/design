---
layout: unit
title: ROS Introduction
abstract:
 What is ROS?
reference_id: ros-introduction
tags: [ros, introduction]
skills: []
topics: []
---

##What is ROS?

ROS is an open-source, meta-operating system for your robot.  It provides the services you would expect from an operating system, including hardware abstraction, low-level device control, implementation of commonly-used functionality, message-passing between processes, and package management.  It also provides tools and libraries for obtaining, building, writing, and running code across multiple computers. ROS is similar in some respects to 'robot frameworks,' such as [Player](http://playerstage.sf.net), [YARP](http://eris.liralab.it/yarp/), [Orcos](http://www.orocos.org/), [CARMEN](http://carmen.sourceforge.net), [Orca](http://orca-robotics.sourceforge.net), [MOOS](http://www.robots.ox.ac.uk/~pnewman/TheMOOS/index.html), and [Microsoft Robotics Studio](http://msdn.microsoft.com/en-us/robotics/default.aspx).

The ROS runtime "graph" is a peer-to-peer network of processes (potentially distributed across machines) that are loosely coupled using the ROS communication infrastructure. ROS implements several different styles of communication, including synchronous RPC-style communication over [services](http://wiki.ros.org/Services), asynchronous streaming of data over [topics](http://wiki.ros.org/Topics), and storage of data on a [Parameter Server](http://wiki.ros.org/Parameter%20Server). These are explained in greater detail in our [Conceptual Overview](http://wiki.ros.org/ROS/Concepts). 

ROS is not a realtime framework, though it is possible to integrate ROS with realtime code. The Willow Garage PR2 robot uses a system called [pr2_etherCAT](http://wiki.ros.org/pr2_etherCAT), which transports ROS messages in and out of a realtime process. ROS also has [seamless integration with the Orocos Real-time Toolkit](http://www.willowgarage.com/blog/2009/06/10/orocos-rtt-and-ros-integrated).

##Goals

A lot of people ask, "How is ROS different from X?" where X is another robotics software platform. It's a difficult question to answer as the goal of ROS is ''not'' to be a framework with the most features.  Instead, the primary goal of ROS is to support code ''reuse'' in robotics research and development. ROS is a distributed framework of processes (aka ''Nodes'') that enables executables to be individually designed and loosely coupled at runtime. These processes can be grouped into ''Packages'' and ''Stacks'', which can be easily shared and distributed. ROS also supports a federated system of code ''Repositories'' that enable collaboration to be distributed as well. This design, from the filesystem level to the community level, enables independent decisions about development and implementation, but all can be brought together with ROS infrastructure tools.

In support of this primary goal of sharing and collaboration, there are several other goals of the ROS framework:

* Thin: ROS is designed to be as thin as possible -- we won't wrap your main() -- so that code written for ROS can be used with other robot software frameworks. A corollary to this is that ROS is easy to integrate with other robot software frameworks: ROS has already been integrated with OpenRAVE, Orocos, and Player.  
* ROS-agnostic libraries: the preferred  development model is to write ROS-agnostic libraries with clean functional interfaces.   
* Language independence: the ROS framework is easy to implement in any modern programming language. We have already implemented it in [Python](http://wiki.ros.org/rospy), [C++](http://wiki.ros.org/roscpp), and [Lisp](http://wiki.ros.org/roslisp), and we have experimental libraries in Java and Lua.  
* Easy testing: ROS has a builtin unit/integration test framework called [rostest](http://wiki.ros.org/rostest) that makes it easy to bring up and tear down test fixtures.  
* Scaling: ROS is appropriate for large runtime systems and for large development processes.  

So, "How is ROS different from X?" It's hard to answer for every X, but first, if you choose to use X, we hope that you can still use many of the libraries distributed with ROS. As for more specifics, this e-mail by Brian Gerkey (of both Player and ROS) to the ros-users mailing list regarding the differences between ROS and Player, including OpenCV integration, provides some comparisons:

{% raw %}
	The answer, as usual, depends.  In particular, it depends on what you're trying to do.  Player is a great fit for simple, non-articulated mobile platforms.  It was designed to provide easy access to sensors and motors on laser-equipped Pioneers.

	ROS, on the other hand, is designed around complex mobile manipulation platforms, with actuated sensing (tilting lasers, pan/tilt sensor heads, sensors attached to arms).  As compared to Player, ROS makes it easier to take advantage of a distributed computing environment, and I would say that the higher-level side of things is more developed in ROS than in Player.  Whereas Player offers more hardware drivers, ROS offers more implementations of algorithms.

	I think that's it's fair to say that ROS is more powerful and flexible than Player, but, as usual, greater power and flexibility come at the cost of greater complexity.  While we're working hard to make ROS easy to use, there is still a significant learning curve.  Of course, familiarly with Player should help in learning to use ROS, as many of the underlying concepts are similar.

	As to your specific question regarding OpenCV integration, I think that you'll find quite a bit more ROS code than Player code that uses OpenCV in interesting ways.   In the future, you should expect to see even more, as there's significant overlap between the ROS and OpenCV development teams.

	I should note that ROS leverages a lot of code from the Player project.  There are ROS nodes that reuse code from many Player drivers, and both Stage and Gazebo are well-supported and widely used in the ROS community.
{% endraw %}

##Operating Systems

ROS currently only runs on Unix-based platforms. Software for ROS is primarily tested on Ubuntu and Mac OS X systems, though the ROS community has been contributing support for Fedora, Gentoo, Arch Linux and other Linux platforms.

While a port to Microsoft Windows for ROS is possible, it has not yet been fully explored. 

##Releases

The core ROS system, along with useful tools and libraries are regularly released as a [ROS Distribution](http://wiki.ros.org/Distributions). This distribution is similar to a Linux distribution and provides a set of compatible software for others to use and build upon. 

##Contributing

As ROS is open source, we hope that you will consider contributing to ROS or libraries that are compatible with ROS. Please see our section on [Contributing](http://wiki.ros.org/Contributing) for more information on how you can participate in the ROS community.



