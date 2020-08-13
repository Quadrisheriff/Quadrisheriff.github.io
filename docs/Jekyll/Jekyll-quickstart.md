---
title: Jekyll Quickstart.
summary: Create a documentation website with the documentation theme for jekyll.
authors:
    - Quadri Sheriff 
---
#**Work in progress**

###**Introduction**

####**Prerequisites**

This guide assumes that you:

 - Ruby installed locally (version 2.5.0 or above) - visit [this link](https://www.ruby-lang.org/en/documentation/installation/) for instructions on how to install Ruby on mac, windows and linux.

 - Rubygems installed locally - visit [this link](https://rubygems.org/pages/download) for instructions on how to install Rubygems.

---

###**Installing Jekyll gem**

=== "Windows installation"

Install with gem.

```bash
gem install jekyll
```

Verify your installation.

```bash
jekyll -v
```

=== "Mac and Linux installation"

Install with gem.

```bash
sudo gem install jekyll
```

Verify your installation.

```bash
jekyll -v
```

###**Creating your website** 

Use the `Jekyll new` command to create a new Jekyll project and install all the neeeded dependecies.

```bash
jekyll new jekyll-project
```


```
jekyll-project
    _posts
        welcome-to-jekyll.markdown
    _config.yml
    404.html
    about.markdown
    Gemfile
    Gemfile.lock
    index.markdown
```

###**Adding a theme**

###**Configuring your website**

###**Adding contents to your website**

###**Starting Jekyll development server**

```bash
bundle exec jekyll serve
```

This command will start a development server at [http://localhost:4000](http://localhost:4000).


