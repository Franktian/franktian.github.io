---
layout: post
title: "How I setup my first octopress blog and create my first post"
date: 2014-11-04 21:38:01 -0500
comments: true
categories: 
---
After playing around with Octopress' [official documentation](http://octopress.org/docs/setup/). I finally got this blog setup and found this Octopress blogging tool is so awesome that fits all needs for a lazy developer like me. It gives me full control of all the source files in such an easy way(unlike Wordpress). And the deployment process is ridiculously easy:
```
rake generate
rake deploy
```

So if you would like to find an easy-to-use blogging system and you have some basic familarities with unix command line, Octopress is highly recommended.

Octopress' official guideline is definitely quite helpful. However I still got some problems that's not covered from their doc while I was going through.

I am on OSX terminal, after cloning the repo and typing in the following command:
```
gem install bundler
```
I got the following error
```
ERROR:  While executing gem ... (Gem::FilePermissionError)
    You don't have write permissions for the /Library/Ruby/Gems/2.0.0 directory.
```
So I saw a [stackoverflow question](http://stackoverflow.com/questions/14607193/installing-gem-or-updating-rubygems-fails-with-permissions-error) that solves this problem. The answer recommended a way to install tool that controls the ruby version. I spent like an hour but did not get my problem solved. And it was actually one of the comment under the question that solved my problem:
```
sudo gem install bundler
```

I am not quite sure about what sudo means, but right now, to me, it's just like providing administrative access, and solves my access denied error.

After setting up all the requirements, the deployment process went pretty easy. I was deploying to [Git pages](https://help.github.com/articles/user-organization-and-project-pages/). If this is the first time you are using git hosting service, you might need to wait for a few minutes for your blog to be available on Github's server.

And, if you type in:
```
rake preview
```
You should be able to view your blog at 'localhost:4000'

Finally, I found it quite convenient to keep running
```
rake watch
```
and
```
rake preview
```
on two separate terminal windows while I am editing the source of this post. I could directly see the changes after saving and refreshing the browser.

Furthermore, take a look at [LiveReload](http://livereload.com/) if you got an extra monitor and would like to enjoy some cool stuff done by the real geeks.