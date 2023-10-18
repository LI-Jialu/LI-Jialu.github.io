---
layout: post
title: Jekyll & GitHub Pages Crafting Step by Step
date: 2023-09-23 20:08:02 +/-5000
categories: [Web Dev, Front-end Dev]
tags: [jekyll, github page]     # TAG names should always be lowercase
---

# Using jekyll to create blog 
<!-- 
## Requirements 
- Directly generate page from Markdown files 
- SEO-friendly 
- Easy to use 

## Framework 
| Framework | Description | 
|- | -| 
| Astro | Demos: https://github.com/flexdinesh/blogster  | 
| Next.js | | 
| Nuxt.js | |  -->


## Installation 
- Install `Ruby` by download from `https://rubyinstaller.org/downloads/`

- Check by `ruby -v` 
`RubyGems` is automatically installed 
Check by `gem -v` 

- Install `Make`: 
From here https://gnuwin32.sourceforge.net/packages/make.html 
Then download the setup file.  
Add `C:\Program Files (x86)\GnuWin32\bin` to PATH.  

- Install `Jekyll` by `gem install jekyll bundler` 
Check by `jekyll -v` 

## Deploy the tempalte locally 
- click `use the tempalte` button on the GitHub page 
- run `bundle exec jekyll s` in the command line on local machine 
- you should see the page running succeesfully on localhost 

## Editing 
- Create a new post by: create a new markdown file in the `_posts` folder following the pattern of `YYYY-MM-DD-title.md`
- Insert a hyperlink of websites or pages follow the following pratices: 

<!-- ```
[Local file link]({% post_url 2023-09-01-python_data_structure %})

[Link to a post]({{ site.baseurl }}{% link _posts/2023-09-01-python_data_structure.md %})

[Link to a pdf]({{ site.baseurl }}{% link pdf/resume.pdf %})

[google](https://www.google.com)
``` -->

<!-- ## Modification based on template
- change the favicon 

## Notes 
- Jekyll does not render the markdown correctly, solution: 
-  -->