---
layout: post
title:      "Metaprogramming and Macros "
date:       2019-08-04 19:48:58 -0400
permalink:  metaprogramming_and_macros
---


Hello everyone. Tomorrow begins Module 3's project week, which means that I am officially past the halfway point of this program. 

These past twelve weeks have been a whirlwind for me. Although I'm not sure if these last three months have flown by or dragged on, I am proud of how much I've accomplished thus far and am excited to continue learning. 

![](https://media.giphy.com/media/Phv08kX42gDHq/giphy.gif)

Our third module and project is the last of our Ruby lessons and is centered on Rails. Rails is a MVC framework similar to the DSL Sinatra of Module 2 but with far more features to create databases, web services, and web pages with ease. 

Throughout Ruby, and especially within Rails, we use programming techniques known as metaprogramming and macros to provide lots of functionality with very little code. As Rails emphasizes the practice of DRY (Don't Repeat Yourself) you can imagine the importance of techniques that provide clean, succinct, and functional code for your projects. 

## What is Metaprogramming?

Metaprogramming is the process of writing of code that knows about and can operate on other code. This means that metaprogramming allows programs to create methods or manipulate code at runtime instead of having to define them in the program itself.

A common usage of metaprogramming is through the macros of `attr_reader`, `attr_writer`, and `attr_accessor` in Object Orientation. Wait a minute. Attr_what? Attr_who? What's a macro? 

![](https://media.giphy.com/media/UeTTJbrcJy3io/giphy.gif)


## What is a Macro?

A macro is a class method that creates and returns new instance methods. Since a macro is code that returns more Ruby code instead of a Ruby datatype, it is considered a type of metaprogramming. 

In object-oriented Ruby, one way macros are used is to abstract away the explicit defining of setter and getter methods of a Ruby class's attributes. 

For example, when creating a User class you may give each instance a `username` attribute and an `email` attribute. Per Ruby conventions, that would mean that your User class would need a getter method and a setter method for both attributes. 

```
class User 

    def username=(username)
	 @username = username 
    end 

    def user 
	 @user
    end 

    def email=(email)
	 @email = email 
    end 

    def email
	 @email 
    end 

end 

```

Having to repeat this pattern of manually creating a setter and getter method for each of your class's attributes seems tedious and inefficient. Thankfully, the macros `attr_reader`, `attr_writer`, and `attr_accessor` take care of that repitition for us. 

Just writing the name of the macro followed by the attribute name (`attr_reader :username ` and `attr_writer :username`) will create the necessary getter and setter methods. 

So, writing this..

```
class User 

attr_reader :username
attr_writer :username

end 
```

..will create this.

```
class User

def username=(username)
 @username = username
end 

def username
 @username
end 

end 
```

## attr_accessor 

Ruby simplifies this one step further through the use of the `attr_accessor` macro. The `attr_accessor` macro creates BOTH the setter and getter method which means that we can achieve the same results of the code above by writing just `attr_accessor :username` in place of the `attr_reader` and` attr_writer` macros. 

These macros allow you to define setter and getter methods for multiple attributes, too, just by following the same syntax of `:attribute` separated by commas.

```
class User

attr_accessor :username, :email

end 
```

The code above will create the necessary setter and getter methods for both `username` and `email`. 


How simple is that?  

![](https://media.tenor.co/images/7f6402cf7df54cdf24505ee7895326aa/raw)

Macros are found throughout Ruby and are often times used to make code more palatable. 

Other common examples of macros include the Active Record associations methods (`has_one`, `has_many`, `belongs_to`, etc.) which each create several methods that express relationships between objects,  as well as the ` resources`  macro in Rails which creates the seven RESTful routes for a controller in an MVC. 

Metaprogramming and macros make our lives as programmers easier by abstracting away any unnecessary repetition, allowing us to achieve more functionality with fewer lines of code. Although metaprogramming and macros may seem a bit confusing (and at times they are), the benefits we as programmers receive from utilizing them are immeasurable. 

