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

If you use the Chirpy theme like I did, install _v3.2.11_ instead of the latest version to avoid version mismatches when you build and serve your blog.

Once Ruby and Jekyll are succesfully installed, open a terminal in your project directory and run the following commands:

```bash
bundle install
bundle execute jekyll serve
```
These commands finish installing necessary dependencies, build your project, and serves it locally. This may take a minute or two to run so take a second to pat yourself on the back - the most tedious part of this process is behind you! 

When the commands finish executing, look for the local server address where your blog is hosted on your machine. It'll most likely be `http://127.0.0.1:4000/`. Open up that address in your browser, and you'll see your blog. Right now, it just the default template for whatever theme you chose earlier. It's time to give it a little character.

## Blog Customization
Open your local copy of the project in your favorite IDE and open `_config.yml`. Change the title, tagline, and description to whatever you'd like for your blog. In the _social_ section, set your name and email. Set the url to `https://username.github.io`. 

```yml
title: Your Blog Title
tagline: Your blog tagline.
description: Your blog description.

url: "http://username.github.io"
```

For your first blog post, create a new file in the `_posts` directory. The naming format for blog posts is `YYYY-MM-DD-title.md`, so you can name the file something like `2026-08-22-hello-world.md`. 

Each blog post markdown file requires some metadata at the top of the file. Specify the post's title, date, categories, and tags in the metadata section, then add your post content to the file in markdown format.

```markdown
---
title: "Hello World"
date: 2026-08-22 12:00:00 -0500
categories: [Hello World]
tags: [Hello World]
---

# Header 1
Put the rest of your super interesting blog content here.

```

Save the file and head back over to `http://127.0.0.1:4000/` (or wherever your blog is being served locally). Now you can see the effect of the changes you made to `_config.yml` and your first blog post! This is fantastic, but it's still only available on your machine. We want your blog to be available to the Internet so that everyone can ready all the cool stuff you're going to post on your blog.

Commit and push your changes. Github Pages handles the build and deployment of your project. You can check the status of this workflow in the _Actions_ tab of your project on Github. Once the workflow completes successfully, head over to `username.github.io` in your browser. Congratulations, your blog is now publicly hosted and available to others.


## DNS Configuration
To link your new blog to your custom domain, you'll need to configure the DNS settings in your domain registrar. I used Namecheap to buy my domain for about $12.

To point your custom domain to your blog, add the following A records and CNAME record to your domain settings. The full documenation for these configurations is available [here](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site).


| Type   |  Host  | Value          | TTL      |
|--------|--------|----------------|----------|
|A Record| @      |185.199.108.153 | Automatic|
|A Record| @      |185.199.109.153 | Automatic|
|A Record| @      |185.199.110.153 | Automatic|
|A Record| @      |185.199.111.153 | Automatic|
|CNAME   | www    |username.github.io. | Automatic|

Change the url in `_config.yml`to your domain (i.e `www.your-domain.com`).

In your project's _Settings > Pages_ page on Github, add your domain to the _Custom Domain_ section (i.e. `www.your-domain.com`). The value you enter should **exactly** match the value in the `CNAME` file in your project. Otherwise, you may have issues generating the TLS certificate needed for HTTPS. 

Save your custom domain to kick of the DNS Check process. This is handled by Github Pages to make sure your DNS settings were configured properly. You can follow the status of the DNS check on Github.

And now, you wait! It can take serveral hours for the DNS configurations to propagate. Go do the dishes, or fold that pile of clothes you've been ignoring. 


- add section for profile pic and icon + favicon