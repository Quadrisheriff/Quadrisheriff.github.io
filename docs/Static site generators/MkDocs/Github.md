---
title:  Publishing your MkDocs website with GitHub pages.
summary: Publish your MkDocs website with GitHub pages.
authors:
    - Quadri Sheriff 
---

###**Introduction**

In this guide, you will deploy your MkDocs website to GitHub and publish the website with GitHub pages.

GitHub pages is a free hosting service offered by GitHub that allows you to publish your webistes for free directly from your GitHub repositories. GitHub pages is available in all public GitHub repositories and GitHub free for organizations.

###**Prerequisites**

This guide assumes that you have:

- A ready to deploy MkDocs website - You can follow our [MkDocs tutorial](/Static%20site%20generators/MkDocs/Getting-started/) for instructions on how to create a documentation website with MkDocs.  
- `git` installed locally and GitHub account - visit [product.hubspot.com](https://product.hubspot.com/blog/git-and-github-tutorial-for-beginners) for instructions on how to setup `git` and GitHub.

---

###**Deploying your project to GitHub**

To deploy your website on to GitHub:

1. Create a new github repository for your project - git@github.com:Quadrisheriff/mkdocs-project.git.
2. Initialize your project directory with git and add a remote origin. 
```bash
  git init
```
3. Add your repository as the remote origin.
```bash
git remote add origin git@github.com:Quadrisheriff/mkdocs-project.git
```
4. Verify your remote origin.
```
$ git remote -v
origin	git@github.com:Quadrisheriff/mkdocs-project.git (fetch)
origin	git@github.com:Quadrisheriff/mkdocs-project.git (push)
```
5. Add your new changes to `git`.
```bash
git add .
```
6. Commit your changes.
```
git commit -m 'mkdocs-project'
```
7. Push your directory to GitHub.
```
git push --set-upstream origin master
```

###**Publishing your website with GitHub pages**

Use the `mkdocs gh-deploy` command to deploy MkDocs websites directly from your terminal with GitHub pages. The link to your website will be printed out into your terminal window.

