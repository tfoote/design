---
layout: unit
title: ROS Higher-Level Concepts
abstract:
 What is ROS?
reference_id: ros-higher-level-concepts
tags: [ros, concepts]
skills: []
topics: []
---


# {{ page.title }}

The core ROS platform attempts to be as architecture-agnostic as possible. It provides several different modes of communicating data ([topics](http://wiki.ros.org/Topics), [services](http://wiki.ros.org/Services), [Parameter Server](http://wiki.ros.org/Parameter)), but it doesn't prescribe how they're used or how they are [named](http://wiki.ros.org/Names). This approach allows ROS to be easily integrated with a variety of architectures, but higher-level concepts are necessary for building larger systems on top of ROS.

There are several stacks, such as [common](http://wiki.ros.org/common), [common_msgs](http://wiki.ros.org/common_msgs), and [geometry](http://wiki.ros.org/geomentry), that provide these higher-level concepts for use with ROS and are described below.

##Coordinate Frames/Transforms

The [tf](http://wiki.ros.org/tf) package provides a distributed, ROS-based framework for calculating the positions of multiple coordinate frames over time.

##Actions/Tasks

The [actionlib](http://wiki.ros.org/actionlib) package defines a common, [topic](http://wiki.ros.org/Topics)-based interface for preemptible tasks in ROS.

##Message Ontology

The [common_msgs](http://wiki.ros.org/ROS/common_msgs) stack provide a base message ontology for robotic systems. It defines several classes of messages, including:
* [actionlib_msgs](http://wiki.ros.org/ROS/actionlib_msgs): messages for representing [actions](http://wiki.ros.org/ROS/Higher-Level%20Concepts#actions).  
* [diagnostic_msgs](http://wiki.ros.org/diagnostic_msgs): messages for sending diagnostic data.  
* [geometry_msgs](http://wiki.ros.org/geometry_msgs): messages for representing common geometric primitives.  
* [nav_msgs](http://wiki.ros.org/nav_msgs): messages for navigation.  
* [sensor_msgs](http://wiki.ros.org/sensor_msgs): messages for representing sensor data.  

##Plugins

[pluginlib](http://wiki.ros.org/pluginlib) provides a library for dynamically loading libraries in C++ code.

##Filters

The [filters](http://wiki.ros.org/filters) package provides a C++ library for processing data using a sequence of filters.

##Robot Model

The [urdf](http://wiki.ros.org/urdf) package defines an XML format for representing a robot model and provides a C++ parser.

##Cheat Sheet

Check out the [ROScheatsheet.pdf](http://pr.willowgarage.com/downloads/ROScheatsheet.pdf|ROScheatsheet.pdf).



