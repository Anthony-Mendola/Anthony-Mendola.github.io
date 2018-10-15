---
layout: post
title:      "JavaScript Reduce Method Visual"
date:       2018-10-15 13:16:51 -0400
permalink:  javascript_reduce_method_visual
---



What is reduce? 
Reduce is an extremely useful array method similar to map and filter but more flexible. It gives you full control of it's output. Using an array as an input, you can get one single element (let's say an Object, or a Number, or another Array) based on the callback function (the first argument) which gets the accumulator and current element parameters.

# Sum Example

The best way to explain reduce is to visualize it. A common way to use to reduce is to sum an array. It allows you to take this array of numbers and compute a single result. 

![http://reduce.surge.sh/](http://engineering.khanacademy.org/images/lets-reduce/visualization.gif)

**Full demo:**  [http://reduce.surge.sh/](http://)

Reduce takes two arguments:
1. the callback function, called once for every item in the array. The callback takes a parameter accumulator(acc). The other callback parameter is the item itself.
2. an initial value which usually is 0 or an empty string

The initial value becomes the first argument supplied to the callback as *acc*. Our *initial value* is set to be **0**, and the first item in our array is **3**, so on the first iteration, our function body populates to *return* **0 + 3**.

For every subsequent iteration, *acc* receives the previous iteration's return value. This is the tricky part of *reduce*. We named the parameter *acc*, because  it accumulates the value of each iteration. 

Following the sequence, the second iteration receives **3** as the *acc* parameter (since the first iteration returned 0 + 3), and it adds that value to the next item in our array: *return* **3 + 5**;.

The third iteration receives **8** as the *acc* (since 3 + 5 is 8), and *returns*  **8 + 1**.

This process continues until the final iteration, where it *returns* **13 + 2**, which resolves to our final answer, **15**.

# Data Array Example
I recently completed a React/Redux project with a Rails API and used the reduce method to fix a common problem. 

**My data was coming back from my API like this:**
```
const inputFromServer = [
  {id: 'a', name: 'Amy'},
  {id: 'b', name: 'Blanche'},
  {id: 'c', name: 'Claude'},
];
```

**To ensure Redux working correctly, I used the reduce method:**
```
const getMapFromArray = data => (
  data.reduce((acc, item) => {
    acc[item.id] = item;

    return acc;
  }, {})
);

//initial value is an empty object
//on iteration it is augmented with the item provided
//Each item in the array is added to the acc object, keyed by its id

getMapFromArray(inputFromServer)

```

**This created a database-like tree structure:**

```
const desiredOutput = {
    a: {id: 'a', name: 'Amy'},
    b: {id: 'b', name: 'Blanche'},
    c: {id: 'c', name: 'Claude'},
};

```

# How is reduce different from map or filter?

This image sums it up!
![](https://i.imgur.com/jQ2De3N.png)




