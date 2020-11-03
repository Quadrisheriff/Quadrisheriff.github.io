---
title:  Deploying your Jekyll website on Netlify.
summary: Deploy your Jekyll website with Netlify.
authors:
    - Quadri Sheriff 
---

This tutorial explains how to deploy and manage your `Jekyll` websites with Netlify. 

[Netlify](https://www.netlify.com/) is a cloud computing platform that allows you to publish all your web projects for free. 

To deploy your `Jekyll` website on Netlify, first you have to deploy your website's directory into a git repository manager(GitHub, GitLab,or Bitbucket), then coonect the repository to Netlify from the git repository manager.

###**Prerequisites**

This guide assumes that you have: 

- A ready to deploy Jekyll website - you can check out our [Jekyll quickstart tutorial](/Static%20site%20generators/Jekyll/Jekyll-quickstart/) for details on how to set up a documentation website with `Jekyll`.
- Git installed locally and GitHub account - visit [product.hubspot.com](https://product.hubspot.com/blog/git-and-github-tutorial-for-beginners) for instructions on how to setup Git and GitHub.
- Netlify account - visit [nelify.com](https://www.netlify.com/) to set up your free Netlfiy account.

###**Deploying your project to GitHub**

To deploy your website on GitHub:

1. Create a new GitHub repository for your project - git@github.com:Quadrisheriff/jekyll-project.git.
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

###**Deploying your website on Netlify from GitHub**

To deploy your website to Netlify from your GitHub repository:

1. From your Netlify dashboard, select **New site from Git**. ![Screen Shot 2020-08-27 at 1 12 56 AM](https://user-images.githubusercontent.com/59125401/91369162-f8cd3c80-e802-11ea-928b-ce876f4249cd.png)
2. Click **GitHub**. ![Screen Shot 2020-08-22 at 9 38 57 PM](https://user-images.githubusercontent.com/59125401/91368638-8ad44580-e801-11ea-8946-9a427a099dab.png)
3. Walk through the processes involved in linking your GitHub account with Netlify. ![Screen Shot 2020-08-22 at 9 39 31 PM](https://user-images.githubusercontent.com/59125401/91368722-ba834d80-e801-11ea-8396-e27a2d796361.png)
4. Select your website's repository from all the listed repositories. ![Screen Shot 2020-08-27 at 11 31 07 PM](https://user-images.githubusercontent.com/59125401/91505637-f41e8c00-e8c7-11ea-8e3b-8830dce0fd5b.png)
5. Click **Deploy site** to deploy your webste on Netlify ![Screen Shot 2020-09-13 at 3 45 30 AM](https://user-images.githubusercontent.com/59125401/93009038-c72ed200-f573-11ea-83c4-35c4d26b6934.png)
6. Once deployed, a preview link will be generated and displayed on your Netlify dashboard.
![Screen Shot 2020-09-13 at 4 00 32 AM](https://user-images.githubusercontent.com/59125401/93009215-cc8d1c00-f575-11ea-97bd-9c4afdbd83d8.png)
