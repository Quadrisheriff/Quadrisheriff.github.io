---
title:  Deploying your Hugo website on Netlify.
summary: Deploy your Hugo website with Netlify.
authors:
    - Quadri Sheriff 
---
# Work in progress

This tutorial explains how to deploy your Hugo websites on Netlify. [Netlify](https://www.netlify.com/) is a cloud computing platform that allows you to deploy all your web projects for free. Netlify offers some cool features like CDN, continous integration, admin GUI that enables you to better manage your web projects.

This guide include steps about adding Netlify configuration files, deploying your website's repository to GitHub, and finally deploying your website to Nelitfy directly from GitHub.

###**Prerequisites**

This guide assumes that you have:

- A ready to deploy Hugo website - you can check out our [Hugo quickstart tutorial](/Static%20site%20generators/Hugo/Hugo-quickstart/) for details on how to set up a documentation website with Jekyll. 
- `git` installed locally and GitHub account - visit [product.hubspot.com](https://product.hubspot.com/blog/git-and-github-tutorial-for-beginners) for instructions on how to setup `git` and GitHub.
- Netlify account - visit [nelify.com](https://www.netlify.com/) to set up your free Netlfiy account.

---

###**Adding Netlify configuration files**
1. Create a `netlify.toml` file in your website's root directory.
```
touch netlify.toml
```
2. Add the following configuration into the `netlify.toml` file.
```
[build]
publish = "public"
command = "hugo --gc --minify"

[context.production.environment]
HUGO_VERSION = "0.74.3"
HUGO_ENV = "production"
HUGO_ENABLEGITINFO = "true"
```

###**Deploying your project to GitHub**

To deploy your website on netlify, you have to deploy your project into a git repository manager(GitHub, GitLab or Bitbucket), and then deploy directly to Netlify from the git repository manager.

Follow these instructions to deploy your Hugo website to GitHub.

1. Create a GitHub repository for your website - git@github.com:Quadrisheriff/hugo-project.git.
2. Initialize your website directory with `git`.
```bash
git init
```
3. Add your repository as the remote origin.
```bash
git remote add origin git@github.com:Quadrisheriff/hugo-project.git
```
4. Verify your remote origin.
```
$ git remote -v
origin	git@github.com:Quadrisheriff/hugo-project.git (fetch)
origin	git@github.com:Quadrisheriff/hugo-project.git (push)
```
5. Add your new changes to `git`.
```bash
git add .
```
6. Commit your changes.
```
git commit -m 'hugo-project'
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
5. Click **Deploy site** to deploy your webste on netlify ![Screen Shot 2020-08-27 at 11 31 58 PM](https://user-images.githubusercontent.com/59125401/91505740-3e077200-e8c8-11ea-951c-32cd60086b69.png)

Once deployed, your website's details and a preview link will be added to your Netlify dashboard.