---
layout: tutorial
reference_id: interactive-makers-teleop
title: Interactive Makers Teleop
abstract:
  How to use rviz interactive markers for controlling the TurtleBot
tags: [TurtleBot, teleoperation interactive makers]

provided skills: [interactive makers, teleoperation]
required_skills: [install, network configuration, bringup]
---

# {{ page.title }}

##Introduction

TurtleBot interactive markers are an alternative way to control your TurtleBot. They allow you to teleoperate the robot from rviz.

##Running the Marker Server

Do these steps on the PC, not the TurtleBot laptop for best performance. First, make sure you have the package installed:

	sudo apt-get install ros-hydro-turtlebot-interactive-markers

Then launch the turtlebot_marker_server, which will host an interactive_markers server.

	roslaunch turtlebot_interactive_markers interactive_markers.launch

##Running rviz

Next, start up a copy of rviz displaying the marker topics. On the PC, type:

	roslaunch turtlebot_rviz_launchers view_robot.launch

##Interact!

Check the "Interactive Makers" display component and select the "Interact" tool in the tool palette on the top of the screen (shown below) to bring up the interactive markers for the turtlebot.

<p align="center">
	<img src="{{site.baseurl}}/courses/getting-started-turtle/interact.png"/>
</p>

You can now drag the red arrows to drive the TurtleBot forward and backward, and the blue ring to rotate the TurtleBot. You can also drag the blue ring to both rotate and translate the TurtleBot at the same time.

###**Video**

<div style="text-align: left"><iframe width="480" height="360" src="//www.youtube.com/embed/MQ6fNrehMNI" frameborder="0" allowfullscreen></iframe></div>

