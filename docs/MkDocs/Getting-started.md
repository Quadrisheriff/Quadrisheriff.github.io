---
title: MkDocs Quickstart.
summary: MkDocs quickstart guide.
authors:
    - Quadri Sheriff 
---

![Screen Shot 2020-08-02 at 2 10 04 PM](https://user-images.githubusercontent.com/59125401/89128860-7053c880-d4f0-11ea-9ab3-e563aeb24568.png)

###**Introduction**

MkDocs is an open-source static site generator geared to creating technical documentation websites. In this guide, you will create a documentation website with MkDocs, and deploy the website to GitHub for hosting with GitHub pages.

###**Prerequisites**

This guide assumes that you have:
 
  * Python installed locally - visit [this link](https://realpython.com/installing-python/) for instructions on how to install python on mac and windows.

  * PIP installed locally - visit [this link](https://realpython.com/what-is-pip/) for instructions on how to install 
  PIP on mac and windows.

  * Git installed locally and GitHub account - visit [this link](https://product.hubspot.com/blog/git-and-github-tutorial-for-beginners) for instructions on how to setup Git and GitHub.

---

###**Installing MkDocs with pip**

MkDocs can be installed with pip using the `pip install` command.

```Bash
pip install mkdocs
```

After Installing MkDocs, verify your installation with the  `mkdocs --version` command.

```Bash
$ mkdocs --version
mkdocs, version 1.1
```  

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

###**Configuring your website**

All of MkDocs configurations are done using the `mkdocs.yml` file in the projects folder.

Add the following configuration into your `mkdocs.yml` file to specify your project's information.

```mkdocs.yml
## Add your website's information
site_name: Mkdocs Project
site_description: A new mkdocs project
site_author: Quadri Sheriff
```

Visit [MkDocs website](https://www.mkdocs.org/#getting-started) for more configuration options.

###**Adding Contents to your website**

You can add pages to your website by putting the markdown files in the `docs` folder.

Create a second markdown file in the `docs` folder.

```
touch second.md
```

Edit the page

```
---
title: Second Page. ## page name
summary: Mkdocs project second page. ## page summary
authors:
    - Quadri Sheriff ## page author
---

This is the second page of our new mkdocs tutorial.

```
You can add the new page into the website navigation bar by configuring the `mkdocs.yml` file.

```mkdocs.yml
## Add your website's information
site_name: new-mkdocs-project
site_description: A new mkdocs project
site_author: Quadri Sheriff


## Edit the Nav bar
nav:
- Home: index.md
- Second page: second.md

```

###**Starting the MkDocs development server**

Mkdocs ships with a development server that allows you to preview your documentation during production.

Use the `mkdocs serve` command to start the dev-server.

```shell 
$ mkdocs serve

INFO    -  Building documentation... 
INFO    -  Cleaning site directory 
INFO    -  Documentation built in 0.30 seconds 
[I 200729 15:08:04 server:296] Serving on http://127.0.0.1:8000
INFO    -  Serving on http://127.0.0.1:8000
[I 200729 15:08:04 handlers:62] Start watching changes
INFO    -  Start watching changes
[I 200729 15:08:04 handlers:64] Start detecting changes
INFO    -  Start detecting changes
```

The development server will be deployed at [http://localhost:8000](http://localhost:8000). 


The development server supports live changes, and will reload automatically to preview any changes made in your documentation files.

You can close the development server by pressing `CTRL C` in your terminal window.

###**Building your website**

Use the `mkdocs build` command to generate all your websites static files.

```
$ mkdocs build
INFO    -  Cleaning site directory 
INFO    -  Building documentation to directory: /Users/sheriff/new-mkdocs-project/site 
INFO    -  Documentation built in 0.32 seconds 
```

This command will create a site folder where all the static files are stored. You can deploy your website on publishing platforms like AWS or GitHub pages using this files.

###**Deploying your project to GitHub**

To deploy your project to Github

create a new github repository - git@github.com:Quadrisheriff/mkdocs-project.git.

Then, initialize your project directory with git and add a remote origin.

```bash
$ git init

$ git remote add origin git@github.com:Quadrisheriff/mkdocs-project.git

```

Now, push your directory to github.

```bash
$ git add .

$ git commit -m 'mkdocs-project'

$ git push --set-upstream origin master

```

###**Publishing your website with GitHub pages**

You can publish your website online directly from GitHub using GitHub pages. Use the `mkdocs gh-deploy` command to publish MkDocs websites with GitHub pages.

```bash
mkdocs gh-deploy
```







