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

The core ROS platform attempts to be as architecture-agnostic as possible. It provides several different modes of communicating data ([[Topics topics]], [[Services services]], [[Parameter Server]]), but it doesn't prescribe how they're used or how they are [[Names named]]. This approach allows ROS to be easily integrated with a variety of architectures, but higher-level concepts are necessary for building larger systems on top of ROS.

There are several stacks, such as [[common]], [[common_msgs]], and [[geometry]], that provide these higher-level concepts for use with ROS and are described below.

##Coordinate Frames/Transforms

The [[tf]] package provides a distributed, ROS-based framework for calculating the positions of multiple coordinate frames over time.

##Actions/Tasks

The [[actionlib]] package defines a common, [[Topics|topic]]-based interface for preemptible tasks in ROS.

##Message Ontology

The [[common_msgs]] stack provide a base message ontology for robotic systems. It defines several classes of messages, including:
 * [[actionlib_msgs]]: messages for representing [[#actions|actions]].  
 * [[diagnostic_msgs]]: messages for sending diagnostic data.  
 * [[geometry_msgs]]: messages for representing common geometric primitives.  
 * [[nav_msgs]]: messages for navigation.  
 * [[sensor_msgs]]: messages for representing sensor data.  

##Plugins

[[pluginlib]] provides a library for dynamically loading libraries in C++ code.

##Filters

The [[filters]] package provides a C++ library for processing data using a sequence of filters.

##Robot Model

The [[urdf]] package defines an XML format for representing a robot model and provides a C++ parser.

##Cheat Sheet

Check out the [ROScheatsheet.pdf](http://pr.willowgarage.com/downloads/ROScheatsheet.pdf|ROScheatsheet.pdf).



