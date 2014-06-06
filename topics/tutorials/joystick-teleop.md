---
layout: tutorial
reference_id: joystick-teleop
title: Joystick Teleop
abstract:
  Joystick teleoperation of a turtlebot
tags: [TurtleBot, teleoperation, joystick]
provided skills: [teleoperation]
required_skills: [install, network configuration, bringup]

---

# {{ page.title }}

* This will become a table of contents (this text will be scraped).
{:toc}


##Joystick

Several joystick configurations are supported - currently playstation3, xbox360 and logitech's rumblepad2. These example nodes are simple and depending on your joystick you may just need to remap the keys.

##Setting up the Joystick

For the most part, this tutorial assumes you have already got your joystick plugged in and its ready to go. Some more detailed information for specific joysticks: **Playstation 3 Joysticks**

##On the TurtleBot

Now ssh (ssh help) into the TurtleBot and start the joystick and teleop nodes

**Playstation 3**

	roslaunch turtlebot_teleop ps3_teleop.launch

**Xbox360** (use the left stick while keeping the right stick pressed in)

	roslaunch turtlebot_teleop xbox360_teleop.launch

**Logitech joysticks** (general configuration for all logitech joysticks)

	roslaunch turtlebot_teleop logitech.launch

##Unsupported Joystick

If your joystick is not listed above, it is a simple matter remapping the keys. Use the ps3_teleop.launch as a starting point and configure the buttons (working out which button you want for the deadman_axis is the most important) appropriately. Echo the /joy topic to help observe the id's of the various buttons getting pressed.

	<launch>
	   <!--  smooths inputs from cmd_vel_mux/input/teleop_raw to cmd_vel_mux/input/teleop -->
	   <include file="$(find turtlebot_teleop)/launch/includes/velocity_smoother.xml"/>

	   <node pkg="turtlebot_teleop" type="turtlebot_teleop_joy" name="turtlebot_teleop_joystick">
	     <param name="scale_angular" value="1.5"/>
	     <param name="scale_linear" value="0.5"/>
	     <param name="axis_deadman" value="10"/>
	     <param name="axis_linear" value="1"/>
	     <param name="axis_angular" value="0"/>
	     <remap from="turtlebot_teleop_joystick/cmd_vel" to="cmd_vel_mux/input/teleop_raw"/>
	   </node>
	   <node pkg="joy" type="joy_node" name="joystick"/>
	</launch>

Once you've finalised the launcher for your custom joystick, send it to us and we'll integrate it with the official software!

Need More Help?

**Show other Joystick Tutorials**

