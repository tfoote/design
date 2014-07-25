---
layout: unit
title: ROS Concepts
abstract:
 What is ROS?
reference_id: ros-concepts
tags: [ros, introduction, concepts]
skills: []
topics: []
---


# {{ page.title }}

ROS has three levels of concepts: the Filesystem level, the Computation Graph level, and the Community level.  These levels and concepts are summarized below and later sections go into each of these in greater detail.

In addition to the three levels of concepts, ROS also defines two types of [[Names names]] -- Package Resource Names and Graph Resource Names -- which are discussed below. 

_**Note: since ROS Groovy these wiki pages describe concepts as they relate to the new catkin buildsystem. For older versions of ROS or when using the rosbuild buildsystem, see: [[rosbuild/ROS/Concepts]]**_

##ROS Filesystem Level

The filesystem level concepts mainly cover ROS resources that you encounter on disk, such as:

 * **[[Packages]]**: Packages are the main unit for organizing software in ROS. A package may contain ROS runtime processes (''nodes''), a ROS-dependent library, datasets, configuration files, or anything else that is usefully organized together. Packages are the most atomic build item and release item in ROS. Meaning that the most granular thing you can build and release is a package.
 * **[[Metapackages]]**: Metapackages are specialized Packages which only serve to represent a group of related other packages. Most commonly metapackages are used as a backwards compatible place holder for converted [[rosbuild]] [Stacks](rosbuild/ROS/Concepts#Stacks).
 * **[[catkin/package.xml|Package Manifests]]**: Manifests (`package.xml`) provide metadata about a package, including its name, version, description, license information, dependencies, and other meta information like exported packages. The `package.xml` package manifest is defined in [REP-0127](http://www.ros.org/reps/rep-0127.html).
 * **Repositories**: A collection of packages which share a common VCS system. Packages which share a VCS share the same version and can be released together using the catkin release automation tool [[bloom]]. Often these repositories will map to converted [[rosbuild]] [[rosbuild/ROS/Concepts#Stacks|Stacks]]. Repositories can also contain only one package.
 * **[[msg|Message (msg) types]]**: Message descriptions, stored in `my_package/msg/MyMessageType.msg`, define the data structures for [[Messages|messages]] sent in ROS.
 * **[[srv|Service (srv) types]]**: Service descriptions, stored in `my_package/srv/MyServiceType.srv`, define the request and response data structures for [[Services|services]] in ROS.

##ROS Computation Graph Level

The *Computation Graph* is the peer-to-peer network of ROS processes that are processing data together. The basic Computation Graph concepts of ROS are *nodes*, *Master*, *Parameter Server*, *messages*, *services*, *topics*, and *bags*, all of which provide data to the Graph in different ways.

These concepts are implemented in the [[ros_comm]] repository.

 * **[[Nodes]]**: Nodes are processes that perform computation.  ROS is designed to be modular at a fine-grained scale; a robot control system usually comprises many nodes.  For example, one node controls a laser range-finder, one node controls the wheel motors, one node performs localization, one node performs path planning, one Node provides a graphical view of the system, and so on.  A ROS node is written with the use of a ROS [[Client Libraries client library]], such as [[roscpp]] or [[rospy]].
 * **[[Master]]**: The ROS Master provides name registration and lookup to the rest of the Computation Graph. Without the Master, nodes would not be able to find each other, exchange messages, or invoke services. 
 * **[[Parameter Server]]**: The Parameter Server allows data to be stored by key in a central location. It is currently part of the Master.
 * **[[Messages]]**: Nodes communicate with each other by passing [[Messages messages]].  A message is simply a data structure, comprising typed fields.  Standard primitive types (integer, floating point, boolean, etc.) are supported, as are arrays of primitive types.  Messages can include arbitrarily nested structures and arrays (much like C structs).
 * **[[Topics]]**: Messages are routed via a transport system with publish / subscribe semantics.  A node sends out a message by ''publishing'' it to a given [[Topics topic]]. The topic is a [[Names name]] that is used to identify the content of the message.  A node that is interested in a certain kind of data will ''subscribe'' to the appropriate topic.  There may be multiple concurrent publishers and subscribers for a single topic, and a single node may publish and/or subscribe to multiple topics.  In general, publishers and subscribers are not aware of each others' existence.  The idea is to decouple the production of information from its consumption. Logically, one can think of a topic as a strongly typed message bus.  Each bus has a name, and anyone can connect to the bus to send or receive messages as long as they are the right type.
 * **[[Services]]**: The publish / subscribe model is a very flexible communication paradigm, but its many-to-many, one-way transport is not appropriate for request / reply interactions, which are often required in a distributed system.  Request / reply is done via [[Services services]], which are defined by a pair of message structures: one for the request and one for the reply. A providing node offers a service under a [[Names|name]] and a client uses the service by sending the request message and awaiting the reply.  ROS client libraries generally present this interaction to the programmer as if it were a remote procedure call.
 * **[[Bags]]**: Bags are a format for saving and playing back ROS message data. Bags are an important mechanism for storing data, such as sensor data, that can be difficult to collect but is necessary for developing and testing algorithms.

The ROS [[Master]] acts as a nameservice in the ROS Computation Graph. It stores [[Topics topics]] and [[Services services]] registration information for ROS [[Nodes nodes]]. Nodes communicate with the Master to report their registration information. As these nodes communicate with the Master, they can receive information about other registered nodes and make connections as appropriate. The Master will also make callbacks to these nodes when this registration information changes, which allows nodes to dynamically create connections as new nodes are run.

Nodes connect to other nodes directly; the Master only provides lookup information, much like a DNS server. Nodes that subscribe to a topic will request connections from nodes that publish that topic, and will establish that connection over an agreed upon connection protocol. The most common protocol used in a ROS is called [[ROS/TCPROS|TCPROS]], which uses standard TCP/IP sockets. 

This architecture allows for decoupled operation, where the [[Names names]] are the primary means by which larger and more complex systems can be built. Names have a very important role in ROS: nodes, topics, services, and parameters all have names. Every ROS [[Client Libraries client library]] supports [[Remapping Arguments command-line remapping of names]], which means a compiled program can be reconfigured at runtime to operate in a different Computation Graph topology. 

For example, to control a Hokuyo laser range-finder, we can start the [[hokuyo_node]] driver, which talks to the laser and publishes <<MsgLink(sensor_msgs/LaserScan)>> messages on the `scan` topic.  To process that data, we might write a node using [[laser_filters]] that subscribes to messages on the `scan` topic. After subscription, our filter would automatically start receiving messages from the laser.

Note how the two sides are decoupled.  All the `hokuyo_node` node does is publish scans, without knowledge of whether anyone is subscribed.  All the filter does is subscribe to scans, without knowledge of whether anyone is publishing them.  The two nodes can be started, killed, and restarted, in any order, without inducing any error conditions.

Later we might add another laser to our robot, so we need to reconfigure our system. All we need to do is *remap* the names that are used. When we start our first `hokuyo_node`, we could tell it instead to remap `scan` to `base_scan`, and do the same with our filter node. Now, both of these nodes will communicate using the `base_scan` topic instead and not hear messages on the `scan` topic. Then we can just start another `hokuyo_node` for the new laser range finder.

http://ros.org/images/wiki/ROS_basic_concepts.png [[attachment:ROS_basic_concepts.dia]]

##ROS Community Level

The ROS Community Level concepts are ROS resources that enable separate communities to exchange software and knowledge. These resources include:
 * **[[Distributions]]**: ROS Distributions are collections of versioned [[Stacks|stacks]] that you can install. Distributions play a similar role to Linux distributions: they make it easier to install a collection of software, and they also maintain consistent versions across a set of software.
 * **[[Repositories]]**: ROS relies on a federated network of code repositories, where different institutions can develop and release their own robot software components. 
 * **[[Documentation|The ROS Wiki]]**: The ROS community Wiki is the main forum for documenting information about ROS. Anyone can sign up for an account and contribute their own documentation, provide corrections or updates, write tutorials, and more.
 * **Bug Ticket System**: Please see [[Tickets]] for information about file tickets.
 * **[[Mailing Lists]]**: The [[Mailing Lists|ros-users mailing list]] is the primary communication channel about new updates to ROS, as well as a forum to ask questions about ROS software.
 * **[Answers](http://answers.ros.org|ROS Answers)**: A Q&A site for answering your ROS-related questions.
 * **[Blog](http://www.ros.org/news)**: The [[http://www.ros.org/news|ros.org Blog]] provides regular updates, including photos and videos.

