##Markdown Basics

To get started with Markdown syntax, refer to this link: [https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

Below we'll mention basic Markdown syntax relevant to this site.

###**1. Headers**

Headers are preceded by 1-6 hashtags (#), ranging form largest headers (1 hashtag) to smallest headers (6 hashtags). 

For example, here is a large header and a smaller one following it:

	#Large Header  

	####Smaller Header  

This would look like this:

#Large Header (size #)

####Smaller Header (size ####)

Headers can also be defined by underlining with -- or ==. For example:

	Larger Header
	==

	Smaller Header
	--

	Smaller Header (adding lines underneath to underline)
	-- 
	---

Would look like:

Larger Header  
==

Smaller Header
--

Smaller Header (adding lines underneath to underline)
--
---

###**2. Paragraphs and Breaks**

* In order to start a new pragraph, put a blank line between paragraphs

* If you want a line break, end your line with two spaces

###**3. Block Quotes**

To produce a blockquote, use the following format:

	> Blockquote
	>
	> In order to get blank lines, insert a space after ">"
	>
	> > Second paragraph in the blockquote, nested
	>
	> ## This is an h2 in a blockquote

> Blockquote
> 
> In order to get blank lines, insert a space after ">"
> 
> > Second paragraph in the blockquote, nested
> 
> ## This is an h2 in a blockquote

###**4. Bold and Itallics**

	*itallics* or _itallics_ or it*tal*lics

*itallics* or _itallics_ or it*tal*lics

	**bold** or __bold__ or this**is**bold

**bold** or __bold__ or this**is**bold

	***bold and itallics*** or ___bold and itallics___ or **_bold and itallics_**

***bold and itallics*** or ___bold and itallics___ or **_bold and itallics_**

###**5. Lists**

For **bulletpoint** use the following format:

	All of these...
	
	* This		+ This		- This
	* is		+ is		- is
	* list		+ list		- list

...look like this:

* This
* is
* list

For **ordered lists** use the following format:

	1. This
	2. is
	3. ordered

1. This
2. is
3. ordered

Lists can have multiple levels:

	* This
	  * list
	    * has
	* many
	 1. levels
	  + and has many
	    - ways to make it

* This
  * list
    * has
* many
 1. levels
  + and has many
    - ways to make it

You can also make these lists more intricate, like so:

	* A list item.

	  With multiple paragraphs.

	  > and a blockquote
	
	* Another list item with  
	  a hard wrapped 2nd line. 

	  	and a code block

* A list item.

  With multiple paragraphs.

  > and a blockquote

* Another list item with  
  a hard wrapped 2nd line. 

  	and a code block

###**6. Links**

	An [inline link](http://xrl.us/ "optional title").

	A [reference link][id] (id defined elsewhere)

	[id]: http://example.com/ "optional title"   
	 
	or

	[id]: <http://example.com/> (optional title)

	or 

	[id]: http://example.com/long/path/to/resource
	  "optional title"  

	<http://example.com>  
	<address@example.com>


An [inline link](http://xrl.us/ "optional title").

A [reference link][id] (id defined elsewhere)

[id]: http://example.com/ "optional title"   
 
or

[id]: <http://example.com/> (optional title)

or 

[id]: http://example.com/long/path/to/resource
  "optional title"  

<http://example.com>  
<address@example.com>

###**7. Horizontal Lines**

	--- or *** or ___ make a line by itself

***

###**8. Escaping**

In markdown, a backslash ( \ ) escapes the folowing characters:

\ ` * _ { } [ ] ( ) # + - . !

	\*this text is surrounded by asterisks\*

	Avoid accidental numbered lists by escaping:  
	2014\. Happy New Year!

\*this text is surrounded by asterisks\*

Avoid accidental numbered lists by escaping:  
2014\. Happy New Year!

