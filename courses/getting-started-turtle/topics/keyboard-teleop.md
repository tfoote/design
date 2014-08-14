---
layout: tutorial
reference_id: keyboard-teleop
title: Keyboard Teleop
abstract:
  Keyboard teleoperation of a turtlebot
tags: [TurtleBot, teleoperation, keyboard]
provided skills: [teleoperation]
required_skills: [install, network configuration, bringup]
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

# {{ page.title }}

*This assumes that you have a TurtleBot which has already been brought up in this tutorial. See TurtleBot Bringup if you have not brought up the TurtleBot.*

##On the TurtleBot.

Now ssh (ssh help) into the turtlebot and start the keyboard teleop nodes

	roslaunch turtlebot_teleop keyboard_teleop.launch

Key presses in this terminal can now be used to control the robot.

