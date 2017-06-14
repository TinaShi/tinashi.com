+++
date = "2017-06-12T19:17:00"
draft = false
categories = ["R"]
tags = ["blogdown", "Hugo", "Netlify", "website"]
title = "A short tutorial of blogdown for beginners"
math = true
summary = """
Create a beautifully simple personal or academic website for beginners. 
"""
+++

This is a tutorial for the people like me, who are building the first personal website with RStudio installed. This tutorial will explain only the necessary steps to put the static website online with blogdown + Hugo + Netlify. If you want to make it fancier or if you want to explore more, [Yihui Xie’s video] (https://www.rstudio.com/resources/webinars/introducing-blogdown/) and Yihui Xie and Amber Thomas’ book blogdown: [Creating Websites with R Markdown](https://bookdown.org/yihui/blogdown/) are great resources. My friend Josh helped me to figure out the following steps, I simply summarize it here. 

1.	[Download RStudio here](https://www.rstudio.com).
Create a new project in RStudio. File -> New Project -> New Directory -> Empty Project-> Type in Directory name and choose the working directory. Here I just use example as directory name, and create project as subdirectory of the default setting ~ (which is /Users/tinashi) -> Click “Create Project”.
2.	Install blogdown in RStudio
devtools::install_github("rstudio/blogdown")
3.	The use the following code:
library(blogdown)
blogdown::install_hugo()
blogdown::new_site()
blogdown::hugo_build()
4.	In RStudio Viewer you will see the following image
![Figure 1](/img/Picture1.png)

5.	Based on the instructions in Yihui Xie and Amber Thomas’ book blogdown: Creating Websites with R Markdown [Section 1.7 A recommended workflow] (https://bookdown.org/yihui/blogdown/workflow.html), we can deploy the website by using Netlify. 
“Log in onto https://www.netlify.com (you can use a GitHub account if you have one).”
Click “Site” after logging into netlify, we can see the following instruction:
![Figure 2](/img/Picture2.png)

6.	Since my project has path /Users/username/personal_website, we can find public folder under this directory. We right-click public folder, and choose Compress “public”. Drag public.zip to Netlify. 
7.	Now click “Sites” on Netlify again, if you see the following image (it should have a different name though), the website is deployed. 
![Figure 3](/img/Picture3.png)

8.	Click on the green name, you will see the link to the website.
![Figure 4](/img/Picture4.png)

9.	Click on the link provided by Netlify https://gunner-crocodile-33781.netlify.com, it directs to your website. 
10.	If you want to custom the domain, click “Set up domain”. Type in the domain name you have and click Save.

Comment: I purchased my domain name in google, so I go to google domains -> Manage my domains -> DNS (configure DNS) -> type in “104.198.14.52” for IPv4 address under Custom resource records -> Add. If you already have a record, you can just edit the IPv4 address. Then the domain name you have points to the website you have created with netlify.

References:  
1.	[Yihui Xie and Amber Thomas’ book blogdown](https://bookdown.org/yihui/blogdown/)    
2.	[Netlify homepage](https://www.netlify.com )   
3.	[Netlify custom domain instruction] (https://www.netlify.com/docs/custom-domains/#dns-configuration)    
4.	Friend Josh
 
   