---
layout: post
title: Jekyll Website Setup
---

# How did I create this website?

As I learn how to format markdown code, I figure the best way to do so is to begin writing posts. I see no better way to do that than by starting off with how I went about creating this website. 

## GitHub Pages

GitHub Pages is a free website hosting service provided by GitHub with every GitHub account. With GitHub Pages, you have to either type out the HTML and CSS for a static site or use Jekyll to generate it for you. As this website was to be a blog, and Jekyll is oriented toward blogs and integrates natively with GitHub Pages, it was an easy decision to go with Jekyll.

You can easily create a static site by creating a new GitHub repo titled "%username%.github.io", filling in your GitHub username. This will be your default GitHub Pages site, and you can add any HTML and CSS code to it as you would like. I did not do this, as I wanted to use the Dark Poole theme for the website.

## Jekyll

Jekyll is a static site generator written in Ruby. There are numerous other static site generators out there, but Jekyll is the one used by GitHub pages, so it can be used directly without having to manually regenerate the static cite with every change. I installed Jekyll using Linux, as that is what is recommended. If you would like to try to use it on Windows, the instructions to do so can be found on the [Jekyll Website](https://jekyllrb.com/docs/installation/windows/). 

To install Jekyll on Linux (Pop OS) to run the site locally:

1. Install Dependencies
```
sudo apt install ruby-full build-essential zlib1g-dev
```
2. Install Jekyll
```
sudo gem install jekyll bundler jekyll-gist jekyll-paginate jekyll-seo-tag jekyll-redirect-from
```
3. View the Site Locally - navigate to the main directory of the repo
```
jekyll serve
```
NOTE: It recommends setting up a gem directory and not installing them as root \[[src](https://jekyllrb.com/docs/installation/ubuntu/)\]; however, this caused a lot of issues in my case, so I installed it as root anyways. Additionally, I use jekyll-redirect-from for my Resume button, but it is not required for the default Dark-Poole installation.

## Dark Poole

[Dark Poole](https://github.com/andrewhwanpark/dark-poole) is a modified version of the [Poole](https://github.com/poole/poole) theme for Jekyll. I liked this theme and the [Lanyon](https://lanyon.getpoole.com/) theme as well. I stumbled across a dark version of Poole before I had installed either of the two and liked it the best, so that is what I ultimately went with. These themes have the entire website already setup for you, so you simply fork the repository and start writing.

# Setting up the website

These are the steps I took to setup the website:
1. Fork the original [Dark Pool](https://github.com/andrewhwanpark/dark-poole) repository by clicking the fork button at the top right.
2. Rename the repo to "%username%.github.io" by clicking Settings and editing the name under Repository Name at the top.
3. Switch the default branch to gh-pages by clicking Settings > Branches and changing the default branch. You can delete the other branches now if you would like.
4. Edit "\_config.yml"
   - Change url to "http://%username%.github.io%
   - Change baseurl to ""
   - Remove "/dark-poole" from the Blog and About urls at the bottom
   - Change Author information and Title to what you would like 

From there, you can change the website and add/remove posts however you would like. You can change the About and Archive pages by editing the respective markdown file in the main directory. To add a post to the website, go into the "\_posts/" folder and create a new file using the format "yyyy-mm-dd-title.md". Then, add the following text to the top of the file:
```
---
layout: post
title: Jekyll Website Setup
---
```
This is called the [Front Matter](https://jekyllrb.com/docs/front-matter/) and tells Jekyll the layout it use and the title it should use.

That's it! There is plenty more you can do with Jekyll to customize the website more to your liking, but that enough to get the website setup and ready to start blogging.
