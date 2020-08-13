---
title: Material for MkDocs theme setup guide.
summary: Material for MkDocs theme installation and setup guide.
authors:
    - Quadri Sheriff 
---
 
![Screen Shot 2020-08-02 at 2 32 49 PM](https://user-images.githubusercontent.com/59125401/89128917-da6c6d80-d4f0-11ea-8e03-e60aa433f4c3.png)

###**Introduction**

The Material for MkDocs theme is a MkDocs theme that is built using the Google material design guidelines. 

The Material for MkDocs theme is easily customizable, mobile responsive, well-tested and well-optimized. In this guide, you will build a documentation website with the Material for MkDocs theme.

###**Prerequisites**

This guide assumes that you have [python](https://realpython.com/installing-python/) and [pip](https://realpython.com/what-is-pip/) installed locally on your computer. 

MkDocs, Markdown, Pygments, and Python Markdown markdown extensions will be installed as local dependecies to the Material for MkDocs theme.

###**Installing the Material for MkDocs theme with pip**

You can install the Material for MkDcs theme with `pip`.

```bash
pip install mkdocs-material
```

This command will install the material for mkdocs theme and all current compatible versions of all its dependencies.


###**Creating your website**

Create a MkDocs website with the `mkdocs new` command.

```shell
$ mkdocs new mkdocs-project
INFO    -  Creating project directory: mkdocs-project 
INFO    -  Writing config file: mkdocs-project/mkdocs.yml 
INFO    -  Writing initial docs: mkdocs-project/docs/index.md 
```
This command will generate a new directory with the following file structure:

```
mkdocs-project/
    docs/        
        index.md 
    mkdocs.yml  
``` 

The following files are:

- `docs` : Main docs folder.
- `docs/index.md` : Home page markdown file.
- `mkdocs.yml` : Mkdocs configuration file.


###**Configuring the Material for MkDocs theme**

Add the following into your mkdocs.yml file to configure the material for mkdocs theme and specify the project’s information.


```mkdocs.yml
## Add your website's information
site_name: Mkdocs Project
site_description: A new mkdocs project
site_author: Quadri Sheriff

## Configure the material theme
themes:
  name: material
  palette:   ## edit the website's color palette
    primary: 'purple'
```

Visit [MkDocs-material website](https://squidfunk.github.io/mkdocs-material/setup/changing-the-colors/) for more configuration options.

###**Adding Contents to your website**

You can add pages to your website by putting the markdown files in the `docs` folder.

First, create a markdown file in the `docs` folder:

```bash
touch new_page.md
```

Edit the page

```
---
title: New Page.  ## page name.
summary: Mkdocs project second page.   ## page summary.
authors:
    - Quadri Sheriff  ## page author, very useful when writing blog   ## posts.
---

This is the second page of our new mkdocs tutorial.

```

You can add the new page into the website navigation bar by configuring the mkdocs.yml file.

```mkdocs.yml
## Add your website's information
site_name: Mkdocs Project
site_description: A new mkdocs project
site_author: Quadri Sheriff

## Configure the material theme
themes:
  name: material
  palette:   ## edit the website's color palette
    primary: 'purple'

## Edit the Navbar
nav:
- Home: index.md
- New page: new_page.md

```

###**Starting the MkDocs development server**

Mkdocs ships with a development server(dev-server) that allows you to preview your documentation during production.

Use the mkdocs serve command to start the dev-server. This dev-server will be deployed at [http://localhost:8000](http://localhost:8000). 

The dev-server supports live changes and will reload automatically to preview any edit made in your documentation files.

You can close the dev-server by pressing `CTRL+C` into your terminal window.


###**Building your website**

Use the `mkdocs build` command to generate all your websites static files.

```
$ mkdocs build
INFO    -  Cleaning site directory 
INFO    -  Building documentation to directory: /Users/sheriff/new-mkdocs-project/site 
INFO    -  Documentation built in 0.32 seconds 
```

This command will create a site folder where all the static files are stored. You can deploy your website on publishing platforms like AWS or GitHub pages using this files.

