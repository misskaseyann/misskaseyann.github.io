---
layout: post
title: "Make a Free Blog with Jekyll and GitHub Pages"
excerpt: "Learn how to make your own static website or blog for free using GitHub Pages and Jekyll. This tutorial is very easy and you will be up and running with a blog in no time!"
categories: [tutorial]
tags: [jekyll, programming, resources, tutorial, github, web, ruby]
comments: true
image:
  feature: http://i65.tinypic.com/2z8t5is.png
---
I will be showing you how to create your own free static website. It is super easy and doesn't take long to get set up. One thing that is required before starting is that you have a [GitHub account](https://github.com/). If you do, then feel free to continue reading. Otherwise, sign up and then meet me back here :)

Quick note: these instructions are mainly for Unix/Linux OS.

### Requirements
1. Open your terminal.
2. Check that you have Ruby 2.1.0 or higher installed:
```bash
$ ruby --version
ruby 2.X.X
```
3. If you do not have Ruby installed, install it by following directions on their [website](https://www.ruby-lang.org/en/documentation/installation/).
4. Install Bundler:
```bash
$ gem install bundler
# Installs the Bundler gem
```
5. Download and install Git. For more information see: [set up git](https://help.github.com/articles/set-up-git/).

### Create New Site
1. Be sure to direct terminal to where you would like your site folder to be. Create a new site:
```bash
$ jekyll new mysite
```
2. Move into that directory:
```bash
$ cd mysite
```
3. Install required gems:
```bash
$ bundle install
```
4. Verify everything is up and running correctly locally:
```bash
$ jekyll serve
```
5. Browse to [http://localhost:4000](http://localhost:4000) to see your website running!

### Pick a Theme
1. Jekyll, when installed, uses a default theme called minima. You can, however, use any theme you like. Here is a [collection of gem-packaged themes](https://github.com/planetjekyll/awesome-jekyll-themes) you can pick from if minima is not for you. I will use [swiss](https://github.com/broccolini/swiss) as an example.
2. In your Jekyll site's `Gemfile`, replace the line `gem "minima", "~> 2.0"` to `gem "your-theme-name"` or in my case `gem "jekyll-swiss"`.
3. In your Jekyll site's `_config.yml`, under Build settings, you will see the line `theme: minima`. Change that line to `theme: your-theme-name` or in my case `theme: jekyll-swiss`.
4. Run Bundler to install the theme gem and its dependencies:
```bash
$ bundle install
```
5. Verify everything install correctly:
```bash
$ jekyll serve
```
6. Browse to [http://localhost:4000](http://localhost:4000) to see your website running with its new theme!

### Create Repository for Your Site
1. In the root folder of your website, initialize a new Git repository for your Jekyll site:
```bash
$ git init
Initialized empty Git repository in /Users/username/mysite/.git/
```
2. Add and commit all your files:
```bash
$ git add .
$ git commit -m "Initial commit"
```
3. Navigate to GitHub and create a **New Repository** by clicking the **+** in the upper-right hand corner.
4. Name your repository *username*.github.io, where *username* is your username on GitHub. This must exactly match your username or else it won't work (case sensitive). ![](http://i66.tinypic.com/s3llqh.png)
5. Now push this repository for the command line by typing:
```bash
$ git remote add origin https://github.com/username/username.github.io.git
$ git push -u origin master
```
6. You are done! Navigate your browser to **https://username.github.io**. This will sometimes take a few minutes.

### Quickstart 
#### Pages
These are the basic building blocks. To add a page, just create an HTML file in the root directory with a suitable filename. For a site with a homepage, an about page, and a contact page, here's what the root directory and associated URLS might look like:
```
.
|-- about.md    # => http://example.com/about.html
|-- index.html    # => http://example.com/
└── contact.html  # => http://example.com/contact.html
```
If there are a lot of pages, they can be organized into subfolders. These will exist in the `_site` folder when your site builds.
#### Posts
The `_posts` folder is where your blog posts live. These are typically written in Markdown but HTML is also supported. To create a post, add a file to your `_posts` directory with the following format:
```
YEAR-MONTH-DAY-title.MARKUP
```
Where `YEAR` is a four-digit number, `MONTH` and `DAY` are both two-digit numbers, and `MARKUP` is the file extension representing the format used. For example:
```
2018-09-10-how-to-use-jekyll.md
```
All blog post files must begin with [front matter](https://jekyllrb.com/docs/front-matter/) which is used for layout and meta data. Here is a simple example:
```markdown
---
layout: post
title:  "Welcome to Jekyll!"
---

# Welcome

**Hello world**, this is my first Jekyll blog post.

I hope you like it!
```

### More Resources
This is just to get you started but if you are ready to dig through more information, be sure to check out [Jekyll](https://jekyllrb.com/) for the documentation. If you would like to add commenting to your pages, I recommend checking out [Staticman](https://staticman.net/docs/) since it is free and open sourced! I hope you liked this tutorial and that it was easy to follow. Now go make beautiful websites!