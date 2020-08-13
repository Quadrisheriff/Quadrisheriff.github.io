---
title:  Hugo Quickstart.
summary:  Create a documentation website with Hugo and Docsy theme.
authors:
    - Quadri Sheriff 
---
#**Work In Progress**

###**Introduction**

Hugo is a speed optimized static site generating tool written in GO. Hugo can be used to create an type of website including documentation websites, blogs, portfolio websites etc.

In this guide, we will build a documentation site with Hugo-extended and the [Docsy theme]().

###**Prerequisites**

This guide assumes you have:

- GO installed locally - visit [this link](https://ednsquare.com/story/how-to-install-golang-on-windows-linux-mac------T3VRkO) for instructions on how to install Go on mac, windows and linux.

- Homebrew(MacOS and LINUX) - visit [this link](https://brew.sh/) for instructions on how to install homebrew on mac and linux.

- Chocolatey(windows) - visit [this link](https://chocolatey.org/docs/installation) for instructions on how to install chocolatey on windows.


###**Installing Hugo-extended**

=== "Windows"

Install hugo-extended with Chocolatey on windows.

```bash

choco install hugo-extended -confirm
```

Confirm your installation.

```bash
$ hugo version
Hugo Static Site Generator v0.64.1/extended windows/amd64 BuildDate: unknown
```

=== "MacOS" and "Linux"

Install hugo-extended with homebrew on mac and linux.

```bash

brew install hugo
```

Confirm your installation.

```bash
$ hugo version
Hugo Static Site Generator v0.64.1/extended darwin/amd64 BuildDate: unknown
```

###**Creating your website**

You can create a new Hugo project by using the `hugo new site` command.

```
$ hugo new site hugo-project

Congratulations! Your new Hugo site is created in /Users/salius/hugo-project.

Just a few more steps and you're ready to go:

1. Download a theme into the same-named folder.
   Choose a theme from https://themes.gohugo.io/ or
   create your own with the "hugo new theme <THEMENAME>" command.
2. Perhaps you want to add some content. You can add single files
   with "hugo new <SECTIONNAME>/<FILENAME>.<FORMAT>".
3. Start the built-in live server via "hugo server".

Visit https://gohugo.io/ for quickstart guide and full documentation.
```

###**Adding a theme to your website**

In this step, we will add the Docsy theme to our website.

cd to your project directory

```bash
cd hugo-project
```

Install .

```bash
sudo npm install -D --save autoprefixer
sudo npm install -D --save postcss-cli
```

Install the Docsy by adding it as a git submodule into your project.

```
git init
git submodule add https://github.com/google/docsy.git themes/docsy
echo 'theme = "docsy"' >> config.toml
git submodule update --init --recursive
```

###**Configuring your website**

###**Adding contents to your website**

###**Starting Hugo web server**

Start your development server with the `hugo server` command.

```
hugo server 
```
the development server will be hosted at [http://localhost:1313](http://loacalhost:1313)


Hugo ships with LiveReload built in, this allows you to preview changes realtime when your development server is running.

You can also run your dev server without livereload. Use the 



###**Building your website**

```
hugo -D
```


