---
layout: tutorial
title: Code and Syntax Highlighting
abstract:
 Learn code syntax in markdown
reference_id: syntax-highlighting
tags: [markdown, code, syntax]
skills: [markdown code syntax]
required_skills: []
---

# {{ page.title }}

Here you will learn code syntax in Markdown.

##Code Blocks

You can make a code block by using the following format:

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
