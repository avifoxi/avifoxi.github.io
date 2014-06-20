---
layout: post
title:  "Bourbon Based Cocktails"
date:   2014-06-17 14:12:22
categories: technical design
---

In my [last installment](http://avifoxi.github.io/legacy/unit1_projects/sassy_bartender/index.html) of my technical blog, I described how to install and configure some wonderful design tools:
 
I described how Sass functions in my last blog post. 

The Thoughtbot suite of tools are built to exploit Sass' built in funcionality and give us as designers a set of tools at our fingertips that we will not have to re-define with _every_ new project. Thanks!

#### [**Bourbon**](http://bourbon.io/)

Bourbon is a set of Sass mixins that have been expertly predefined for us, that we can import when we choose into our .scss file. 
When you install Bourbon on a project, you have access to ALL these mixins which you can use as you see fit. 
But nothing extra is added to your CSS files until you @include a specific mixin. 
Some examples of cool mixins you'll like? 

```
@include clearfix; 
```

This single line of code in your .scss file is translated by Sass to several lines of code in the file you've set a link between 
```sass --watch style.scss:style.css```
The Bourbon mixin specifies a multiline clearfix with cross browser compatibility. COOL!

Similarly useful ```@include```s include 'outer-container', 'span-columns', 'shift(_specified-num-of-columns_)'.

I've only just begun to explore what is possible with Bourbon. And there is SO much they've included, its really astounding. But pre-mixed animations, columns, alignment tools... NICE. 

Explore them all on the [Bourbon Docs](http://bourbon.io/docs/) page. 

#### [**Neat**.](http://neat.bourbon.io/)

Neat is an easily modifiable grid system built using the mixins defined in Bourbon. They're a powerful duo! 

Neat is pre-engineered to be responsive - so we can jump straight into using them, and know that the grid will hold up accross multiple platfoms. 

Particularly useful is a circus-tent-looking grid overlay that you can enable or disable on any page that you're designing. Very cool - the toggle is in Neat's settings folder, the  ```_visual-grid.scss``` file. Open the file up in your text editor and toggle line 1 between true or false to see a nice grid overlay. 

Check out the [Neat Docs](http://neat.bourbon.io/docs/), and the awesomely laid out [Examples](http://neat.bourbon.io/examples/) page. 

#### [**Bitters**](http://bitters.bourbon.io/)

Is Bitters cheating? 
Who cares. 

It's awesome. 
If you include Bitters on your project, it imports a nicely styled set of defaults for you to love, and easily manipulate. 

If you're styling a project with Bitters, the first file you should visit is your ```_variables.scss``` file within Bitters' mixins directory. 

Within this file, you can quickly manipulate the global fonts, colors, and typography for the project. And virtually everthing is modifiable within the pretty set of folders which you should not be afraid to explore and change as you see fit.  


#### [**Refills**](http://refills.bourbon.io/)

Refills is definitely cheating. 
No two ways about it. 

Refills are prefab pieces of code that implement pretty elements into your page ready to go. 
So so cool - and easy peasy from the get go. ALTHOUGH - I had a harder time manipulating these fully assembled pieces. It's more likely that more experienced designer would have no problem. 
But again - the code is right there for you to futz with should you so choose. 

And that's all for now.
Hurray Weekend Before DBC!!







