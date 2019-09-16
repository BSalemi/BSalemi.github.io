---
layout: post
title:      "Project Number One: National Park CLI"
date:       2019-06-10 00:43:48 -0400
permalink:  project_number_one_national_park_cli
---


#### **ATTENTION EVERYBODY: **

I made it through the first month of Flatiron School’s Online Software Engineering Boot Camp, which means that I managed to create my first CLI project!

After an initial (near) mental breakdown and several hours of not knowing why my code was breaking, I finally completed my National Park CLI using Object Orientation and other essential Ruby concepts. Being still relatively new to coding, this first project was incredibly overwhelming to me in the beginning. In order to make it seem less daunting, I decided to approach the project one step at a time. 

***Step Zero(Programmers start at zero): Freak Out***

And boy, *did I*.

At the start of project week I was a mess. I was full of anxiety and self-doubt. Am I really cut out for this? Did I make the right decision signing up for this boot camp? What’s a Ruby? 

![](https://media.giphy.com/media/P4133zeloooHm/giphy.gif)

A few deep breaths and several video lectures later, I began to feel less overwhelmed by the complexity of my first big coding project.  I reminded myself that it was still early on in my coding journey and my anxiousness regarding the project was normal. I knew that approaching this project systematically was the best approach, so I opened my notebook and began to jot down some ideas. 

***Step One: Pick a Topic***

As the guidelines for the project were pretty open-ended, I wanted to pick a topic I was passionate about as to inspire me.  Since I’ve always enjoyed being outside, especially walking in the woods or going on hikes (I’m from NH after all), I decided to make my CLI project based on national parks. 

Since the concept of scraping was going to be at the center of my project, I knew I had to find a suitable website to glean information from.  Luckily for me, I had perused the U.S. National Park Service website once or twice (or ten times) before while compiling my bucket list of national parks and knew it would be the perfect site for this project.

![](https://thenextissuepodcast.files.wordpress.com/2017/06/tumblr_opnoems9gq1vnaib7o1_400.gif?w=452&h=360&zoom=2)

***Step Two: Outline***

After having a meltdown, watching some video lectures, and picking a topic I was passionate about, it was now time for me to start outlining my project in its barest form. 

First, I wrote out the classes my CLI project would have: a CLI class which contained any method responsible for interacting with the user as well as #run, responsible for running the CLI as a whole, a Scraper class which held the two scraper methods that pull information from multiple URLs to populate instances of the remaining two classes, my “has many” and “belongs to” State and Park classes.

***Step Three: Flesh and Test***

After outlining my whole project, I began to flesh out each new Class with attributes and methods to add functionality. I used Nokogiri to parse HTML for each state and the parks within, including each park’s name, location, type, and bio. 
Once I had the core of my project fleshed out, I began to test how it ran. All was well at first. 

The CLI printed a list of all states and U.S. territories that had national parks, and then prompted the user to enter the abbreviation of the state or territory whose list of parks they would like to see.  Things continued to go off without a hitch, it all seemed too easy.

![](http://giphygifs.s3.amazonaws.com/media/ANbD1CCdA3iI8/giphy.gif)

When it came time to enter a state abbreviation I was ready to see a list of that state’s national parks output back to me, but instead I saw “undefined method `text' for nil:NilClass". My first thought was to immediately panic. What did I do wrong? Why were my variables returning ‘nil’ as a value?  

So I slapped a Pry on the method and line in question and dove into a debugging session. I checked each of my variables against .nil? and they all returned false. What did this mean? How could my variables be both ‘nil’ and not ‘nil’ at the same time?

![](http://giphygifs.s3.amazonaws.com/media/FRRK3vMJ4no52/giphy.gif)

Luckily before I spiraled (too) out of control, my professor’s office hours began and I was able to troubleshoot the issue with him. Turns out I needed to use a ternary operator to check each variable against .nil? and set it equal to the parsed HTML. 

After that issue was figured out, it was relatively smooth sailing through to the end. A couple of while loops, some minor refactoring, and a handful of tests later; my National Park CLI project was complete and I had officially taken my first real step towards becoming a Programmer. 

![](https://media1.tenor.com/images/967b2c08758615868bb0a67c41a8f6fa/tenor.gif?itemid=4435000 )




