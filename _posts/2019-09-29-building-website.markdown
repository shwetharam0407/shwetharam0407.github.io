---
layout: post
title:  Building a Website with Jekyll al-folio theme and Hosting on GitHub Pages
date:   2019-09-29 22:00:00
description: A short summary of procedure followed and some lessons learnt while building this website
comments: true
---
Building this website was more trouble than it should have been- took me a whole three day weekend to build this and another blog! To be fair, I was completely new to Jekyll and GitHub Pages, my HTML and CSS were also very rusty. All the same, I think it would have been much easier if I had found everything in one place so naturally, that's my first blog post here. While I don't have the time to write a very detailed post, I'll try to document the procedure I finally followed in enough detail, so someone can follow along.


### Installation on a macOS Mojave
I found these resources useful and managed to get stuff done without needing sudo everywhere.

[https://jekyllrb.com/docs/installation/macos/](https://jekyllrb.com/docs/installation/macos/)  

[Install Jekyll on macOS Mojave](https://desiredpersona.com/install-jekyll-on-macos/)


### Two Options - Build locally or let gh-pages do it
1. You can upload your website's source files into a github repo and let gh-pages build it for you. These [video walkthroughs](https://jekyllrb.com/tutorials/video-walkthroughs/) from Giraffe Academy can walk you through the process. I did this for [My Music Corner](https://shwetharam0407.github.io/music-corner/)

2. GitHub pages don't support many custom ruby plugins because of security concerns. If you need one of these (jekyll-scholar in my case), deploying your source on gh-pages is not an option. A work around is to build your website locally and only upload the build (contents of _site folder) to a github repo. You can, of course,  keep the source in a separate branch or a different repo. This is the process I followed for this website.


I want to have both code and build in the same repo, so I have them on different branches. source branch has all the code, master is the deployment branch.

#### 1. Fork theme ([al-folio](https://github.com/alshedivat/al-folio) in my case) and clone it.

#### 2. In the folder, delete the .git folder 

    cd al-folio/
    
    rm -r .git 
    
#### 3. Initialize a new empty repo

    git init

#### 4. Add some files common to both branches.

    git add README.md .gitignore
    
    git commit -m "initial commit"
 
#### 5. Create a repo on github called github_username.github.io
 
#### 6. Set the github repo as your remote and push to master branch
    
    git remote add origin https://github.com/github_username/github_username.github.io.git
    
    git push --set-upstream origin master
 
#### 7. Create a source branch and add the source files and push them to source branch in remote repo

    git checkout -b source
    git add .
    git commit -m "adding source files cloned from theme al-folio"
    git push origin source
  
#### 8. Set the baseurl field in _config.yml to be an empty string as recommended for user webpages


#### 9. Build and serve your site locally

I ran into this error:

    bundle exec jekyll serve

    jekyll 3.8.5 | Error:  superclass must be a Class (Faraday::DeprecatedConstant given). 

Fixed this by forcing an older version of faraday gem by adding this line to Gemfile

    gem 'faraday', "< 0.16" 

Run 

    bundle update faraday

bundle exec jekyll serve worked after the fix. You can view the built website at localhost.

#### 10. Deploying to gh-pages

If you upload the contents of _site folder now to gh-pages, you will find that links are broken and styles are missing. This is because, when you run bundle exec jekyll serve, Jekyll embeds localhost in the paths of the built HTML files. 

For deployment, run

    bundle exec jekyll build
    
Here, I came across this warning:

    GitHub Metadata: site.name is set in _config.yml, but many plugins and themes expect site.title to be used instead. To avoid potential inconsistency, Jekyll GitHub Metadata will not set site.title to the repository's name.
    
I added a site.title field to my _config.yml to get around this.

Also note that Jekyll generates relative paths that require an active server to resolve them. If you simply open the built HTML files in a browser, you will find that the paths are not resolved and as a result, links are broken and styles are missing.

#### 11. Check out master branch and add contents of the built site
   
    git checkout master

Copy contents of the _site folder to the root folder of your website. I found it useful to have _site folder in my .gitignore.

    git add .
    git commit -m "build <commit hash>" 

I use this <commit hash> to keep track of which build corresponds to which commit in the source branch

    git push
    
Your website should be up and running on https://github_username.github.io, sometimes it takes a few minutes.
    
### It's time to start customizing your website now!
