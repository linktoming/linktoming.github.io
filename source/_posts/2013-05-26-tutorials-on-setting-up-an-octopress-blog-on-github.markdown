---
layout: post
title: "Tutorials on Setting up an Octopress Blog on Github"
date: 2013-05-26 10:03
comments: true
categories: 
---
I've been thinking to host a tech note blog using [Octopress](http://octopress.org/) on github for a while. It's free, tech oriented and simple for hackers. 

However, I found out that only reading the [official start here guide](http://octopress.org/docs/setup/) was not enough to get my blog up and running. I did't know how to update my new post or new settings to github.

After searched around, these were the additional articles that helped me to make this post possible.

* [Octopress: Setting up a Blog and Contributing to an Existing One](http://code.dblock.org/octopress-setting-up-a-blog-and-contributing-to-an-existing-one)
* [Creating a Github Blog Using Octopress](http://www.tomordonez.com/blog/2012/06/04/creating-a-github-blog-using-octopress/)

To summarize,we have two branches in github repository:

* master: used for the generated web content from which github will read for our github pages.
* source: the source code of Octopress and the posts we've written.

In our local machine, the root folder of Octopress is a git repository with only the source branch. It's the one we used for the origin/source. There is a _deploy folder in the root folder which is also a git repository with only the master branch. It's the generated web content for deployment or push to the origin/master.

The process for adding a new post and push to github:
	$ rake new_post["New Post"]
	$ rake generate
	$ rake preview
	$ git add .
	$ git commit -am "Some comment here." 
	$ git push origin source
	$ rake deploy




