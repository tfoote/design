---
layout: default
title: ROS Courses
---

# Hello, welcome to ROS Courses!

----

The purpose of this site is to provide a repository for educational material concerning ROS and general robotics (sort of like a course/lesson/activity database).  It is our goal is to collaboratively create online robotics courses that educators can both edit and pull from in order to use with their own students.  Contributors can provide material ranging anywhere from individual activities and informational content to entire courses.  We want teaching and learning robotics to be accessible to all!

# Courses

Here is a list of courses available so far. 


{% for p in site.pages %}
    {% if p.layout == 'course' %}
----

#### [{{ p.title }}]({{ site.baseurl }}{{ p.url }})

{{ p.abstract }}
    {% endif %}
{% endfor %}
----

testing this

For TurtleBot Courses see: [here](turtlebot)
