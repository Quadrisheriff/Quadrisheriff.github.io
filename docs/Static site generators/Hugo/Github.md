---
title:  Publishing your Hugo website with GitHub pages. 
summary: Publish your Hugo website with GitHub pages. 
authors:

    - Quadri Sheriff 

---

###**Introduction**

In this guide you will learn how to deploy a Hugo website to GitHub, and publish the website for free with GitHub pages. 

GitHub pages is a free hosting service offered by GitHub that allows you to publish your webiste projects for free directly from your GitHub repositories. GitHub pages is available in all public GitHub repositories and GitHub free for organizations. 
 
###**Prerequisites**
This guide assumes that you have:

- A ready to deploy Hugo website - you can check out our [Hugo quickstart tutorial](/Static%20site%20generators/Hugo/Hugo-quickstart/) for details on how to set up a documentation website with Jekyll. 
- `git` installed locally and GitHub account - visit [product.hubspot.com](https://product.hubspot.com/blog/git-and-github-tutorial-for-beginners) for instructions on how to setup `git` and GitHub.

---
###**Deploying your website to GitHub**

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

###**Hosting your website on GitHub pages**

1. Create a GitHub pages repository - `<YOUR-USERNAME>`.github.io.
2. Navigate back to your website's directory.
```
cd <hugo-project-directory-name>
```
2. Link your GitHub pages repository to your original repository. 
``` bash
git submodule add -b master https://github.com/<YOUR-USERNAME>/<YOUR-USERNAME>.github.io.git public
```
3. Update your config.toml file to specify your `baseURL`. 
``` 
# Config.toml

baseURL = "<yourusername>.github.io"
```
4. Create a `deploy.sh` file in your root directory.
``` bash
touch deploy.sh
```
5. Add the following script into the `deploy.sh` file to automate your deployment. 
``` 
#!/bin/sh

# If a command fails then the deploy stops
set -e

printf "\033[0;32mDeploying updates to GitHub...\033[0m\n"

# Build the project.
hugo # if using a theme, replace with `hugo -t <YOURTHEME>` 

# Go To Public folder
cd public

# Add changes to git.
git add .

# Commit changes.
msg="rebuilding site $(date)"
if [ -n "$*" ]; then
	msg="$*"
fi
git commit -m "$msg"

# Push source and build repos.
git push origin master

```
6. Deploy your website to GitHub pages.
``` bash
./deploy.sh "commit message"
```
After deploying your website, your website will be published and hosted at <yourusername>.github.io. 

