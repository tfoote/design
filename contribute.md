---
layout: default
title: Contribute
---

#Contribute

All of the pages on this website have a sidebar on the right hand side with all pull requests (open and closed) which involve this file in some way. **_Please review the previous pull requests before proposing a change to prevent duplicates and to prevent rehashing issues already addressed._**

In addition, before contributing, please review the **About** section of this site to familiarize yourself with the purpose and organization of the content within.

##For Quick Changes

On the right hand side you'll find links to view the source of this page on Github.com and to edit this page in Github.com's on-line editor. The "Edit in Github" button will bring you to an on-line editor where you can make simple changes. Github will automatically fork this repository to your github user account, save your on-line changes to a branch there, and open a pull request against our repository on your behalf. This allows us to review and discuss changes to each page before accepting the pull request.

##For More Extensive Changes (recommended)

For more more extensive changes, you will want to:

1. First fork this repository
2. Clone it to your local machine (set up a local copy of the repository)
3. Edit it there
4. Then propose a pull request

The following instructions will lead you through this process.

####1. **Forking this Repository**

First make sure you don't already have a fork of this repository at:

    https://github.com/<your username>/design

If you do not, then browse to this [repository](https://github.com/ros2/design) and click on the "Fork" button:

<img src="{{ site.baseurl }}/img/fork.png"/>

Github.com will now go off and create a fork off this repository onto your user account. 

####2. **Clone Repo onto your Local Machine**
Then you can clone your fork of the repository by running this command in your terminal:

    git clone https://github.com/<your username>/design.git

This will clone this repository onto your machine into a folder called `design`. You can edit these files in this folder using your favorite editor.  Make sure to run the above command in the local folder where you wish to save the repository in.

For more instructions on how to fork and clone a repository, see these instructions:

[Github - how to fork a repo](https://help.github.com/articles/fork-a-repo)  
[Github - using pull requests](https://help.github.com/articles/using-pull-requests)

####3. **Editing Material**

Refer to sections below for adding/modifying material.

####4. **Submitting a Pull Request**

Once you are satisfied with your changes you can follow the Github.com tutorial on [creating a pull request](https://help.github.com/articles/creating-a-pull-request) against ours, where we can review and discuss your changes before merging.

----

#Adding or Modifying Material

Once you have your own copy of the “design” repository, it’s time to add your contribution to it.  This can be done in one of two ways:

* Modifying existing material **_or_**
* Adding new material


##Modifying Existing Material

If you are **modifying existing material**, navigate to the appropriate folder (courses, units, or topics) to find the file you want to edit.  Note that the files are written in Markdown.  For information on relevant Markdown syntax used in this site, see section on **Markdown Syntax**.

##Adding New Material

If you are **adding new material** to the site, there are some things you should consider:

* How does your material interface with our format (the “hierarchy” of content established on this site)?
* How will you organize your material using this hierarchy?
* How will you present your material given the tools available in markdown?

Once you’ve considered these questions, it’s time to start adding your own material.

####1. **Save Templates**

In your local copy of the repository, navigate to design/topics/lessons/ and find the appropriate templates for your new material. 

Open the template file for the type of content you wish to upload and **_IMMEDIATELY SAVE AS_**, choosing a clear name that describes the content in the file. Make sure that the name isn't already used elsewhere (including in another category). If you wish to use more than one word, represent spaces with a dash: **this-is-an-example.md**

####2. **Fill in Header**

At the top of each template, you'll need to fill in the header with the appropriate:

* Title
* Abstract
* Reference ID (The name of the markdown file you are edditing: this-is-an-example)
* tags (key words by which the file can be searched for)
* skills (what does the user get from the file? similar to tags)
* Units (if "course") or Topics (if "unit") - same format as reference ID: give the redererence IDs of the files you are citing
* previous (for topics only) - what previous skills should the user cover?

####3. **Add your Material**

Once you have the header set up, go ahead and fill in the template with your material! For any questions regarding syntax, refer to the "Markdown Syntax" section on this page.

----

#Testing and Working Offline

If you change is more extensive, you wish to work offline, or you want to see what your changes will look like on the live site, you can do so by running Jekyll locally. We recommend using docker to isolate the installation from your local machine. 

####**Simple Testing Using Docker (recommended)**

If you don't want to or can't install the version of jekyll required you can just use the script deploy_jekyll.sh for quick deployment (included in the **design** repository). 

First install docker:

    sudo apt-get install docker

Then, before each work session, navigate in your terminal to your local copy of the design repo and run:

    ./deploy_jekyll.sh

You will be prompter for your root password.

Now, you can navigate to [http://0.0.0.0:4000](http://0.0.0.0:4000) in your browser and view the changes as you make them (if you do not see changes in the browser, refresh the page).


####**Full installation instructions**

If you do not want to use docker as instructed above this will install jekyll on your local machine. The docker instance does this for you inside the container. 

[http://jekyllrb.com/docs/installation/](http://jekyllrb.com/docs/installation/)

    sudo gem install jekyll jekyll-sitemap

Once you have Jekyll installed you should be able to run this command:


    jekyll serve --watch --baseurl=''


The `jekyll server` command will start a web server which you can access at [http://localhost:4000](http://localhost:4000) locally. The `--watch` option will cause the jekyll web server to regenerate pages which are changed each time they are modified. This allows you to make quick edits to the documents and then refresh the web page to get the changes immediately. The `--baseurl=''` option sets the `baseurl` variable for the site's global config, allowing static files like the `css` and `js` files work on your local host.

----

#Markdown Syntax - How to add files and format content

For help with Markdown syntax, refer to this link: [https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)


###Blocks of Code

When writing blocks of code, use the following format:

{% raw %}

	{% raw %}

		code here

	{% endraw %}

{% endraw %}

###Syntax Highlighting in Code Blocks

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

