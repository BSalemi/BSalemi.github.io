---
layout: post
title:      "Project Number Two: Sinatra Video Game Organizer"
date:       2019-07-14 21:07:25 -0400
permalink:  project_number_two_sinatra_video_game_organizer
---




My second month of boot camp has come to an end and with it my second portfolio project. I am happy to report that, unlike my first project, I did not have a meltdown three minutes into working on it (*or at all, surprisingly*). 

For my second project I was tasked with creating a CRUD, MVC (or Model View Controller) app using Sinatra, or in simpler terms, a Content Management System. After reading the guidelines for the project, I followed the same course of action as last time (*minus the freak out*), and grabbed my trusty notebook to begin jotting down my ideas. 

The guidelines suggested building our custom app to track a collection of some sort, and being a gamer, I decided to make my CMS for video games. Once I had selected a topic, I wrote down the various models I needed. The five models I used were User, Game, System, Company, and UserGame (a join model of the first two classes). Through these five models I used several associations including a has many/belongs to relationship (i.e. games belong to systems and companies and systems and companies have many games) and a many-to-many relationship between User and Game (a user can have many games, and a game can have many users). The UserGame class was created so that my database could allow a User to select which games they owned and a specific Game could keep track of how many Users own it. 

After deciding on each of my classes, their attributes, and their associations, I used the Rake gem to create the tables for each model and migrated them to my database. I also set up a seed file that I used to fill my app with dummy data so that it wouldnt be devoid of games, systems, etc., when a user first signed on. I used Nokogiri to scrape a popular gaming website and ran 'rake db:seed' to fill my database with several instances of video games and their corresponding systems and companies. 

With my database all set up, it was time to set up my controllers using RESTful routing conventions and CRUD. RESTful routing, which stands for Representational State Transfer, is a naming pattern that allows for easy data manipulation by providing mapping between HTTP verbs(like GET, POST, and DELETE) and controller CRUD (Create, Read, Update, Delete) actions. The seven RESTful routes are the foundation of just about every website that includes functionality for users to create, edit, view, and delete data. 

Using CRUD, I instilled within my app the ability to Create a new User, Read or show the User's profile, Edit the User's login information, and Delete the User's account altogether. I also used the Create and Read actions of CRUD throughout the rest of my models, allowing users to add a new Game to the database, as well as view(or Read) the index pages for all of the games, systems, and companies found within the database. Within each game's show page, I allowed to user the option to add the game to their profile to signify that they owned that game. Utilizing the join table of UserGame, this action increments the total number of players that play that particular game by one each time a User adds it to his or her profile.

After setting up all of my controllers and about two dozen view pages, I opened shotgun to test out my app. Much to my relief everything was working as intended. With my app's functionality all, well, functioning, I turned my attention to CSS to try and take my app from ugly to not-so-ugly, and this proved to be quite the headache. Having no prior experience with CSS, I taught (*using the term very loosely here*) myself some basic CSS and began to add some personality to my app. After hours of trial and error, I somehow managed to add some drop-down menus and much needed borders to my pages. Even though my app was more ugly than not-so-ugly, I was officially done with my CMS Sinatra project and was proud of all that I had accomplished.

![](https://media1.tenor.com/images/9e7871c8d23549bbcf7919fcb227bb96/tenor.gif?itemid=3438539://)
