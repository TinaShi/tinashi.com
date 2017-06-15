---
title: 'Continuous deployment: Link Netlify webpage to GitHub'
author: Tina Shi
date: '2017-06-14'
slug: continuous-deployment-link-netlify-webpage-to-github
categories: ["GitHub"]
tags: ["Netlify", "GitHub", "Continuous deployment"]
---
This tutorial is for the people who already followed "A short tutorial of blogdown for beginner" or already set up website on Netlify and want to link Netlify website with GitHub for continuous deployment. Again the procedures are developed by my friend Josh, I just summarize it here for future reference.
1.	Create a repository on your GitHub account username.github.io.
2.	Move to the directory where you project is saved. For my case, it is personal_website directory. The following commands in terminal will help us to start:  
cd personal_website/  
git init  
git remote add origin https://github.com/username/username.github.io  
3.	Create a file called .gitignore use the command line below.  
touch .gitignore
4.	Open the file just created .gitignore, I used sublime for my case and pasted the following names of the files to the file .gitignore so that the files are not pushed to GitHub:  
public/  
.DS_Store   
.Rhistory  
.Rproj.user/  
personal_website.Rproj  
public.zip  
.Rproj.user  
5.	Then in terminal I check the status of files:  
git status  
The following files are in staging area:  
.gitignore  
config.toml  
content/    
index.Rmd  
static/  
themes/  
6.	Then we add and commit the changes and push them to GitHub:  
git add .  
git commit -m 'initial commit'  
git push -u origin master  
7.	Log in to netlify account and go to “Sites”. Under your sites, click on the site you plan to link with GitHub. For this case, it is "username.github.io". ![Pic1](/img/continuous_deployment_Pic1.png)
8.	Continuous deployment -> Deploy settings -> Edit settings.
For Repository, link to a repository -> GitHub (Under “Continuous Deployment”) -> the repository “username.github.io”.
9.	Set the branch to deploy to be “master”. In “Basic build settings”, set build command to be “hugo” and publish directory to be “public”.
10.	Go to terminal and check the version of hugo installed using “hugo version”. Mine is version 0.21. So in the “Advanced build settings”, set Key to be “HUGO_VERSION” and Value to be “0.21”.
![Pic2](/img/continuous_deployment_Pic2.png)
11. Click “Deploy site”.   
Congratulations, we are done. Every time you update your information locally, once you push it GitHub, it is automatically updated on your Netlify site as well.

References:  
1. Yihui Xie and Amber Thomas’ book blogdown: Creating Websites with R Markdown [Section 3.3 GitHub pages](https://bookdown.org/yihui/blogdown/github-pages.html)  
2. [Netlify Common configuration directives](https://www.netlify.com/docs/continuous-deployment/#common-configuration-directives)  
3. Friend Josh
