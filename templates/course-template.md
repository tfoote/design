---
layout: course
title: Course Template
abstract:
 Write abstract here
reference_id: course-template
tags: [tags, go, here]
skills: [skills, go, here]
units: [list of units, go, here, as md files, this-is-an-example]
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

{% for c in page.contributors %}
{% assign exists = 0 %}
{% if c.name != 'Name' %}
{{ c.name }}
{% assign exists = 1 %}
{% endif %}
{% if c.email != '' || c.email != 'Email' %}
{{ c.email }}
{% assign exists = 1 %}
{% endif %}
{% if c.corresponding_author and exists == 1 %}(This person is a corresponding author){% endif %}
{% endfor %}

(HERE YOU WRITE A DESCRIPTION OF THE COURSE - TELL WHAT THE COURSE IS FOR, SUMMARIZE WHAT IS COVERED, PROVIDE ANY RELEVANT INFORMATION... ETC)

(OPTIONAL: INCLUDE BULLET POINTS OUTLINING TOP-LEVEL HEADERS)

* USE THIS SIZE FOR TOP-LEVEL HEADERS
* TOP-LEVEL 2
* TOP-LEVEL 3
* Tutorial Description

## USE THIS SIZE FOR TOP-LEVEL HEADERS

### NEXT HEADERS

#### AND SO ON

## TOP-LEVEL 2

## TOP-LEVEL 3

##Course Description

A course is basically a syllabus and contains the units that will be covered in the course.  Metadata in the header for the course includes: title, abstract, tags , prerequisites (by course or by topic), skills, requirements, and version/compatibility tags.

(BELOW THIS TEXT WILL APPEAR A LIST WITH THE CONTENTS OF THE COURSE IN SYLLABUS FORM AS LINKS)
