---
layout: post
title:  "Putting the blog on the web"
date:   2019-10-28 20:29:00 +0100
---
Here I teach myself to put this blog on Github Pages so the whole world can read it, and therefore become smarter.

## Step 1: Put the thing on Github*

The easy part. Create a repository on Github. Do not initialize it.
Create a repository in your blog folder, commit all your files, and push it to Github. This happens as follows:

```bash
cd blog #Enter your blog directory
git init #Create a new repository
git add * #Add all files to the staging area
git commit -m "First commit" #Commit them
git remote add origin https://your-git-remote-url #Add the remote to your git config
git push --set-upstream origin master #Push it to the remote (and tell git that the remote branch should track the master branch so we can push/pull/merge)


