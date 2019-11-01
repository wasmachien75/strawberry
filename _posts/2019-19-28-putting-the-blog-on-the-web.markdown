---
layout: post
title:  "Putting a Jekyll blog on Github Pages"
date:   2019-11-01 20:29:00 +0100
---
Here I teach myself to put this blog on Github Pages so the whole world can read it, and therefore become smarter.
The good part about using Jekyll with Github is that the latter takes care of the build process for you. This means that Github automatically detects your Jekyll config, builds a static site from your source code and publishes it. If you would use another site generator, you would need to do this yourself, probably using a CI tool such as [Travis](https://www,travis-ci.org). Having this done automatically simplifies things dramatically, the downside is that tracking down problems in a black box system is a difficult task.

Being a good user, I mostly used Github's own documentation to figure everything out, but like most technical documentation it does not manage to explain this relatively short setup in a concise way. Let me try to do it a little bit better.

I assume the blog itself is created already. if this is not the case, read the quickstart docs on the Jekyll [site](https://jekyllrb.com/docs/).

## Step 1: Put the the source on Github

Some git experience is useful to follow this, although not a hard requirement.
Create a repository on Github. Do not initialize it. Create a repository in your blog folder, commit all your files, and push it to Github. This happens as follows:

```bash
cd blog #Enter your blog directory
git init #Create a new repository
git add * #Add all files to the staging area
git commit -m "First commit" #Commit them
git remote add origin https://your-git-remote-url #Add the remote to your git config
git push --set-upstream origin master #Push it to the remote (and tell git that the remote branch should track the master branch so we can push/pull/merge)
```
By default, Jekyll will have created a `.gitignore` file that prevents the _site folder (the folder that contains the built site) from being added to your git repository. 

Go to your repository on Github and make sure your files are there: `_config.yml` and the `_posts` directory are the ones you should be most concerned about.

## Step 2: Modify _config.xml

This one is important. Assuming you do not create a user site, your site will have a URL with following pattern: ***https://{username}.github.io/{repository-name}***. Jekyll needs to know this in order to create correct references. You should therefore set the name of your repository as your `baseurl` in `_config.yml`, e.g. `/my-first-blog`.

It took me a while to figure this out - when you don't do this, the site will work, but the CSS will not load and you will have 404 errors all around the place. I did not see this subtle, but important detail explained in Github's own documentation!

Feel free to fill out the other fields as well.

## Step 3: Configure your Github repository

We now need to tell Github that we want to use this repository to act as the source for a Github Pages website. To do this, go to the **Settings** of your repository and scroll down to the **Github Pages** section. Select **master branch** as the source of your site. After saving, Github will tell you that your site is ready to be deployed. It can even set the theme for you, isn't that cool? Do note that this will silently add a commit to your `_config.yml` file, so make sure to pull before you push later on.
