---
layout: default
title: About
---

# About this Site

----

This project began with the general mission of making it easier to teach Robotics Operating System (ROS) using Willow Garage’s[LINK] TurtleBot[LINK].  We started brainstorming ways to facilitate and consolidate collaboration within the already-existent ROS education community.  This led us to develop a website using a Git web repository as the host, a collaboration platform many open source projects already use.  Once we got the ball rolling, we realized that the collaborative nature of the project enabled it to extend beyond just teaching ROS with TurtleBot; if anyone can upload material related to TurtleBot, they can also contribute any material relevant to teaching and learning robotics.  Therefore, the general purpose of this site is providing free robotics education resources relevant to any and all areas of robotics.

Since no two teachers have the same teaching style, we needed to prepare for material coming into the site in all manner of shapes and sizes.  We decided to address this issue by establishing a standard format to organize material on the site which we hope will provide common grounds upon which collaboration can occur.  This format enables incoming material to be categorized, which will in turn reduce redundancy and will enable a means for users to easily navigate through material on the site.

The fundamental organization of the site is a hierarchical structure not too different from a class syllabus: course, unit, and topics (lessons, tutorials, challenges).  Here’s example of what a course might look like using this format:

**Course**

* Unit
   * Lessons
   * Tutorial
   * Lesson
   * Tutorial
   * Challenge
* Unit
   * Lesson
   * Lesson
   * Tutorial
   * Challenge
   * Challenge
* Unit
   * Tutorial
   * Challenge

In addition, we have written guidelines for how to define these categories:

----

**Course**: This is basically a syllabus and contains the units that will be covered in the course.  Metadata in the header for the course includes: title, abstract, tags , prerequisites (by course or by topic), skills, requirements, and version/compatibility tags.


**Unit**: These are the various topics covered in the course.  We can think of the units as individual folders that contain all the material; any lesson, tutorial or challenge will belong to at least one unit.


**Lesson**: Lessons will be where the educators present all the information and building blocks they are giving to the students - in slides, videos, notes, diagrams… etc. A topic can have multiple lessons, maybe to give students stopping points to apply the information they are receiving.


**Tutorial**: This is where students can be walked-through an application of what they are learning.  If it’s a new programming concept for instance, it can be a series of questions that get the student to walk through an example of the material.  (The idea here is really similar to what we think of online tutorials - these are step by step instructions and examples).


**Challenge**:  This is the fun part.  Here is where educators can post material that get the student to apply and expand on the concepts covered.  Here is where you would find homework problems, problem sets, projects, open ended questions… etc.  The challenges will be labelled as either “recommended” or “extended.”

----

All elements (courses, units, lessons, tutorials, and challenges) will be indexed and will reference the material they belong with.  In addition, units and the elements they contain can also be cross-referenced if material is applicable to more than one course and/or unit.  But we’ll talk about indexing and referencing later on.

In this manner, contributors to the site can decide which category/categories to place their material in.  The courses will be composed of units, which in turn contain lessons, tutorials, and challenges.  Each element (courses, units, lessons, tutorials, and challenges) will have a header containing a reference ID and meta-data that both gives users a sense of the content and acts as a means of searching for course material in the repository. Units and the content in the units can be cross-referenced between units as well as courses so that course material can be recycled if appropriate. 

