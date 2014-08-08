Another nifty way of adding material that might be used in multiple places is by creating an **"include"** file.  This is a markdown file that can be referenced in one or several markdown files. 

For example, the material in the "Contribute" tab for the site is almost idential to the material in the course "How to contribute". That is because both the course and the tab are referencing the same markdown **"include"** files. 

####**Format**

The format for creating an include file is as follows:

1. In the course directory that you are working in, make a new folder called "includes"

2. In that folder, save the markdown file that you wish to include. Note that you **do not** need a header for this file, as it will be included in another file that has appropriate header formatting.

3. In the parent file, use the following code to "include" the markdown file:

{% raw  %}
	{% include COURSE_DIR/includes/INCLUDE_FILE.md %}
{% endraw %}
