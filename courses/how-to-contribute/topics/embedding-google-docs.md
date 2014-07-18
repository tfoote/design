---
layout: tutorial
title: Embedding Google Docs
abstract:
 Learn to embed Google Docs (presentations, spreadsheets, docs... etc)
reference_id: embedding-google-docs
tags: [google docs, embed, markdown, html]
skills: [embed google docs]
required_skills: []
---

# {{ page.title }}

It is fairly simple to embed a Google document in this site. Every Google doc has a "Publish to Web" option that produces an html snippet which can easily interface with any markdown file. In this tutorial, we will go through the steps to embedding a Google doc.

####**1. Set up the Google doc alignment**

In your markdown file, copy and paste the following HTML div code required to align the Google doc iframe. 

{% highlight html %}
	<div style="text-align: center"> </div>
{% endhighlight %}

This div contains the CSS code that will tell the viewer's browser to center the video.  If you wish to align the doc to the right or left, replace `center` with either `right` or `left`.

####**2. Obtain html Snippet**

In your browser, navigate to the Google doc you wish to embed. From the file menu, select **"Publish to Web"**.

<p align="center">
  <img src="{{site.baseurl}}/courses/how-to-contribute/publish-web.png"/>
</p>

You will then get a message asking you to start publishing. Select "Start Publishing."

<p align="center">
  <img src="{{site.baseurl}}/courses/how-to-contribute/start-publish.png"/>
</p>

After a few moments, you will get a new window. Here, you will see a line of html code labeled as "Embed Code." Select this and copy it (Ctl+C). Note that if you are embedding a **presentation**, you may specify the size and other desired features of the presentation **before copying** this html code.

<p align="center">
  <img src="{{site.baseurl}}/courses/how-to-contribute/embed-code.png"/>
</p>

####**3. Paste html Code in Markdown File**

Return to the markdown file and click the empty space before the "</div>" code. Then press "Ctrl-V" to paste the embed code. Your code should now resemble the following:

{% highlight html %}
	<div style="text-align: center"><iframe src=GOOGLE_DOC_SOURCE_AND_SPECIFICATIONS></iframe></div>
{% endhighlight %}

For example, if I want to embed a spreadsheet, this is what my code will look like:

{% highlight html %}
	<div style="text-align: center"><iframe src="https://docs.google.com/spreadsheets/d/1C9znokjgbBoPrOZiIe1BKdnNz44FkiyyZTDfi1rH-CI/pubhtml?widget=true&amp;headers=false"></iframe></div>
{% endhighlight %}

This spreadsheet will now appear like this on my web page:

<div style="text-align: center"><iframe src="https://docs.google.com/spreadsheets/d/1C9znokjgbBoPrOZiIe1BKdnNz44FkiyyZTDfi1rH-CI/pubhtml?widget=true&amp;headers=false"></iframe></div>

####**iframe Sizing and Options**

When embedding an "iframe," either for a video or a google doc, there are several options that can be specified.  These options include but are not limited to:

* frameborder - recommennd: frameborder="0"
* width
* height
* scrolling - ="yes" or "no"
* allowfullscreen (and mozallowfullscreen and webkitallowfullscreen) - ="true" or "false"

In the html code used to embed docs, these specifications are placed after the`src=SOURCE_HERE` and before `><iframe>`.

The most relevant of these options are the width and the height, as they will specify the size of the doc on the page. We recomend starting with the following: `width="400" height="400"` and adjusting from there. Width and height can also be set as percentages: `width="50%" height="100%"`.  this sets the dimensions of the iframe relative to the size of the entire page.

Keep in mind that if a document is modified (for instance, if you add rows or collumns in a spreadsheet), you may need to resize the iframe).

Here is the same spreadsheet from above, only now with several options specified:

{% highlight html %}
	<div style="text-align: center"><iframe src="https://docs.google.com/spreadsheets/d/1C9znokjgbBoPrOZiIe1BKdnNz44FkiyyZTDfi1rH-CI/pubhtml?widget=true&amp;headers=false" frameborder="0" width="50%" height="300" scrolling="no"></iframe></div>
{% endhighlight %}

<div style="text-align: center"><iframe src="https://docs.google.com/spreadsheets/d/1C9znokjgbBoPrOZiIe1BKdnNz44FkiyyZTDfi1rH-CI/pubhtml?widget=true&amp;headers=false" frameborder="0" width="50%" height="300" scrolling="no" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe></div>
