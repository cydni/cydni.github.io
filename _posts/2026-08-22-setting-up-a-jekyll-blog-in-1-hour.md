---
title: "Setting Up a Jekyll Blog in 1 Hour"
date: 2026-08-22 12:00:00 -0500
categories: [Jekyll, blog]
tags: [Jekyll, blog]
---

In the spirit of honesty, I’ll admit that it took me a *biiit* longer than an hour to get everything setup. **BUT** - if you follow the steps I outline, I’m confident you’ll be able to manage it.

## Project Setup
First, the fun part: pick a theme. There are plenty of nice (free) Jekyll themes out there to choose from. Try not to fall down the rabbit hold and spend half an hour scrolling through them. I went with the [Chirpy](https://github.com/cotes2020/chirpy-starter) theme.

When you find a theme you like, fork the github repository into a new project. Name the project ``` username.github.io```. Clone the repository locally so you can easily edit files later.

## Dependency Installation
Install Ruby and Jekyll following the instructions in [this guide](https://jekyllrb.com/docs/installation/). 

If you use the Chirpy theme like I did, install _v3.2.11_ instead of the latest version to avoid version mismatches when you try to build and serve your blog.

Once Ruby and Jekyll are succesfully installed, open a terminal in your project directory and run the following commands:

```bash
bundle install
bundle execute jekyll serve
```
These commands finish installing necessary dependencies, build your project, and serves it locally. This may take a minute or two to run so take a second to pat yourself on the back - the most tedious part of this process is behing you! 

## Blog Customization
- configure config.yaml
- initial blog post
- profile pic (?)

## DNS Configuration
- a names and c names
- make sure github has www.domain.com (to match CNAME in project)
- change url to www.domain.com