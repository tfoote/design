#ROS Courses

Hello, welcome to ROS Courses! The goal of the repository/website is to consolidate existing online ROS education material and promote future collaborative course development.

This repository is a [Jekyll](http://jekyllrb.com/) website hosted on [Github Pages](http://pages.github.com/) at https://tfoote.github.io/design/

For more details on this site and project, please visit the site [https://tfoote.github.io/design/](https://tfoote.github.io/design/) or deploy (instructions below). Information can be found in the [About]({{ site.baseurl }}/about/) section of the site or, in the repository, in design/about.md. 

In addition, for information on future work and opportunities to contribute, see section "Thoughts on Users and Future Work" in "About" section. 

## Requirements for deployment

For deploying, you must access and clone repository through GitHub.

 you need jekyll jekyll-sitemap pygments and nodejs installed

Then use jekyll command directly. 

## Working Locally and Requirements for Development

For local development and testing, you need jekyll jekyll-sitemap pygments and nodejs installed (minimum version of jekyll required: )

If you do not have the required version of jekyll, alternatively you may install docker (ubuntu package docker.io) and use it to run jekyll in a container (minimum version of docker required: )

Once you have installed docker, you can run the site locally by running the following command in this repository:

```
./deploy_jekyll.sh
```

You can then view the site by navigating in your browser to:  [http://localhost:4000/](http://localhost:4000/)
