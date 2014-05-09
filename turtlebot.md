---
layout: default
title: TurtleBot Courses
---

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

