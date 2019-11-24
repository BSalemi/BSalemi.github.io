---
layout: post
title:      "Arrow Functions "
date:       2019-11-24 17:10:52 -0500
permalink:  arrow_functions
---


Arrow functions, introduced in ES6, are a shorter and often times more readable way to write  functions in JavaScript.  In addition to the aesthetic changes, there are a few key differences between arrow functions and regular functions. 

Before ES6, functions were declared like so:

```
const sayHello = function(){
	return "Hello there!"
};

sayHello() // "Hello there!"
```

But with arrow functions, the above code could also be written like this:

```
const sayHello = () => {
	return "Hello there!"
};
```

As you can see, arrow functions don't use the word "function" at all and instead are represented by an arrow "=>", separating the parameter(s) from the function body. 

The arrow function's parameters go inside the parentheses, as with normal JavaScript functions. However with arrow functions you can further do away with unnecessary keystrokes, because if your function has only one parameter, then the parentheses surrounding it can be omitted. 

```
const helloThere = name => {
	return "Hello there, " + name
	};

helloThere("Brian!") // "Hello there, Brian!"
```

Another unique trait of JavaScript arrow functions is that they give implicit returns under some circumstances. For instance, if the arrow function has a concise body, when only an expression is specified (*Think: one-line-manipulation of arguments*), then the expression's value is implicitly returned. 

```
const square = x => x * x;

square(3) // 9
```


However, if an arrow function has a block body, an explicit return statement must be used. As a refresher, a block statement is defined as "used to group zero or more statements" and are "delimited by a pair of curly brackets". 

```
const multiply = (x, y) => { x * y };

multiply(3,2); // undefined 
```

The return value is `undefined` because the function body is wrapped in a block; thus an explicit return is necessary.
     
```
const multiply = (x, y) => {
	return x * y 
};
 
 multiply(3,2); // 6


Note: This function could also be written on one line and use an implicit return like a couple of examples ago. But I wanted to provide an example where an explicit return is necessary, even for a one-line-manipulation of arguments.
```

Another divergence from regular functions, and probably the biggest, is that with arrow functions there is no binding of `this`. Click [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this) for a crash course on `this`. 

In regular functions `this` represents the object that called the function but in arrow functions, `this`represents the object that defined the arrow function.  Here's an example to make this concept a little clearer.

```
const hi = function(){
  console.log(this)
};

// A button object calls the function:
document.getElementById("btn").addEventListener("click", hi)

```

Each time the button is clicked, the event listener will call the function `hi` and the button element will be logged to the console. This is because `this` in a regular function represents the object (`button`)  that called the function (`hi()`).

Now let's look at the same code except `hi()` is an arrow function: 

```
const hi = () => {
 console.log(this)
}

// A button object calls the function:
document.getElementById("btn").addEventListener("click", hi)

```

This time, when the button is clicked, `window` will be logged to the console, not the button element. This is because `hi()` was defined globally in the window and in arrow functions `this` represents the object that defined the arrow function.  

Arrow functions are a great addition to JavaScript and help to keep your code succinct and easy to read. However, the behavioral change of `this` in arrow functions can cause some unexpected results if used incorrectly. If you're unsure of the value of `this` in your function, be sure to throw a `console.log` in and test it out!

