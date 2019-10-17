---
layout: post
title:      "Final Project and React Components"
date:       2019-10-17 00:26:23 +0000
permalink:  final_project_and_react_components
---


Well everyone, I did it. I've officially completed my final project and survived Flatiron School's Full Time Software Engineering boot camp.

![](https://media.giphy.com/media/l4JySAWfMaY7w88sU/giphy.gif)

The experience was a five month, mentally and physically taxing whirlwind that was equal parts stressful and rewarding. There were highs and lows, triumphs and defeats, but through it all I was determined to keep moving forward no matter how arduous the journey became. I'm beyond proud of myself for all that I have accomplished throughout this process and I'm excited to start my career as a Full Stack Web Developer. 

![](https://foolishwatcher.files.wordpress.com/2017/07/im-ready-game-of-thrones.gif?w=540)

Enough with the feels, let's talk projects. For our final project, the guidelines were pretty open-ended and just instructed us to use all that we've learned throughout the course to demonstrate an understanding of each of the languages, frameworks, and libraries we were taught. 

I decided to build upon my vanilla Javascript project, Grow To Go. Grow To Go is a mock ecommerce site that allows customers to find the perfect houseplant that fits their lifestyle and capabilities. To meet the guidelines of the project, I completely revamped Grow To Go, converting it into a React and Redux application and adding a couple dozen plants to the inventory in the process. I also added several new features to my app, including a search bar that automatically renders any plant whose name includes the user's input, a filter option for houseplants that are non-toxic or "pet friendly", and individual show pages that include additional information for each houseplant. 

### React Components


For those that don't know, React is a Javascript library for building user interfaces. React uses a combination of components, state, props, and JSX, a seemingly unholy combination of vanilla Javascript and HTML.

Components are the most fundamental part of React and each are responsible for describing and constructing a piece of one's React UI. Components can either be written as classes or functions depending on their use.  If a component does not use state or need access to the lifecycle methods that class components provide, then it should be written as a function. Functional components do not have access to state or lifecycle methods, but they provide user's with simplicity and a small performance boost over their class brethren. 

Components can be further organized into two different categories, "dumb" or presentational components and "smart" or container components.  

Container components are concerned with how things work and are responsible for providing the data and subsequent behavior to presentational components. I won't get too much into Redux here, but container components are typically generated through the use of a higher order component called `connect()` and communicate with the Redux store through `mapStateToProps` and `mapDispatchToProps`. I used two container components, PlantContainer and CartPlantContainer in my project which were responsible for passing information down to the subsequent presentational components. 

Presentational components, as their name suggests, are typically concerned with presenting content and how things look. These components receive props and utilize them to display content but do not typically deal with state or have a lot of added logic in them. I used several presentational components in my final project, the most important being my Plant, Plant Show, and Cart Plant components. These components take the props passed down from their respective container components and render the data to the DOM. 

There are no hard and fast rules for container and presentational components. They are meant solely to aid in the organization (and debugging!) of a React and Redux project through a separation of concerns. 

![](https://media.giphy.com/media/8gJ28HfjAkc9y/giphy.gif)

If you're not sure whether a component should be a class or functional component, then feel free to make all of your components class components. And if your project doesn't incorporate container or presentational components, don't sweat it. As long as your code is organized in a way that works for you, and is easily understandable to other programmers, then you're good to go.  Happy coding!


