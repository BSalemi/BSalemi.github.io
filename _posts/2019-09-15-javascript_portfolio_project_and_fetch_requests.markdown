---
layout: post
title:      "Javascript Portfolio Project and Fetch Requests "
date:       2019-09-15 22:42:45 +0000
permalink:  javascript_portfolio_project_and_fetch_requests
---


As October draws near, I am reminded of how far I've come in my coding journey. These past four months have really flown by and it's crazy to think that I've already completed 80% of my Software Engineering bootcamp. 

For our penultimate project here at Flatiron School, we were tasked with creating a **S**ingle **P**age **A**pplication (or SPA). For our frontend we were instructed to use a combination of HTML, CSS, and Javascript, which would communicate with our backend API built with Ruby and Rails. As with my other Flatiron School projects, I wanted to pick a topic I was passionate about. As I'm obsessed with owning as many houseplants as humanly possible, I decided to create an ecommerce site where users can purchase houseplants to add to or start their own collection. 

![](http://66.media.tumblr.com/3a68b7956139c67d6703c24ab5b5a71d/tumblr_mgt3uuWLeE1ry7r58o1_500.gif)

*Actual footage of the houseplants at Home Depot whispering sweet nothings for me to take them home.*

After setting up my Rails API, the various models and controllers, and seeding my database with my site's plant inventory, it was time to `fetch()` the data and append it to the DOM.

![](https://media.tenor.co/images/383495c2d8dd5c49746c89a170dcd2b5/raw)

*No Gretchen, we're not talking about that kind of fetch.*

To understand `fetch()`, first we need to discuss what **AJAX** is. AJAX stands for Asynchronous Javascript And XML and allows browsers to render HTML and CSS initially while Javascript is running *asynchronously* in the background. AJAX sends a request for data and if successful will update the DOM without requiring the user to refresh. Since this happens asynchronously, the user is greeted with HTML and CSS in the browser and the DOM, upon a successful retrieval of data, will be updated soon after. Before AJAX, users would have to wait for *all* of the data to be processed before being shown anything, which, for web pages with a lot of data, would result in lengthy wait times ( and a lot of unhappy users). 

Now that we know the basics, we can learn about how to handle the requests made by AJAX. `Fetch()` is a function that retrieves data. For an HTTP GET request, `fetch()` only accepts one argument, the URL or route for the API. Since I created my own API using Rails, in order to grab the Plant seed data, I passed in the index route as the argument. 

```
function fetchPlants(){
    fetch(PLANTS_URL)
    .then(res => res.json())
    .then(plants => renderPlants(plants))
}
```


The`fetch()` request, being called inside my function `fetchPlants()`, returns an object known as  a Promise, which is *representative* of the data that was sent back from `PLANTS_URL`. On the following  line, the `.then()` method is called on the Promise that takes as its argument a function which receives the response as its argument. Inside that function we call and return a callback function `.json()` on the response, which converts the data into JSON.

JSON stands for Javascript Object Notation and is frequently used for transmitting data over the internet. JSON's syntax is formatted identically to the code used for creating objects in Javascrip. This allows programs to easily convert JSON data in Javascript objects. 

The newly converted JSON data is then passed to the final `.then()` function where it can be used and manipulated. The JSON data, represented by `plants` in my function, is then passed as in argument into another function `renderPlants()`. The `renderPlants(plants)` function uses the data from the `fetch()` request to populate the DOM with seed data for the plants.  


![](https://media1.tenor.com/images/e07e0ebebc7b59407986b393b8edad31/tenor.gif?itemid=7304860)

A `fetch()` request may fail for a variety of reasons, such as if a user is asking for non-existant resources or if authorization is needed to access a resource. When a `fetch()` request fails, we need a way for our program to bring the error to our attention.

![](https://media.tenor.com/images/47e1c06dff39636dd69837a6f2aa667b/tenor.gif)

*Well, no, Regina.. I'd really like to make this fetch() happen..*

To identify the errors causing our `fetch()` request to fail, we simply add the `.catch()` function to the end of our request.
 
 `.catch( error => console.error('error:', error)`

Through `.catch()` we can "catch" the errors and log them to the console. Once an error is indentified, we can fix what is needed to like totally make fetch happen. 

![](https://media.giphy.com/media/xT9KVF4zNt70nyNpi8/giphy.gif)

