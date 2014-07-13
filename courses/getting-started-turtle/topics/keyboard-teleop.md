---
layout: tutorial
reference_id: keyboard-teleop
title: Keyboard Teleop
abstract:
  Keyboard teleoperation of a turtlebot
tags: [TurtleBot, teleoperation, keyboard]
provided skills: [teleoperation]
required_skills: [install, network configuration, bringup]

---

----

*This assumes that you have a TurtleBot which has already been brought up in this tutorial. See TurtleBot Bringup if you have not brought up the TurtleBot.*

##On the TurtleBot.

Now ssh (ssh help) into the turtlebot and start the keyboard teleop nodes

	roslaunch turtlebot_teleop keyboard_teleop.launch

Key presses in this terminal can now be used to control the robot.

