---
layout: course
title: General ROS Industrial
abstract:
  Learn about ROS-Industrial general capabilities, libraries, messages, etc
reference_id: general-ros-industrial
categories: [ROS-Industrial, ROS]
tags: [industrial, general, ros, tutorials]
skills: [general ros-i]
units: [ros-i-training, ros-i-general, industrial-calibration-toolbox, industrial-moveit, industrial-trajectory-filters]
#if page is finished, change under_construction to “False”
under_construction: True
#please provide contributor(s)/author(s) and specify if person is a point of contact (default is "True")
contributors:
  - name: NAME
    email: EMAIL
    corresponding_author: True
  - name: NAME
    email: EMAIL
    corresponding_author: True
---

----


{% include under_construction.html email='mliebmanpelaez@gmail.com' %}

== General ROS-Industrial ==
The following sections cover ROS-Industrial general capabilities, libraries, messages, etc.

=== Training ===
The training class curriculum is recommended for new users to both ROS and ROS-Industrial.

 1. [[http://aeswiki.datasys.swri.edu/rositraining|Basic Developers' Training Class Curriculum]] - ROS-I Consortium class for C++ programmers starting with basic Linux and concluding with a vision-enabled pick and place project. Includes slides, step-by-step exercises, and test code. Visit [[https://github.com/ros-industrial/industrial_training|GitHub]] for the code.

=== General ===
These tutorials cover assorted topics on ROS-Industrial.  The tutorials do not have a specific order and are meant to be followed on a topic by topic basis.

<<FullSearchWithDescriptionsCS(title:"Industrial/Tutorials/" IntermediateCategory)>>

=== Industrial Calibration Toolbox ===
<<Include(industrial_extrinsic_cal/Tutorials)>>

=== Industrial MoveIt ===
The [[industrial_moveit|Industrial MoveIt]] software package contains industrial add-ons to the [[http://moveit.ros.org/|MoveIt]] motion planning library.

<<Include(industrial_moveit/Tutorials)>>

=== Industrial Trajectory Filters ===
The [[industrial_trajectory_filters|Industrial Trajectory Filters]] package contains filters for the <<MsgLink(trajectory_msgs/JointTrajectory)>> messages.

<<Include(industrial_trajectory_filters/Tutorials)>>

(HERE YOU WRITE A DESCRIPTION OF THE COURSE - TELL WHAT THE COURSE IS FOR, SUMMARIZE WHAT IS COVERED, PROVIDE ANY RELEVANT INFORMATION... ETC)

(OPTIONAL: INCLUDE BULLET POINTS OUTLINING TOP-LEVEL HEADERS)

* USE THIS SIZE FOR TOP-LEVEL HEADERS
* TOP-LEVEL 2
* TOP-LEVEL 3
* Tutorial Description

## USE THIS SIZE FOR TOP-LEVEL HEADERS

### NEXT HEADERS

#### AND SO ON

## TOP-LEVEL 2

## TOP-LEVEL 3

##Course Description

A course is basically a syllabus and contains the units that will be covered in the course.  Metadata in the header for the course includes: title, abstract, tags , prerequisites (by course or by topic), skills, requirements, and version/compatibility tags.

(BELOW THIS TEXT WILL APPEAR A LIST WITH THE CONTENTS OF THE COURSE IN SYLLABUS FORM AS LINKS)
