---
title:  Hugo Quickstart.
summary:  Create a documentation website with Hugo and Docsy theme.
authors:
    - Quadri Sheriff 
---

###**Introduction**

Hugo is a speed optimized static site generating tool written in GO. Hugo can be used to create documentation websites, blogs, portfolio websites, etc. from markdown and HTML.

In this guide, you will build a documentation website with Hugo-extended and the [Docsy theme](http://docsy.dev/).

###**Prerequisites**

This guide assumes that you have:

- GO installed locally - visit [ednsquare.com](https://ednsquare.com/story/how-to-install-golang-on-windows-linux-mac------T3VRkO) for instructions on how to install Go on your local machine.

- Homebrew(MacOS and LINUX) - visit [brew.sh](https://brew.sh/) for instructions on how to install homebrew on mac and linux.

- Chocolatey(windows) - visit [chocolatey.org](https://chocolatey.org/docs/installation) for instructions on how to install chocolatey on windows.


###**Installing Hugo-extended**

=== "Windows installation"

     Install hugo-extended with `Chocolatey` on windows.

     ```bash
     choco install hugo-extended -confirm
     ```

     Verify your installation.

     ```bash
     $ hugo version
     Hugo Static Site Generator v0.64.1/extended windows/amd64 BuildDate: unknown
     ```

=== "MacOS installation"

     Install hugo-extended with `homebrew` on MacOS.

     ```bash
     brew install hugo
     ```

     Verify your installation.

     ```bash
     $ hugo version
     Hugo Static Site Generator v0.64.1/extended darwin/amd64 BuildDate: unknown
     ```

=== "Linux installation"

     Install hugo-extended with `homebrew` on linux.

     ```bash
     brew install hugo
     ```

     Verify your installation.

     ```bash
     $ hugo version
     Hugo Static Site Generator v0.64.1/extended darwin/amd64 BuildDate: unknown
     ```

###**Creating your website**

Create your new Hugo project with the `hugo new site` command.

```bash
$ hugo new site hugo-project

Congratulations! Your new Hugo site is created in /Users/sheriff/hugo-project.

Just a few more steps and you're ready to go:

1. Download a theme into the same-named folder.
   Choose a theme from https://themes.gohugo.io/ or
   create your own with the "hugo new theme <THEMENAME>" command.
2. Perhaps you want to add some content. You can add single files
   with "hugo new <SECTIONNAME>/<FILENAME>.<FORMAT>".
3. Start the built-in live server via "hugo server".

Visit https://gohugo.io/ for quickstart guide and full documentation.
```

The `hugo new` command will also create a directory with the following file structure:

```
hugo-project/
   ├── archetypes
   ├── config.toml
   ├── content
   ├── data
   ├── layouts
   ├── static
   └── themes
```

This files are:

- `archetypes`: Directory for storing content template files.
- `config.toml`: Hugo configuration file.
- `content`: Directory for content files.
- `data`: Directory for storing configuration files.
- `layouts`: Directory for storing `.html` template files.
- `static`: Directory for storing all static contents.
- `themes`: Directory for storing your theme.

###**Configuring your website**
All of your website's configuration details are defined in your `config.toml` file. Add the following bare minimum configuration into your `config.toml` file to specify your website's details.

```
baseURL = "http://quadrisheriff.org/"
languageCode = "en-us"
title = "Hugo Project"
theme = "docsy"

```

Visit [Hugo Website](https://gohugo.io/getting-started/configuration/) for more configuration options.

###**Adding a theme to your website**

The [Docsy theme](http://docsy.dev/) is a Hugo theme that is built specifically for creating medium to large technical documentation websites. The `Docsy` theme comes preloaded with basic documentation features like the search bar, the menu, etc.

To install the `Docsy` theme:

1. `cd` to your project's directory.
```bash
cd hugo-project
```
2. Install `postCSS` and `autoprefixer` .
```bash
sudo npm install -D --save autoprefixer
sudo npm install -D --save postcss-cli
```
3. Install the `Docsy` theme by adding it as a git submodule into your project.
```
git init
git submodule add https://github.com/google/docsy.git themes/docsy
echo 'theme = "docsy"' >> config.toml
git submodule update --init --recursive
```

###**Adding contents to your website**

All your website's content files are stored in the `content` directory found in your root folder. The website's pages will be rendered with the same content structure as the organized `content` folder, the top level nested subfolders in the `content` directory will also determine the layout and sections for your website.

`Docsy` ships with templates for three type of files in the content directory:

- Documentation files are stored in the `docs` directory.
- Blog contents are stored in the `blog` directory.
- Community oriented contents are stored in the `community`directory.

```
content
    |- docs
    |- blog
    |- community
```

To add a documentation page to your website:

1. Create your documentation markdown or HTML file inside the `docs` directory.
```
touch index.md
```
2. Add the following `yaml` frontmatter to configure the page's information.
```
---
title: "A new documentation page"
weight: 1
type: docs
description: >
  A new documentation page for our Hugo website.
---
```
3. Add markup contents into your page.
```
# Hugo project website 

This is our new documentation page.

```
To add a custom section into your webite, creating the custom subdirectory inside the `content` folder, then specify the page's template in the frontmatter of the page.

Visit the [Docsy website](https://www.docsy.dev/docs/adding-content/content/) for more information about adding contents into your website.

###**Starting Hugo web server**

Hugo ships with a web server that has Live reload built in. This allows you to preview your changes realtime when your web server is running.

Start your web server with the `hugo server` command.

The web server will be hosted at [http://localhost:1313](http://loacalhost:1313). The web server will automatically reload when you make any changes in your website's files.

###**Building your website**

Build your website with the `hugo` command. The command will generate all your website's static files and store them in the `./public/` directory. 

You can deploy your website on different hosting platforms with the generated static files.




