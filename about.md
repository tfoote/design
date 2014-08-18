---
layout: default
title: About
---

# About this Site

----

###**Our Goal**

Enabling collaboration, accessibility, and innovation within the **ROS and Robotics Education Community**.

----

###**Story**

This project began with the general mission of making it easier to teach [Robotics Operating System](http://www.ros.org/) (ROS) using Willow Garage’s [TurtleBot](http://www.turtlebot.com/).  We started brainstorming ways to facilitate and consolidate collaboration within the already-existent ROS education community.  This led us to develop a website using a Git web repository as the host, a collaboration platform many open source projects already use.  Once we got the ball rolling, we realized that the collaborative nature of the project enabled it to extend beyond just teaching ROS with TurtleBot; if anyone can upload material related to TurtleBot, they can also contribute any material relevant to teaching and learning robotics.  Therefore, the general purpose of this site is providing free robotics education resources relevant to any and all areas of robotics.

###**Why GitHub and not Wiki?**

Using GitHub as a host for this site has various advantages. Because the website is hosted in GitHub, the content (transferred from existing ROS Wiki pages and other sources) is easy to deploy and incorporate into courses. In addition, hosting this site on GitHub as opposed to on a Wiki allows for higher levels of quality assurance and less redundancy in the content. Users contribute by forking the repository, adding or editing content, and making a pull request.  All the content on the site is written in Markdown, with the exception of embedding external media which requires the use of HTML. 

###**What the Courses Look Like**

Since no two teachers have the same teaching style, we needed to prepare for material coming into the site in all manner of shapes and sizes.  At the same time, we needed to make sure that the site still enabled teachers to preserve their unique teaching styles.  We decided to address this issue by establishing a standard format to organize material on the site.  We hope this will provide common grounds upon which collaboration can occur while ensuring flexibility in course content and style.  This format enables incoming material to be categorized, which will in turn reduce redundancy and will enable a means for users to easily navigate through material on the site.

The fundamental organization of the site is a hierarchical structure not too different from a class syllabus: course, unit, and topics (lessons, tutorials, challenges).  Here are two examples of what a course might look like using this format:

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

Or

**Course**

* Unit
* Unit
* Unit
   * challenge

In addition, we have written guidelines for how to define these categories:

----

**Course**: This is basically a syllabus and contains the units that will be covered in the course.  Metadata in the header for the course includes: title, abstract, tags , prerequisites (by course or by topic), skills, requirements, and version/compatibility tags.


**Unit**: These are the various topics covered in the course.  We can think of the units as individual folders that contain all the material; any lesson, tutorial or challenge will belong to at least one unit.


**Lesson**: Lessons will be where the educators present all the information and building blocks they are giving to the students - in slides, videos, notes, diagrams… etc. A unit can have multiple lessons, maybe to give students stopping points to apply the information they are receiving.


**Tutorial**: This is where students can be walked-through an application of what they are learning.  If it’s a new programming concept for instance, it can be a series of questions that get the student to walk through an example of the material.  (The idea here is really similar to what we think of online tutorials - these are step by step instructions and examples).


**Challenge**:  This is the fun part.  Here is where educators can post material that get the student to apply and expand on the concepts covered.  Here is where you would find homework problems, problem sets, projects, open ended questions… etc.  The challenges will be labelled as either “recommended” or “extended.”

----

###**Organizing and Searching Through Material on this Site**

All educational material in this site is organized in **courses**. [All courses]({{ site.baseurl }}/all-courses) can be found in the "[All courses]({{ site.baseurl }}/all-courses)" tab in the top menu. In addition, there is also a tab in the top menu where you can find [all courses organized by category]({{ site.baseurl }}/categories). You can also browse through material on the site by its **tags** in the "[Tags]({{ site.baseurl }}/tags)" tab bound in the top menu.

All elements (courses, units, lessons, tutorials, and challenges) will be indexed and will reference the material they belong with.  In addition, units and the elements they contain can also be cross-referenced if material is applicable to more than one course and/or unit. 

Contributors can decide which category/categories to place their material in.  The courses will be composed of units, which in turn contain lessons, tutorials, and challenges.  Each element (courses, units, lessons, tutorials, and challenges) will have a header containing a reference ID and meta-data that both gives users a sense of the content and acts as a means of searching for course material in the repository. Units and the content in the units can be cross-referenced between courses as well as units so that course material can be recycled if appropriate. 

###**Thoughts on Users and Future Work**

There currently exists a lot of educational online material such as the [ROS wiki tutorials](http://wiki.ros.org/ROS/Tutorials), [ROS-Industrial tutorials](http://wiki.ros.org/Industrial/Tutorials) and many other similar resources informing users about ROS and its applications. This site is meant to be a more selective and curated sample of existing online ROS educational material. We hope that this site will initially pick up steam within the ROS education community, mainly with online tutorials and higher-education courses.  Eventually, we would like to see this site extend beyond ROS tutorials and include general robotics educational resources. 

In order to consolidate these online resources, it will require a significant amount of time and energy to tranfer existing content to this site. We have started transfering some content that we think will work well with this site, namely basic ROS and TurtleBot tutorials. The next steps for this site are to get users to contribute and transfer their material to the site.  This will require some means of incentivising users, such as creating a competition or providing recognition for contributions (right now, the closest we have to this is listing authors on the pages they contribute to).
