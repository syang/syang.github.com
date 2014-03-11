---
layout: post
title: "getting started on Octopress"
date: 2014-02-25 16:10:44 -0800
comments: true
categories: Octopress
---

Octopress is a blogging engine built on top of Jekyll, and its documentation can be found at http://octopress.org/docs/, but here is a quick
summary of how to use it along with github pages.

## Github User pages
As how this blog is hosted, Github can help you host a blog from `http://username.github.com`. 

You need to first setup a user account `username`, and then you need to create a repo as`http://www.github.com/username/username.github.com`.

## Setup your blog configuration with Rake (One time work)
Octopress provides a configuration task that helps you set up all config related to your blog using the following command.
```sh
rake setup_github_pages
```
Copy the SSH or HTTPS URL from your newly created repository (e.g. `git@github.com:username/username.github.io.git`) 
and paste it in as a response.

## Write your blog posts
You need to run the following command to create a new blog entry.
``` sh
rake new_post["title"]
```
And you can use your favorite editor to edit the blog post content.

Moreover, you can ** Specify the page name and location **
You can add pages anywhere in your blog source directory and they'll be parsed by Jekyll. The URL will correspond directly to the filepath, so `about.markdown` will become `site.com/about.html`. If you prefer the URL `site.com/about/` you'll want to create the page as `about/index.markdown`. Octopress has a rake task for creating new pages easily.

```sh
rake new_page[super-awesome]
# creates /source/super-awesome/index.markdown
 
rake new_page[super-awesome/page.html]
# creates /source/super-awesome/page.html
```

## Generate and Preview Site

```sh
rake generate   # Generates posts and pages into the public directory
rake watch      # Watches source/ and sass/ for changes and regenerates
rake preview    # Watches, and mounts a webserver at http://localhost:4000
```

## Last, Push to Github to Publish

Publish the comment by the following, which push the generated site to `master` branch
```sh
rake generate
rake deploy
```

Do not forget to push the `source` branch 
```sh
git add .
git commit -m 'your message'
git push origin source
```





