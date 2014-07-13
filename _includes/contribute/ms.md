

To get started with Markdown syntax, refer to this link: [https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

Below we'll mention additional Markdown syntax relevant to this site.

##Syntax Highlighting in Code Blocks

Use the following format in order to obtain appropriate syntax when writing code:

{% raw %}

	{% highlight javascript %}  
	var s = "JavaScript syntax highlighting";  
	alert(s);  
	{% endhighlight %}

	{% highlight python %}  
	s = "Python syntax highlighting"  
	print s  
	{% endhighlight %}

{% endraw %}

Results:

{% highlight javascript %}
var s = "JavaScript syntax highlighting";
alert(s);
{% endhighlight %}

{% highlight python %} 
s = "Python syntax highlighting" 
print s 
{% endhighlight %}  

  
##Other Markdown Tips


####**Footnotes**

For footnotes, use this format:

	Clicking this number[^fn-sample_footnote] will lead you to a footnote.

	[^fn-sample_footnote]: Handy! Now click the return link to go back.


Result: 

Clicking this number[^fn-sample_footnote] will lead you to a footnote.

[^fn-sample_footnote]: Handy! Now click the return link to go back.

