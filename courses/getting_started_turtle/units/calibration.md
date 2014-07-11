---
layout: unit
reference_id: calibration
title: Calibration
abstract:
  Calibration of a turtlebot
tags: [TurtleBot, calibration]

topics: []

---

# {{ page.title }}

* This will become a table of contents (this text will be scraped).
{:toc}

###TurtleBot Odometry and Gyro Calibration

This will show you how to calibrate or test the calibration of a TurtleBot which is highly recommended when running any navigation based application. *This is only necessary if you have a Create base. The Kobuki comes with a factory calibrated gyro.*

##1. Setup

>Note: Determine which gyro your TurtleBot is using, TurtleBots made by different manufacturers have gyros with different measurement rates. You will need to look at the small chip on the right side of the turtlebot power/sensor board and find its part number (example). Some common ones are:
> 
>	Chip		Setting
>	ADXRS613	150
>	ADXRS652	250
> 
>This link may help: [http://www.alldatasheet.com/view.jsp?Searchword=ADXRS6](http://www.alldatasheet.com/view.jsp?Searchword=ADXRS6)
> 
>Set the gyro_measurement_range value before you run calibration by using dynamic_reconfigure or editing the configuration file as explained in the results section below.
> 

First position TurtleBot at the center of a long straight wall (at least 2 meters long), facing towards the wall, at about 30 cm away from the wall.

**calibration1.JPG calibration2.JPG**

##2. Execution

This assumes you have already started the robot

Now ssh (ssh help) into the TurtleBot and run the calibration routine:

	roslaunch turtlebot_calibration calibrate.launch

Turtlebot will perform a number of calibration spins. When it finishes, you'll see a print on the screen like this:

	[INFO] [WallTime: 1299286750.821002] Multiply the 'turtlebot_node/gyro_scale_correction' parameter with 1.002262
	[INFO] [WallTime: 1299286750.822427] Multiply the 'turtlebot_node/odom_angular_scale_correction' parameter with 1.000263

* If the TurtleBot does not successfully return to facing the wall before executing the next rotation the data will be incorrect. This can be caused by too big of an error in the existing parameters. If it under rotates, increase the odom parameter and retry. If it over rotates, lower the odom_parameter and retry. 

##3. Results

The calibration routine will output 2 numbers. The correction for the gyro and the correction for the odometry. The values are factors to multiply with the current parameters to get the best results (see also this QA and this QA).

After running the calibration set the parameters to the old value multiplied by the correction.

The two parameters are:

* turtlebot_node/gyro_scale_correction
* turtlebot_node/odom_angular_scale_correction 

For a single run you can set the parameters using dynamic_reconfigure:

	rosrun dynamic_reconfigure reconfigure_gui 

Then select the turtlebot_node and set the parameters. 
