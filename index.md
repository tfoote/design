---
layout: default
title: ROS Courses
---

# ROS Courses

This site is repository of courses for teaching ROS and general robotics. 


# Courses

Here is a list of courses available so far. 


{% for p in site.pages %}
    {% if p.url contains 'articles/' %}
----

#### [{{ p.title }}]({{ site.baseurl }}{{ p.url }})

{{ p.abstract }}
    {% endif %}
{% endfor %}
----



# TurtleBot Courses

This is an example of filtering for a set of tagged courses. 

{% for p in site.pages %}
    {% if p.tags contains 'TurtleBot' %}
----

#### [{{ p.title }}]({{ site.baseurl }}{{ p.url }})

{{ p.abstract }}
    {% endif %}
{% endfor %}
----

