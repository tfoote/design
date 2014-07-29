---
layout: unit
title: ROS Client Libraries
abstract:
 What is ROS?
reference_id: ros-client-libraries
tags: [ros, client-libraries]
skills: []
topics: []
---

# {{ page.title }}

##Overview

A ROS client library is a collection of code that eases the job of the ROS programmer. It takes many of the [[ROS/Overview ROS concepts]] and makes them accessible via code.  In general, these libraries let you write ROS [[Nodes nodes]], publish and subscribe to [[Topics topics]], write and call [Services](wiki.ros.org/services), and use the [[Parameter Server]]. Such a library can be implemented in any programming language, though the current focus is on providing robust C++ and Python support.

##Main client libraries

 * [[roscpp]] : roscpp is a C++ client library for ROS. It is the most widely used ROS client library and is designed to be the high performance library for ROS.
 * [[rospy]]: rospy is the pure Python client library for ROS and is designed to provide the advantages of an object-oriented scripting language to ROS. The design of rospy favors implementation speed (i.e. developer time) over runtime performance so that algorithms can be quickly prototyped and tested within ROS. It is also ideal for non-critical-path code, such as configuration and initialization code. Many of the ROS tools are written in rospy to take advantage of the type introspection capabilities. The ROS Master, roslaunch, and other ros tools are developed in rospy, so Python is a core dependency of ROS.
 * [[roslisp]]: roslisp is a client library for LISP and is currently being used for the development of planning libraries. It supports both standalone node creation and interactive use in a running ROS system.

## Experimental client libraries 

 * [[rosjava]]: rosjava is an implementation of ROS in pure-Java with Android support.
 * [[roslua]]: roslua is a client library for Lua, which is a light-weight yet powerful, embeddable scripting language. The client library is currently in an experimental and active development stage.
 * [[roscs]]: roscs is a client library for Mono/.NET. It can be used by any Mono/.NET language, including C#, Iron Python, Iron Ruby, etc. The ROS build system will create .DLL and .so files for each package written in roscs.
 * [[roseus]]: roseus is a client library for [[euslisp EusLisp]] language.
 * [PhaROS](http://car.mines-douai.fr/category/pharos/) is an client library under MIT Licence for the [[http://pharo-project.org/ Pharo]] free Smalltalk language.
 * [[rosR]]: rosR is an ros language extension for the statistical programming language [[http://www.r-project.org/ R]].

See also: [[Implementing Client Libraries]]


