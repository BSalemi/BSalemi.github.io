---
layout: post
title:      "Rails Portfolio Project and Using Scope Methods"
date:       2019-08-11 22:42:23 +0000
permalink:  rails_portfolio_project_and_using_scope_methods
---


Hear ye, hear ye.

I've come to announce that I have completed my third portfolio project here at Flatiron. For the third module, I was tasked with building a complete Ruby on Rails application that manages related data through complex forms and RESTful routes. Much like the second module, this module's project called for building a CMS (Content Management System), this time using Rails instead of Sinatra. 

![](https://i.imgur.com/LTvlYSU.gif)

Oh, what's that? You'd like to hear about my project? Well if you insist...

For my Rails portfolio project, I created an app called Vie Games which built upon the video game CMS I made last module. Vie Games gives users the ability to connect with other gamers through gaming events and tournaments, both online and in-person. In addition to all of my previous project's features, I added the ability for users to create, host, join, and keep track of various events for the video games they own. This new functionality was achieved through two new models, Event and UserEvent, as well as several other methods that enhance user experience. 

One of the requirements for this module's project was to incorporate the use of a scope method. A whosawhat now? I know what a method is and what scope is in Ruby, but I had never heard of a **scope method** before.

![](https://media.giphy.com/media/3RLgFrb0uGsYU/giphy.gif)

*My brain whenever I encounter something I don't know.*

#### Scope Methods

A scope method is a class method that is used to retrieve or query objects from a database. Scope methods allow you to specify commonly-used queries such as `where`, `select`, and `includes()` to pull specific instances of objects from your database. 

I used two scope methods within my Event model, one that locates online events and one that locates in-person events. 

```
class Event < ApplicationRecord
    scope :online, -> { where(location: "Online") }
    scope :in_person, -> { where(location: "In Person")}
end 
```

This is exactly the same as defining two class methods:

```
class Event < ApplicationRecord 

	def self.online
		where(location: "Online")
	end

	def self.in_person
		where(location: "In Person")
	end  
end 
```

You can use either format to write the query, though I prefer the syntactic sugar of the first one. Why use three lines to write code when it can be achieved with just one?

![](https://media.giphy.com/media/l378bl7lVJ1XAMRFu/giphy.gif)

Each scope method will return an ActiveRecord::Relation object which allows for the chaining of other methods or queries to further dive into your database. 

```
class Event < ApplicationRecord 
    scope :free, -> {where(" entrance_fee = 0")}
end 

Event.online.free # => [ All events that are online and free]
```

Scope methods are also chainable within scopes. This means the above query could be achieved through the creation of a chained scope method. 

```
class Event < ApplicationRecord 
  scope :online, -> { where(location: "Online") }
  scope :online_and_free, -> {online.where(" entrance_fee = 0")}
end 

Event.online_and_free #=>[All events that are online and free]

```

Easy, right?

In conclusion, scopes are a great choice if you're looking to grab specific objects out of your database. The syntactic sugar and chainable quality of these methods make querying a database easier than ever. 
