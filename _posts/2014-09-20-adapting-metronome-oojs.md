---
layout: post
title:  "Adapting Chris Wilson's Metronome for my Drum Machine App"
date:   2014-09-20 17:03:20
categories: music-tech
---

I've been working on a simple drum machine in the browser for several weeks. I'm really excited about this app for several reasons: the entry point for working with the Web Audio API, the chance to hand roll a front end MVC stucture, attempting to style a vintage feeling drum machine.... 
AND - I'll likely explore each of these elements in greater depth soon. 

But in building a drum machine, I quickly realized that using Javascript's setTimeout method would be very lacking for scheduling audio. Javascript in the browser is built to FEEL asynchronous. Check out [this article](http://ejohn.org/blog/how-javascript-timers-work/). The browser's API is constantly assessing JS function calls, and asking 'do I have the resources to do this now?'. Callbacks can be deferred for processes that demand lots of resources. 

So - when I need a dependable down beat in a music app, if I exclusively depend on JS timers, I will inevitably get dropped beats, and musical hiccups. 
Not so cool. 

LUCKILY - 
In the nonstop google search that seems to be my life lately, I stumbled upon the work of an awesome engineer named [Chris Wilson](http://cwilso.com/), and this [awesome article](http://www.html5rocks.com/en/tutorials/audio/scheduling/) he wrote about scheduling audio in the browser. 

Mr Wilson built a rock solid (comparatively) metronome, [with the code publically available on GitHub](https://github.com/cwilso/metronome). Wow. 

Wilson's metronome schedules audio via the clock in the Web Audio API, a clock that runs on a separate thread and is nearly as dependable as a DAW for scheduling. This feature is available in most modern browsers. NICE. The metronome works in concert with setTimeout, checking at regular intervals if the next beat is scheduled and if the tempo has changed. For more details on specs and the interaction of the setTimeout with WAAPI clock, I highly recommend Wilson's [article](http://www.html5rocks.com/en/tutorials/audio/scheduling/). 

So, with this wonderful OSS find, I am able to move forward building a musically dependable drum machine! 

But -  my design goals with the project include attempting a hand rolled Front End MVC structure, and to hold to Object Oriented Design as best as I can. Wilson's metronome, while accurate and elegant, seems more procedurally designed. And while concerns of the metronome are broken out to separate functions, I want to encapsulate responsibility in objects. 

Get ready kids, it's time to REFACTOR!!!

The metronome itself seems to belong squarely in the M camp of MVC. My goal then is to build a metronome model that is ONLY concerned with scheduling notes according to the specified tempo. No views allowed. Also I named it MetroGnome. Because its funny. And at this point, I only want to schedule samples in use in an instance of the drum machine. No synthesis. Bye Bye Oscillator. 

[Here](https://github.com/avifoxi/browser-drum-machine/blob/master/app/assets/javascripts/models/metronome.js) is my most current iteration.

Waddya think?
 




