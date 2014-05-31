---
layout: course
title: TurtleBot Tutorial
abstract:
  Learn how to set up, teleoperate, and calibrate a TurtleBot
reference_id: turtlebot-tutorial
tags: [TurtleBot]
skills: [bringup, teleoperation, calibration]
units: [Bringup, Teleoperation, Calibration]
---



* This will become a table of contents (this text will be scraped).
{:toc}

# {{ page.title }}

## Getting Started

In this course, you will learn how to bringup the TurtleBot, various modes of teleoperation, and calibration. Follow through these three units 


Description: How to start the TurtleBot software.

Tutorial Level: BEGINNER

Next Tutorial: TurtleBot Care and Feeding 

Turtlebot Bringup

2.1 Basics

Close the lid of your TurtleBot laptop, place it on the TurtleBot and connect the USB cables. Press the power button for your mobile base. If you have a Create, the power button is on the top left, hidden behind the edge of the lowest deck and a green light will turn on. If you have a Kobuki, the power button is a switch on the left hand side and it will chirp and flash led's excitedly as soon as you turn it on.

Firstly ssh into your TurtleBot computer from your workstation computer (need more help about ssh) .

Bringup Modes

There are three different ways of bringing up the turtlebot:

    Minimal : this starts up turtlebot with your garden variety single master ros environment in which all processes can be started/stopped via roslaunchers.

    App Manager : can do everything minimal does, but also offers the option of managing your programs as robot apps via the app manager.

    Android Enabled : starts private/public masters and allows the app manager to be controlled by a remote android device via the public master. 

It might be benficial if teaching with turtlebots to progressively move through the three modes. The exact instructions then differ depending on whether you have a prepared usb derived release, from debs, or from source.

2.2 Deb Bringup Instructions

> source /opt/ros/hydro/setup.bash
# Without the app manager/android capabilities
> roslaunch turtlebot_bringup minimal.launch
# Launching with the app manager
> roslaunch turtlebot_bringup minimal_with_appmanager.launch
# For dual master app manager/android connectivity
> rocon_launch turtlebot_bringup bringup.concert

 The tutorials that follow for the turtlebot generally assume you have started turtlebot as always in the simplest configuration via the minimal launcher.

Bringup Troubleshooting

If your turtlebot came with a netbook or a USB drive installer, the turtlebot software may already be running on the turtlebot netbook. You can check by running rosnode list on the netbook. If you get a list of nodes (instead of an error) ROS is already running. Note that ROS will only start if the netbook is connected to the network - if ROS is not running check this first.

Otherwise, you may see something like this: 

> rosnode list
ERROR: Unable to communicate with master!

f this is the case manually launch as explained above (from the netbook). Be sure to preset the appropriate environment variables if you have a (create base link)

3 .Workstation Bringup

3.1 Preparation

This assumes you have finished the workstation install and also the network configuration that enables turtlebot and workstation to communicate.

3.2 Dashboard

/!\ To see what is happening on the TurtleBot please keep the turtlebot_dashboard up as much as possible when running the robot.

If you have a Turtlebot 2 based on the Kobuki base you should launch the Kobuki dashboard. 

> rqt -s kobuki_dashboard

Otherwise, if you have a Turtlebot based on the iRobot Create base, the following environment variables should be set.

> export TURTLEBOT_BASE=create
> export TURTLEBOT_STACKS=circles
> export TURTLEBOT_3D_SENSOR=kinect

And the following command to launch the Create dashboard.

> roslaunch turtlebot_dashboard turtlebot_dashboard.launch

You should see the TurtleBot dashboard appear. 



Type `echo Hello world!`, Done.
