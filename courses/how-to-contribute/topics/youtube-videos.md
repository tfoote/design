---
layout: tutorial
title: Youtube Videos
abstract:
 How to add youtube videos to pages.
reference_id: youtube-videos
tags: []
skills: []
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


Youtube videos can't be embedded directly in Markdown.  However, you can embed a YouTube video using HTML (described in the following steps).  In addition, we will also cover how to use HTML or Markdown to add an image with a link to the video.

##**Embedding YouTube - HTML**

####**1. Set up the video alignment**

In your markdown file, copy and paste the following HTML div code required to align the YouTube video iframe. 

{% highlight html %}
	<div style="text-align: center"> </div>
{% endhighlight %}

This div contains the CSS code that will tell the viewer's browser to center the video.  If you wish to align the video to the right or left, replace `center` with either `right` or `left`.

####**2. Obtain Video Address**

In your web browser, navigate to the YouTube video you wish to embed in your markdown file. Click "Share" on the YouTube video and then click "Embed."

<p align="center">
  <img src="{{site.baseurl}}/courses/how-to-contribute/share-YT-video.png"/>
</p>

####**3. Select iframe code**

Select the iframe code in the text box and press "Ctrl-C" to copy it to the clipboard. Note that before you select this code, you can modify the size of the video you wish to display on your web page.


####**4. Paste iframe code in Markdown file**

Return to the markdown file and click the empty space before the "</div>" code. Then press "Ctrl-V" to paste the embed code. Your code should now resemble the following:

{% highlight html %}
	<div style="text-align: center"><iframe width="420" height="315" src="[link to your YouTube video]" frameborder="0" allowfullscreen></iframe></div>
{% endhighlight %}

For example, if I want to embed a video titled "Introducing TurtleBot," this is what my code will look like:

{% highlight html %}
	<div style="text-align: center"><iframe width="560" height="315" src="//www.youtube.com/embed/MOEjL8JDvd0" frameborder="0" allowfullscreen></iframe></div>
{% endhighlight %}

This video will now appear like this on my web page:

<div style="text-align: center"><iframe width="560" height="315" src="//www.youtube.com/embed/MOEjL8JDvd0" frameborder="0" allowfullscreen></iframe></div>



##**Add Image with Link to Video**

You can also embedd an image with a link to the YouTube video. Here are the steps to doing this:

####**1. Obtain YouTube Video ID**

In your web browser, navigate to the YouTube video you wish to embed in your markdown file. The video ID is located at the end of the video's address:

<p align="center">
  <img src="{{site.baseurl}}/courses/how-to-contribute/video-ID.png"/>
</p>

In this case, the ID is **MOEjL8JDvd0**.

####**2. Copy and paste either of the following codes into your markdown file.**

In html:

{% highlight html %}
	<a href="http://www.youtube.com/watch?feature=player_embedded&v=YOUTUBE_VIDEO_ID_HERE
	" target="_blank"><img src="http://img.youtube.com/vi/YOUTUBE_VIDEO_ID_HERE/0.jpg" 
	alt="IMAGE ALT TEXT HERE" width="240" height="180" border="10" /></a>
{% endhighlight %}

Or in pure Markdown, but losing the image sizing and border:

{% raw %}
	[![IMAGE ALT TEXT HERE](http://img.youtube.com/vi/YOUTUBE_VIDEO_ID_HERE/0.jpg)](http://www.youtube.com/watch?v=YOUTUBE_VIDEO_ID_HERE)
{% endraw %}

####**3. Insert YouTube Video ID**

In the code you just pasted, Replace `YOUTUBE_VIDEO_ID_HERE` with the ID obtained in step 1.  Note that the html code has two instances of `YOUTUBE_VIDEO_ID_HERE`. For example, for the same "Introducing TurtleBot" video above (ID = MOEjL8JDvd0), this is what the code should now look like:

{% raw %}
	<a href="http://www.youtube.com/watch?feature=player_embedded&v=MOEjL8JDvd0
	" target="_blank"><img src="http://img.youtube.com/vi/MOEjL8JDvd0/0.jpg" 
	alt="Introducing TurtleBot" width="240" height="180" border="10" align="center" /></a>

	Or

	[![IMAGE ALT TEXT HERE](http://img.youtube.com/vi/MOEjL8JDvd0/0.jpg)](http://www.youtube.com/watch?v=MOEjL8JDvd0)
{% endraw %}

Note that in the html method, you can specify the dimensions of the image. You may also include image alternative text in both methods (replace `IMAGE ALT TEXT HERE`). 

Here's the result from the first method (html):

<a href="http://www.youtube.com/watch?feature=player_embedded&v=MOEjL8JDvd0
" target="_blank"><img src="http://img.youtube.com/vi/MOEjL8JDvd0/0.jpg" 
alt="Introducing TurtleBot" width="240" height="180" border="10" align="center" /></a>

Here's the result from the second method (pure Markdown):

[![IMAGE ALT TEXT HERE](http://img.youtube.com/vi/MOEjL8JDvd0/0.jpg)](http://www.youtube.com/watch?v=MOEjL8JDvd0)
