---
title:  Publishing your Jekyll website with GitHub pages.
summary: Publish your Jekyll website with GitHub pages.
authors:
    - Quadri Sheriff 
---

###**Introduction**

You will learn how to deploy and host a Jekyll website with [GitHub pages](https://pages.github.com/) in this guide.

[GitHub pages](https://pages.github.com/) is a free hosting service offered by GitHub that allows you to publish your website projects for free directly from your GitHub repositories. 

[GitHub pages](https://pages.github.com/) is powered with the Jekyll engine, hence publishing Jekyll websites with [GitHub pages](https://pages.github.com/) is a much more simplified process compared to other static site generators.

###**Prerequisites**

This guide assumes that you have:

- A ready to deploy Jekyll website - you can check out our [Jekyll quickstart tutorial](/Static%20site%20generators/Jekyll/Jekyll-quickstart/) for details on how to set up a documentation website with Jekyll. 
- `git` installed locally and GitHub account - visit [product.hubspot.com](https://product.hubspot.com/blog/git-and-github-tutorial-for-beginners) for instructions on how to setup `git` and GitHub.

---

###**Deploying your project to GitHub**

Follow these instructions to deploy your Jekyll project to GitHub.

1. Create a GitHub repository for your project - git@github.com:Quadrisheriff/jekyll-project.git.
2. Initialize your project directory with `git`.
```bash
git init
```
3. Add your repository as the remote origin.
```bash
git remote add origin git@github.com:Quadrisheriff/jekyll-project.git
```
4. Verify your remote origin.
```
$ git remote -v
origin	git@github.com:Quadrisheriff/jekyll-project.git (fetch)
origin	git@github.com:Quadrisheriff/jekyll-project.git (push)
```
5. Add your new changes to `git`.
```bash
git add .
```
6. Commit your changes.
```
git commit -m 'jekyll-project'
```
7. Push your directory to GitHub.
```
git push --set-upstream origin master
```

###**Configuring your website to work with GitHub pages**

1. Open your `Gemfile`.
2. Un-comment the following line in your gemfile.
```
# gem "github-pages", group: :jekyll_plugins
```
![Screen Shot 2020-09-12 at 4 49 41 PM](https://user-images.githubusercontent.com/59125401/92999393-658d4a00-f518-11ea-876d-7f907d8644e6.png)
3. Specify your `baseurl` in your `_config.yml` file.
```
baseurl: "/jekyll-project"
```
![Screen Shot 2020-09-13 at 3 29 09 AM](https://user-images.githubusercontent.com/59125401/93008834-6c947680-f571-11ea-84f5-cdf673c7dc4b.png)
4. Add your new changes to `git`.
```bash
git add .
```
7. Commit your changes.
```
git commit -m 'jekyll-project jekyll configuration'
```
6. Push your directory to GitHub.
```
git push 
```

###**Enabling GitHub pages**

1. Browse to your website's repository on GitHub.
2. Click **Settings**.<br />
![Screen Shot 2020-09-13 at 3 10 18 AM](https://user-images.githubusercontent.com/59125401/93008652-e8d98a80-f56e-11ea-99d4-e4ed63b6e325.png)
3. Scroll down to **GitHub Pages**.
![Screen Shot 2020-09-13 at 3 12 40 AM](https://user-images.githubusercontent.com/59125401/93008666-09094980-f56f-11ea-923e-2067c20f68e2.png)
4. Click the dropdown menu set to **None** in the **Source** box.
![Screen Shot 2020-09-13 at 3 14 20 AM](https://user-images.githubusercontent.com/59125401/93008693-6dc4a400-f56f-11ea-880f-04ebf6be5289.png)
5. Select **master**.<br />
![Screen Shot 2020-09-13 at 3 16 04 AM](https://user-images.githubusercontent.com/59125401/93008706-9ba9e880-f56f-11ea-9916-c89f2b01752b.png)<br />
6. Save your changes.
7. Once saved, you will see a message with the link to your website.
![Screen Shot 2020-09-13 at 3 18 01 AM](https://user-images.githubusercontent.com/59125401/93008716-ce53e100-f56f-11ea-90fc-cfa92c0cc74a.png)