---
layout: post
title:      "Pure Functions: What Are They? "
date:       2019-12-01 19:09:08 -0500
permalink:  pure_functions_what_are_they
---

![](https://i.imgur.com/2Q0U6LU.gif)

Pure functions are functions that [deterministic ](https://docs.microsoft.com/en-us/sql/relational-databases/user-defined-functions/deterministic-and-nondeterministic-functions?view=sql-server-ver15) meaning they will always return the same value if the same input is passed in as an argument. 

Pure functions have a couple of specific properties that determine their purity: 

1. Pure functions return output solely based on their input (i.e. parameters), and do not depend on any state or data change.   
2. Pure functions do not produce any observable side effects.

### What are Side Effects?

A side effect refers to any action that is doing something other than the primary purpose of your function. 
Since pure functions just take an input and return a value based on that input, they do not interact with anything outside of their own scope (including functions, variables, etc.). When a function conducts any action outside of calculating its own return value, it is impure.

![](https://media.giphy.com/media/xT5LMuZyzHqiQcVO5a/giphy.gif)

A few examples of side effects are:

1. Logging anything to the console.
2. Making HTTP requests (fetch/AJAX).
3. Querying the DOM.
4. Mutating state or data.
5. Saving something in a database. 
6. Calling an impure function (**Note:** a pure function calling another pure function does not make it impure).

If your functions conducts any of the above actions, then your function is impure.  

Now let's check out some examples of pure and impure functions. 

```
const recipe= [];

function addToRecipe(ingredient){
	recipe.push(ingredient);
}
```

The function `addToRecipe()` is **not** pure.  Since `addToRecipe()` is modifying the variable `recipe` outside of its own scope, the result wouldn't always be the same. Also, notice that there is no value being returned by `addToRecipe()`. Remember, a pure function must return a value based on its input; so if there is no value being returned, then the function is impure. 

If we wanted to convert the above function into a pure function, we could do something like this: 

```
const recipe = [];

const addToRecipe = (recipe, ingredient) => [...recipe, ingredient];
```


In this example, `addToRecipe()` is a pure function because it uses its two variables, `recipe` and `ingredient`, to return a new value while not mutating any variable outside of its own scope. 

You may notice that this example is also lacking an explicit return, but since `addToRecipe()` is an [arrow function](https://bsalemi.github.io/arrow_functions) with a concise body an implicit return is acceptable. Unlike the first example which used `recipe.push(ingredient)`, the pure `addToRecipe()` is using the ES2015 [spread operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax) which does **not** modify the original array. This leads us to my next point.

## Do. Not. Mutate.

The use of any mutating methods for arrays (`push()`, `unshift()`, `pop()`, `shift()`) will instantly render your function impure, as the original array will have been modified. Instead use `concat()` and the spread operator to return a new array. For objects, use `Object.assign()` to maintain purity and create a new object instead of modifying the original. 

## In Summary: Why Pure Functions?

Pure functions are known as the building blocks of functional programming and provide many benefits when using them. 

Firstly, pure functions are immediately testable as they will always produce the same results given the same inputs. The predictability of pure functions allows them to be reused, with confidence, as many times as desired. 

This predictability grants easier maintaining and refactoring of code, allowing for changes and updates to be made without the worry of breaking your entire application.  There are many more benefits to using pure functions, but in short, when used correctly, they produce better quality and more stable code. 

To learn more about the many benefits of pure functions, click [here](https://en.wikipedia.org/wiki/Pure_function). 

![](https://media1.giphy.com/media/dsKnRuALlWsZG/giphy.gif?cid=790b7611eeef786c9d50f9bb821f6ce98bedc9fd6c6cacb9&rid=giphy.gif)

