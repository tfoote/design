---
layout: unit
title: Introduction
abstract:
 Learn about this site and how to use it
reference_id: introduction
tags: [introduction, about]
skills: [about]
topics: [course-elements]
---



* This will become a table of contents (this text will be scraped).
{:toc}

# {{ page.title }}

##About this Site

Hello! Welcome to [NAME OF SITE]!

The purpose of this site is to provide an online space where educators can collaborate on free material for teaching robotics (sort of like a course/lesson/activity database).  Material can range anywhere from individual activities and informational content to entire courses.  We want teaching and learning robotics to be accessible to all!

This project began with the general goal of making it easier to teach Robotics Operating System (ROS) using Willow Garage’s[LINK] TurtleBot[LINK].  We started brainstorming ways to facilitate and consolidate collaboration within the already-existent ROS education community.  This led us to develop a website using a Git web repository as the host, a collaboration platform many open source projects already use.  Once we got the ball rolling, we realized that the collaborative nature of the project enabled it to extend beyond just teaching ROS with TurtleBot; if anyone can upload material related to TurtleBot, they can also contribute any material relevant to teaching and learning robotics.  Therefore, the general purpose of this site is providing free robotics education resources relevant to any and all areas of robotics.


![TurtleBot](http://cdn2.ubergizmo.com/wp-content/uploads/2011/04/TurtleBot-Front-640w.png)

<p align="center">
  <img src="http://cdn2.ubergizmo.com/wp-content/uploads/2011/04/TurtleBot-Front-640w.png"/>
</p>


<p align="center">
  <img src="{{site.baseurl}}/img/fork.png"/>
</p>



{% highlight javascript %}
if (isAwesome){
  return true
}
{% endhighlight %}

Since no two teachers have the same teaching style, we needed to prepare for material coming into the site in all manner of shapes and sizes.  We decided to address this issue by establishing a standard format to organize material on the site which we hope will provide common grounds upon which collaboration can occur.  This format enables incoming material to be categorized, which will in turn reduce redundancy and will enable a means for users to easily navigate through material on the site.  More information on how to use this format can be found in the course “Making a Course.”  However, the fundamental organization of the site can be outlined with the following example of the hierarchical structure used:

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

In this manner, contributors to the site can decide which category/categories to place their material in.  The courses will be composed of units, which in turn contain lessons, tutorials, and challenges.  Each element (courses, units, lessons, tutorials, and challenges) will have a header containing a reference ID and meta-data that both gives users a sense of the content and acts as a means of searching for course material in the repository. Units and the content in the units can be cross-referenced between units as well as courses so that course material can be recycled if appropriate. 

With all of this, the hope is to collaboratively create online robotics courses that educators can both edit and pull from in order to use with their own students.

