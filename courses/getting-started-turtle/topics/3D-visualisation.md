---
layout: tutorial
title: 3D Visualisation
reference_id: 3D-visualisation
abstract:
  Visualising 3d and camera data from the kinect/asus.
tags: [TurtleBot, image data, kinect, 3D, camera]

provided skills: [camera data]
required_skills: [install, network configuration]
---

# {{ page.title }}

##1. Starting the 3D sensor

Plug in your sensor to the netbook.

*Be sure that you do not connect it on a usb 3.0 port (these are usually, but not always, coloured if they are of the 3.0 kind) since these devices still only work in usb 2.0.*

Assuming you have already launched the turtlebot software (refer to the turtlebot bringup tutorial), you can proceed to launch the 3D sensor functionality on top:

	> roslaunch turtlebot_bringup 3dsensor.launch

By default, this will launch the 3d sensor with all the processing modules ON. You can turn these off by sending the appropriate arguments to the launch command (look inside 3dsensor.launch for more information).

The turtlebot apps themselves do this - they only enable exactly what they need to minimise the amount of processing that is done for their task.

##2. Start Rviz

On your workstation computer start rviz already configured to visualize the robot and its sensor's output:

	> roslaunch turtlebot_rviz_launchers view_robot.launch

Note that this also lets you various other aspects of the robot as well.

##3. Enable the desired displays

To visualize any display you want, just click on its check button. These are the displayed sensors:

* DepthCloud  
* Registered DepthCloud  
* Image  
* PointCloud  
* Registered PointCloud  

For example, in the following screen capture both LaserScan and Registered DepthCloud are enabled.

<p align="center">
  <img src="{{site.baseurl}}/courses/getting-started-turtle/laserscan.png"/>
</p>

##4. A bit more about 3D data structures

Groovy introduced the depth_image data type that is now used by default in most places. Without processing, the openni nodelet will just produce depth images. This is the raw data structure provided by the openni driver for 3d information. Upon enabling some processing, this can be converted into the more usable PCL format.

RViz now has views for both data types and you'll note the visualisation of both data types is the same - a 3d point cloud drawn by opengl. You can see both plugins when running rviz via view_robot.launch.

**Q) How are depth images and point clouds used in the Turtlebot?**

For low level operations - depth images are used. Since no conversion is done, it's faster. The depthimage_to_laserscan package does this because it needs to be fast to save computation for mapping. For more complicated operations, such as turtlebot_follower it uses the pcl format where it then has access to the host of algorithms in the point cloud library.

The default 3dsensor.launch file configures the 3D sensor to provide you with fully processed 3d data (registrations, point clouds, fake laser scans) for convenience. The turtlebot apps like follower each call 3dsensor.launch and enable only the processing modules they need via clever use of roslaunch args.

