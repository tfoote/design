
If your change is more extensive, you wish to work offline, or you want to see what your changes will look like on the live site, you can do so by running Jekyll locally. We recommend using docker to isolate the installation from your local machine. 

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
