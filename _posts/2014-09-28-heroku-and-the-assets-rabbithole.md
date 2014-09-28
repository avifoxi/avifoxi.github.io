---
layout: post
title:  "Heroku, Assets, and The AWS Rabbithole"
date:   2014-09-28 17:03:20
categories: music-tech, assets, heroku
---

I'm back from a wonderful week of vacation, and jumping back into developing, applying, and learning. And - I'm working through the kinks of deploying my [drum machine app](https://github.com/avifoxi/browser-drum-machine)! Close... but nooooot quite there yet. 

Those familiar with Heroku will be familiar with the handful of stock challenges that Heroku poses for assets. There are 2 types of static assets where a Rails app can get into trouble. Rails compiles and compresses all assets by default, but Heroku will not recompile these files when deploying later iterations. So for CSS and JS files, if you want fluid recompilation on each iteration of your app - best to add the [12factor gem](https://github.com/heroku/rails_12factor), which overrides Heroku's default and forces the server to recompile assets. Quirky, but a well documented and relatively simple fix. 

We get into more trouble with static assets that demand more storage, and are not integral to business logic of the app. Such as photos, music, and video. 

Heroku reccomends using [Amazon Web Services S3](http://aws.amazon.com/s3/) for storage. And I am learning now that configuring these 2 services to work in sync is not quite as obvious as one might hope. No surprises there, I suppose. 

A more in depth blog post is in the works - but this is a configuration brain teaser. The pieces I am juggling include using S3 to store my static music files. Then configuring a virtual machine instance (EC2) to serve these assets to my app. And ensuring security at each stage with keys and configuration. I do feel a bit like I am building a Rube Goldberb machine to make a piece of toast... but I also think that configuring this setup will be worth the investment of time in the future-- especially as I prepare for a nepotistically acquired project (thanks Dad...) building a fund raising site with social networking features. Allowing individual users to upload photos to their profile pages will likely rely on a similar configuration. And good to dive into this off the clock the first time around. OK! Now I gotta read some [docs](http://aws.amazon.com/documentation/)... 

