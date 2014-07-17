---
layout: tutorial
title: Embedding Pictures
abstract:
 Write abstract here
reference_id: embedding-pictures
tags: [tags, go, here]
skills: [skills, go, here]
required_skills: []
---

# {{ page.title }}

In order to embed pictures in a page for this site, you need to do a few things:

1. **Save** the image **IN THE COURSE DIRECTORY** and give it a descriptive name (again, use a dash - to represent spaces)
2. Find path to image within the "design" repository
3. Plug that path into the html code below.

For example, if I want to embed an image of a turtlebot on this site, I need to to the following:

1. Save the turtlebot-pic.png file in the appropriate folder. In this case, I saved it in the how-to-contribute directory because that is the course directory where this tutorial belongs.

2. Next, I need to find the path to this image file. In this case, it's design/courses/how-to-contribute/turtlebot-pic.png. 

3. Now, I copy that directory and insert it in the second line of code below:

{% highlight html %}
<p align="center">
  <img src="{{site.baseurl}}/courses/how-to-contribute/turtlebot-pic.png"/>
</p>
{% endhighlight %}

All this will get you this image!

<p align="center">
  <img src="{{site.baseurl}}/courses/how-to-contribute/turtlebot-pic.png"/>
</p>

For different alignment condigurations, you can replace "center" with "right" or "left"
