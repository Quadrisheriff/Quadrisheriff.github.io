---
title: Material for MkDocs Theme Quickstart.
summary: Material for MkDocs theme installation and setup guide.
authors:
    - Quadri Sheriff 
---
 
![Screen Shot 2020-08-02 at 2 32 49 PM](https://user-images.githubusercontent.com/59125401/89128917-da6c6d80-d4f0-11ea-8e03-e60aa433f4c3.png)

###**Introduction**

In this guide, I will walk you through the creation of a simple documentation website with the [Material for MkDocs theme]().

The [Material for MkDocs]() theme is an easily customizable, mobile responsive, well-tested and well-optimized MkDocs theme that is built using the Google material design guidelines.

###**Prerequisites**

This guide assumes that you have [python](https://realpython.com/installing-python/) and [pip](https://realpython.com/what-is-pip/) installed on your local machine. 


###**Installing the Material for MkDocs theme with `pip`**

Install the Material for MkDocs theme with `pip`.

```bash
pip install mkdocs-material
```

!!! note
    MkDocs, Markdown, Pygments, and Python Markdown markdown extensions will be installed automatically as local dependecies when you install the Material for MkDocs theme.

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

Add the following into your mkdocs.yml file to specify your project’s information, and also to configure the Material for MkDocs theme. 

```
# mkdocs.yml

site_name: Mkdocs Project                
site_description: A new mkdocs project
site_author: Quadri Sheriff


themes:                 # Configure the material for mkdocs theme
  name: material
  palette:             # edit your website's color palette
    primary: 'purple'
```

Visit the [MkDocs-material website](https://squidfunk.github.io/mkdocs-material/setup/changing-the-colors/) for more configuration options.

###**Adding pages into your website**

To add pages to your website, First create the markdown file in your `docs` folder.

```bash
# /docs

touch new_page.md
```

Then, add the following YAML front matter into your page to configure the page's information.

```

---
title: Second Page. ## page name
summary: Mkdocs project second page. ## page summary
authors:
    - Quadri Sheriff ## page author
---

```

Add markdown contents into the page.

```
# Second Page

This is the second page of our new mkdocs for material theme tutorial.

```

You can also add the new page into the website navigation bar by configuring your mkdocs.yml file.

```
# mkdocs.yml

site_name: Mkdocs Project
site_description: A new mkdocs project
site_author: Quadri Sheriff


themes:
  name: material
  palette:   ## edit the website's color palette
    primary: 'purple'

 
nav:       #  Edit the Navbar
- Home: index.md
- New page: new_page.md

```

###**Starting the MkDocs development server**

Mkdocs ships with a development server(dev-server) that allows you to preview your documentation during production.

Use the mkdocs serve command to start the dev-server. This dev-server will be deployed at [http://localhost:8000](http://localhost:8000). 

The dev-server supports live changes and will reload automatically to preview any edit made in your documentation files.

You can close the dev-server by pressing `CTRL+C` into your terminal window.


###**Building your website**

Use the `mkdocs build` command to generate all your website's static files.

```
$ mkdocs build
INFO    -  Cleaning site directory 
INFO    -  Building documentation to directory: /Users/sheriff/new-mkdocs-project/site 
INFO    -  Documentation built in 0.32 seconds 
```

This command will create a `site` folder where all the static files will be stored. You can deploy your website on publishing platforms like AWS or GitHub pages using this static files.

