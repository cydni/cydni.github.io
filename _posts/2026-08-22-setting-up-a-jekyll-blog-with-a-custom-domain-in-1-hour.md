---
title: "Setting Up a Jekyll Blog With a Custom Domain in 1 Hour"
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
These commands finish installing necessary dependencies, build your project, and serves it locally. This may take a minute or two to run so take a second to pat yourself on the back - the most tedious part of this process is behind you! 

When the commands finish executing, look for the local server address where your blog is hosted on your machine. It'll most likely be `http://127.0.0.1:4000/`. Open up that address in your browser, and you'll see your blog. Right now, it just the default template for whatever theme you chose earlier. It's time to give it a little character.

## Blog Customization
In your local copy of the repo, open `_config.yml`. Change the title, tagline, and description to whatever you'd like for your blog. In the _social_ section, set your name and email. Set the url to `https://username.github.io`. 

For your first blog post, create a new file in the `_posts` directory. The naming format for blog posts is `YYYY-MM-DD-title.md`, so you can name the file something like `2026-08-22-hello-world.md`. 

Each blog post markdown file requires some metadata at the top of the file. Specify the post's title, date, categories, and tags in the following format.

```markdown
---
title: "Hello World"
date: 2026-08-22 12:00:00 -0500
categories: [Hello World]
tags: [Hello World]
---
```
- profile pic (?)

## DNS Configuration
- a names and c names
- make sure github has www.domain.com (to match CNAME in project)
- change url to www.domain.com