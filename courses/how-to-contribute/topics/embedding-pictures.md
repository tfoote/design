---
layout: tutorial
title: Embedding Pictures
abstract:
 Write abstract here
reference_id: embedding-pictures
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

##Discourse

<div id="discourse-comments"></div>

<script type="text/javascript">
  var discourseUrl = "https://tfoote.github.io/design/courses/how-to-contribute/how-to-contribute/",
      discourseEmbedUrl = 'https://tfoote.github.io/design/link-to-blog-entry.html';

  (function() {
    var d = document.createElement('script'); d.type = 'text/javascript'; d.async = true;
      d.src = discourseUrl + 'javascripts/embed.js';
    (document.getElementsByTagName('head')[0] || document.getElementsByTagName('body')[0]).appendChild(d);
  })();
</script>


##Juvia

<script type="text/javascript" class="juvia">
(function() {
    var options = {
        container    : '#comments',
        site_key     : '(some site key)',
        topic_key    : location.pathname,
        topic_url    : location.href,
        topic_title  : document.title || location.href,
        include_base : !window.Juvia,
        include_css  : !window.Juvia,
        comment_order: 'latest-first'
    };

    function makeQueryString(options) {
        var key, params = [];
        for (key in options) {
            params.push(
                encodeURIComponent(key) +
                '=' +
                encodeURIComponent(options[key]));
        }
        return params.join('&');
    }

    function makeApiUrl(options) {
        // Makes sure that each call generates a unique URL, otherwise
        // the browser may not actually perform the request.
        if (!('_juviaRequestCounter' in window)) {
            window._juviaRequestCounter = 0;
        }

        var result =
            'http://juvia-demo.phusion.nl/api/show_topic.js' +
            '?_c=' + window._juviaRequestCounter +
            '&' + makeQueryString(options);
        window._juviaRequestCounter++;
        return result;
    }

    var s       = document.createElement('script');
    s.async     = true;
    s.type      = 'text/javascript';
    s.className = 'juvia';
    s.src       = makeApiUrl(options);
    (document.getElementsByTagName('head')[0] ||
     document.getElementsByTagName('body')[0]).appendChild(s);
})();
</script>

