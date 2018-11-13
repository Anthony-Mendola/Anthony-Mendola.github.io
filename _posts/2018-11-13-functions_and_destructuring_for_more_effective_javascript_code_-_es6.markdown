---
layout: post
title:      "Functions & Destructuring for More Effective JavaScript Code - ES6"
date:       2018-11-13 22:38:54 +0000
permalink:  functions_and_destructuring_for_more_effective_javascript_code_-_es6
---


The purpose of this blog post is to teach some tools and techniques to make your JavaScript code less breakable, less fragile, and more effective. As well as gain a better understanding of some JS concepts.

**Function Declaration**
Function declarations are hoisted. When run, the function is sent to the top. 
```
function sayHi() {
  return console.log("hi");
}
```

**Function Expression**
Function expressions are very common in JS code and are not hoisted. The variable is named but the function is anonymous(not named).

```
const sayHi = function() {
  return console.log("hi");
}
```

We could name the function if we really wanted to. This is an unnecessary step but can be useful when you're debugging so you can easily find your function.

```
const sayHi = function sayHi() {
  return console.log("hi");
}
```

**ES6 Arrow Function**
This is the same as our function expression but shorter and gives us more usage for the *this* keyword.
```
const sayHi = () => {
  return console.log("hi");
}
```

We can also omit the curly brackets and the return. This only works for a one-line expression.

`const sayHi = () => console.log("hi");`

If you want to make use of the automatic return but still have your expression on a second line then you can add parenthesis.

`const sayHi = () => (
console.log("hi"));`


**Destructuring**
Destructuring allows you a way to pull out items from an array or object and assign them to a variable of the same name.

*Arrays*

```
const [a, b] = newArray
const newArray = ['Hi', 'Ant'];
console.log(b); //'Ant'

//This is equivalent to
const newArray = ['Hi', 'Ant']
const a = newArray[0];
const b = newArray[1];
```

If there are more items, you can use the spread operator, `...` which gives us everything else.

```
const newArray = ["hi", "ant", "new", "more"];
const [a, b, ...c] = newArray;
console.log(newArray);
```

*Objects*

We have a person object.
```
const person = {
  name: "Anthony",
  age: 30,
  job: "web dev"
};
```

We create a function that accepts a name, age, & job which are variables that are passed into this function. We return an object and insert the *person* properties with their values (pre ES6)
```
const makePerson = (name, age, job) => {
  return {
    name: name,
    age: age,
    job: job
  }
}
```

*With ES6*

We can omit the value name if the property name is the same as the variable name. Our output will be exactly the same as above.

```
const makePerson = (name, age, job) => {
  return {
    name,
    age,
    job
  };
};
console.log(makePerson("tim", 33, "comedian"));
```

*Object Destructuring*

New dev object:

`const dev = makePerson("Anthony", 30,  'web dev');`

To pull out the name we could:

`const name = dev.name;`

but with ES6 we could:

`const { name } = dev;`

This allows us to write consistent code by naming things consistently and not reassigning a bunch of names to things.

A common usage for this is in React. We can shorten this.props.names by:
`const { names } = this.props;`

This allows us to use `names` alone.

It is very common in JS to make an object and then pull out properties from it. The main benefit is that it helps keep names together without having to create new names for things. It makes your code more cohesive and easier to read.

I plan to continue this segment with a part 2 with more techniques. Thank you for reading!

