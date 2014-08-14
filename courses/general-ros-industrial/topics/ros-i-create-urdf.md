---
layout: tutorial
title: Create a URDF for an Industrial Robot
abstract:
 Walks through the steps and conventions for creating a Unified Robot Description Format (URDF) for an industrial robot
reference_id: ros-i-create-urdf
tags: [urdf, industrial, manipulator]
skills: [skills, go, here]
required_skills: []
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

##Table of Contents

In this tutorial we will learn to create URDFs for typical industrial manipulators.  The URDF XML format is very expressive and allows many different ways of defining the same geometry.  We will discuss specific conventions that are meant to:

* simplify the URDF
* create consistencies between robots across vendors
* enable software functionality that relies on these assumptions
* allow the URDF to be included as part of a larger robot work cell (as this is often the case)



##Generate STLs from 3D CAD Models

The arm path planning methods that are used by ROS-Industrial are collision aware.  In order to take advantage of this capability 3D information about the robot geometry is required.

##Prepare CAD Models
Link coordinate systems must be created before exporting STL files from 3D CAD models.  The coordinate system present in vendor supplied CAD models are rarely in the desired position.  The desired coordinate systems should adhere to the following:

* coincident with the joint nearest to the base of the robot.  This placement results in a simple joint transform.
* if possible, oriented such that when the robot is in the zero position, the X-axis points forward and the Z-axis points up.
* NOTE: If using the **URDF Exporter** plugin for SolidWorks, the coordinate frames and axes of rotation need to be added under the top-level assembly. Tutorials for utilizing the URDF exporter can be found here: **sw_urdf_exporter/Tutorials URDF Tutorials**.
  * all link coordinate frames should be identically-oriented with the X-axis pointing forward and the Z-axis pointing up.
  * if using the URDF Plugin for !SolidWorks, after completing the URDF Export Configuration (`File->Export as URDF`), double check that the **Origin_global** feature that was created by the URDF exporter is oriented correctly (X-axis forward, Z-axis up) .  If it is not correctly oriented, manually correct it by editing the feature, then rerun the URDF Configuration tool to regenerate the URDF file.


##Create STLs

The URDF allows for two types of 3D models, visual and collision models. 

####**Visual STLs**

A visual model is used for display purposes only.  These models can be highly detailed because they are not used for collision checking.  Visual models can be exported directly from a CAD package.  Make certain to export binary STLs.

####**Collision STLs**

Collision models should not be highly detailed.  The more detailed these models, the longer it takes to perform collision checks.  Collision models should be simple, yet encompass the entire link geometry.  It is suggested the convex hulls be created from visual STLs, using a 3D mesh tool such as !MeshLab (`Filters->Remeshing, Simplification and Reconstruction->Convex Hull`).

* NOTE: This tutorial was prepared with !MeshLab v1.3.0. The convex hulls created from the original STL in a program such as !MeshLab will occassionally result in the surface normals being incorrectly oriented (pointing into the model rather than out of the model).  To correct this in MeshLab, simply invert the surface normals (`Filters->Normals, Curvatures and Orientation->Invert Faces Orientation`). In case of inconsistent normal orientation (mesh shows transparent areas), use `Filters->Normals, Curvatures and Orientation->Re-Orient all faces coherently`.

##Create a URDF for your robot

As you step through the following to create a URDF for your robot, adhere to the following conventions:

* the joint origin is specified by a full transform (see [[urdf/XML/joint]]). However, in order to take advantage of some libraries, the joint orientation (roll, pitch, yaw) is limited to a single rotation.  That is '''two of the three orientation angles must remain zero.'''  Because of this, link and/or model transforms may become more complex.
* the joint origins should be oriented with the Z-axis up, and the X-axis forward, when the robot is in the zero position.  Assuming this convention was followed when making the STL coordinate frames, this should be easily achieved.  NOTE: This convention is not a requirement.

##Create a XACRO Macro for your robot

While it is possible to write an explicit URDF for a particular industrial arm, a more general XACRO approach is taken.  A XACRO is a type of URDF macro that can be used to generate a URDF.  We take this approach because industrial manipulators are often combined with custom end-effectors, requiring a custom URDF.  By writing a XACRO that can generate the manipulator portion of the URDF, we provide flexible and extensible library that can be used to generate any custom robot. 

For an example, see:

https://raw.github.com/ros-industrial/motoman/hydro-devel/motoman_sia10d_support/urdf/sia10d_macro.xacro sia10d_macro.xacro

(check this link)

For more information on creating an XACRO, see the [[xacro/Tutorials XACRO tutorials]].

##Additional/Standard Frames

By convention and in order to match common industrial robot frames, several additional frames should be added to the XACRO

**base_link**  
The *base_link* shall be positioned in the logical base position (oriented by convention, z-axis up, x-axis forward).  This frame name is by ROS convention.  Typically this frame is the first frame of the robot tied to the first link.

**tool0**  
The *tool0* frame shall match exactly the *tool0* defined by the robot controller.  
The transform between the last robot link and *tool0* can be defined in any way, as long as the transform is fixed between the two. 

{% raw %}
	<link name="${prefix}tool0" />

	<joint name="${prefix}link_6-tool0" type="fixed">
	  <parent link="${prefix}link_6" />
	  <child link="${prefix}tool0" />
	  <origin xyz="0.0 0 0.0" rpy="0.0 0.0 0.0" />
	</joint>
{% endraw %}

**base**  
The *base* frame shall match exactly the *base* defined by the robot controller.  The transform between *base* and *base_link* can be defined in any way, as long as the transform is fixed between the two (i.e. not across a movable joint). The preference is for the base to be defined relative to *base_link*

{% raw %}
	<link name="${prefix}base" />

	<joint name="${prefix}base_link-base" type="fixed">
	  <parent link="${prefix}base_link" />
	  <child link="${prefix}base" />
	  <origin xyz="0.0 0 0.0" rpy="0.0 0.0 0.0" />
	</joint>
{% endraw %}

##Generate a URDF for your robot

In order to generate a URDF for your robot, another XACRO must be written to call the XACRO created in the previous step. See https://raw.github.com/ros-industrial/motoman/hydro-devel/motoman_sia10d_support/urdf/sia10d.xacro sia10d.xacro for an example.

To generate the actual URDF and check the result:

{% raw %}
	rosrun xacro xacro.py <<xacro_file>> > <<urdf_file>>
	rosrun urdf_parser check_urdf <<urdf_file>>
{% endraw %}

If successful, the commands above will generate a URDF of your industrial manipulator. As an example, see the https://raw.github.com/ros-industrial/motoman/hydro-devel/motoman_sia10d_support/urdf/sia10d.urdf sia10d.urdf


##Generate a URDF for your robot and end-effector (Optional)

This section is meant to demonstrate why a XACRO is used instead of directly writing the URDF.  In the case where an end-effector is added to the robot, the XACRO comes in handy.

See the following robot + end-effector http://code.google.com/p/swri-ros-pkg/source/browse/trunk/swri_demos/longhorn/cfg/longhorn.xacro example


##Verify your URDF

It is very important that the information within the URDF is accurate.  Specifically, the joint limits and orientations will used in the following steps and must be correct.  To visualize your robot run the following: 

	roslaunch urdf_tutorial display.launch model:=<<urdf_file>> gui:=True

Use the GUI sliders to verify the joint orientation (i.e. plus/minus moves the actual robot).  Also verify that the joint limits match.
