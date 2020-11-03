---
title: Jekyll Quickstart.
summary: Create a documentation website with the documentation theme for jekyll.
authors:
    - Quadri Sheriff 
---

![Screen Shot 2020-08-17 at 12 06 41 AM](https://user-images.githubusercontent.com/59125401/91368913-367d9580-e802-11ea-9804-767649ed04e5.png)

###**Introduction**

In this guide, I will walk you through the creation of a simple documentation website with Jekyll and the [Just The Docs](https://jekyllthemes.io/theme/just-the-docs) theme.

Jekyll is a free, blog aware, ruby-based, open source static site generator. Jekyll can be used to build blogs, documentation websites, portfolio websites, etc. directly from templates, markdown, and html.

####**Prerequisites**

This guide assumes that you have:

 - Ruby installed locally (version 2.5.0 or above) - visit [ruby-lang.org](https://www.ruby-lang.org/en/documentation/installation/) for instructions on how to install Ruby on your local machine.

 - Rubygems installed locally - visit [rubygems.org](https://rubygems.org/pages/download) for instructions on how to install Rubygems on your local machine.

 - Bundler installed locally - visit [bundler.io](https://bundler.io/) for instructions of how to install Bundler on your local machine.

---

###**Installing Jekyll gem**

=== "Windows installation"

    Install Jekyll with RubyGem on windows.

    ```bash
    gem install jekyll
    ```

    Verify your installation.

    ```bash
    $ jekyll -v
    jekyll 4.1.1
    ```

=== "MacOS installation"

     Install Jekyll with RubyGem on MacOS.

     ```bash
     sudo gem install jekyll
     ```

     Verify your installation.

     ```bash
     $ jekyll -v
     jekyll 4.1.1
     ```

=== "Linux installation"

     Install Jekyll with RubyGem on Linux.

     ```bash
     sudo gem install jekyll
     ```

     Verify your installation.

     ```bash
     $ jekyll -v
     jekyll 4.1.1
     ```

###**Creating up your website** 

Use the `Jekyll new` command to create a new Jekyll project. 

```bash
jekyll new jekyll-project
```

This command will generate a directory named `jekyll-project` with the following directory structure:

```
jekyll-project/
  _posts /
      welcome-to-jekyll.markdown
  _config.yml
   404.html 
   about.markdown 
   Gemfile 
   Gemfile.lock  
   index.markdown  
```

This files are:

- `_posts`- Directory for blog contents.
- `_config.yml`- Jekyll configuration file.
- `about.markdown`- markdown files.
- `index.markdown`- markdown files.
- `welcome-to-jekyll.markdown`- markdown files.
- `404.html` - 404 HTML file.
- `gemfile` and `gemfile.lock`- Ruby gem files.


###**Configuring your website**

All of Jekyll's confguration are done using your `_config.yml`. Add the following YAML keys into your `_config.yml` file to define your website's information.

```
title: Jekyll Project                     # The title of your website.
email: quadri@sheriff.com                 # your email address.
description: > A new jekyll website       # The description of your website.
baseurl: ""                               # the subpath of your site, e.g. /blog
url: http://quadrisheriff.com             # Your website's base URL.
twitter_username: quadrisheriff           # Your twitter username.
github_username:  quadrisheriff           # Your GitHub username.

```

Visit [jekyllrb.com](https://jekyllrb.com/docs/configuration/options/) for more information about your configuration options.

###**Setting up the Just the Docs theme**

The [Just The Docs](https://jekyllthemes.io/theme/just-the-docs) theme is a modern, high customizable, responsive Jekyll theme geared towards building technical documentation websites. 

The [Just The Docs](https://jekyllthemes.io/theme/just-the-docs) ships with documentation features like the search bar and menu preinstalled, this allows you to focus on writing good documentation. 

To install and set up the [Just The Docs](https://jekyllthemes.io/theme/just-the-docs) theme:

1. Add the following line to your `gemfile`.
```
gem "just-the-docs"
```
2. Install the theme and all its required dependecies.
```bash
bundle install
```
3. Change your theme name in your _config.yml file.
```
theme: just-the-docs
```

###**Adding contents to your website**

Jekyll allows for the usage of two type of content layouts - the `page` and `post` layout. 

#### Adding Pages to your website

Stand alone contents, documentation pages, etc. are created using the `page` layout

To add pages into your website:

1. Add your markdown or html files directly into your website's root folder, you can also group your page files into subfolders, this grouping will determine website's structure.
```
touch new_page.md
```    
2. Add the following `YAML` front matter into the page to specify the page's information.
``` 
---
layout: page
title: New page
permalink: /newpage/
---
```
3. Add markdown or HTML content into the page.
```
# New page
 
This is a new website page.
```

#### Adding posts to your website

The `post` layout is for your blog template. `post` files are created with the `YEAR-MONTH-DAY-title.md` naming format, and stored in the `_posts` folder.

To create a new blog post:

1. Navigate to the `_posts` folder.
```bash
cd _posts
```
2. Create your markdown or HTML file in the `YEAR-MONTH-DAY-title.md` format, where `YEAR` is any 4 digit number, `MONTH` is any 2 digit number, `DAY` is any 2 digit number, and`title` is your blog post title. .
```bash
touch 2020-08-18-new_post.md
```
3. Add the `post` file `YAML` frontmatter.
```
---
layout: post
title:  "New Post!"
---
```
4. Add markdown or HTML contents into your `post` file.
```
# New Post.

This is a new blog post.

```
###**Starting the Jekyll web server**

`Jekyll` ships with a web server that allows you to preview your changes during development. 

Start your web server with the `bundle exec jekyll serve` command. The web server will be hosted at [http://localhost:4000](http://localhost:4000).

!!! note
     Changes made to the _config.yml file will not reflect automatically in your web server, you have to close and restart the server to preview the changes.

Close the web server by pressing `CTRL C` in your terminal window.

###**Building your website**

Build your `jekyll` website with the`jekyll build` command. 

This command will generate all your website's static files and store them in a `_site` directory. You can easily deploy your website on different hosting platforms with the generated static files.
