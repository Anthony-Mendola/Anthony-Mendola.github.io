---
layout: post
title:      "Intro to Ember.js - Part 1"
date:       2018-11-27 19:09:03 +0000
permalink:  intro_to_ember_js_-_part_1
---


I'm in the process of interviewing with a company who's current stack is Ember.js, Rails, & Postgres. Although I wasn't familiar with Ember before applying, I made it a priority to learn as much about it to give myself the best chance of getting the position. Follow along as I create a simple app using Ember.

**What is Ember?**

Ember is an open source MVC framework for creating ambitious web applications. If compared side by side to all other frameworks, it would be most similar to Rails. Ember is built for delivering dynamic, data-driven applications.

**Companies Using Ember**
Discourse , Dollar Shave Club, Sony Playstation Now, Apple Music, & NASA.gov

**Structure**

Model-view-controller (MVC) helps create reusable and extendable code by separating and isolating responsibilities.

![](https://i.imgur.com/GuZHWF1.jpg)

The user will interact with a controller. That controller will manipulate data on a model. That model's data will change and update a view layer which the user will finally see.

Usually, most web applications send data to the servers to validate, process, and render HTML. This is a time consuming proccess. Frameworks like Ember are shifting responsibilities from the server to the web browser. More client responsibilities mean fewer network requests, making the app feel faster. 

Ember uses a holistic approach and gives you benefits from the entire JavaScript community. They put the best practices for tooling, convention, and standards, all in one place. 

**Installing Ember**

Ensure Node.js is installed and npm is available
Install Ember CLI using the terminal `$ sudo npm install -g ember-cli`

To create a new project ` $ ember new <project name>`

Another useful command is `ember serve` which starts a live-reloading development server. The browser will automatically reload whenever application files change. 

**Working in App**

Ember CLI generated several directories with many HTML, JavaScript, & CSS files for us.

Within your app folder you'll find a folder named templates. Templates tell Ember what HTML to generate and display in the web browser to your end user. This is called the "application" template, which is based on the file name of *application.hbs*

By convention, all Ember applications use an application template. Ember uses the Handlebars templating library. The .hbs file extension is specific for Handlebars. These Handlebars templates look like HTML but allow us to insert dynamic data using Handlebars expressions.

**How templates work**

You'll notice in the *application.hbs* file  `{{outlet}}` . This is a Handlebars expression which are wrapped with curly braces (or brackets) and are sometimes called "mustaches".  The *outlet* expression acts as a placeholder and tells Ember where to place other templates on the page to render them. 

The application template is the outermost layer into which other templates get rendered. When the template content changes, the outlet content is updated as well.

![](https://i.imgur.com/iLVUMsR.jpg?1)

Without the `{{outlet}}` expression, there would be nowhere for other templates to go. 

Ember is currently displaying an auto-generated index template. This can be overriden by creating an index.hbs file. Ember displays this by convention.

**Router**

You'll have to let Ember know about new templates you're creating so it can display them. You can do this thorugh the router. The router manages your application state and maps it to the path of the URL. It keeps track of what a user is doing and where they are in your application at all times. For example, their state could be viewing a menu, viewing a receipt, or creating an order. The router does that by mapping that state into the URL. 

![](https://i.imgur.com/uWNnpI6.jpg?1)

Open the router.js file. All the application endpoints will be mapped within `Router.map(function() {
});`

I created an *orders.hbs* template. Now I will add that to my router. 

```
Router.map(function() {
 this.route('orders', { path: '/orders' });
});
```

What this is saying: "when I navigate to the URL /orders, I should see the orders template"
If the path matches the name, we can omit the path. In this case since my file is called orders, we can omit the /orders path from our route.
```
Router.map(function() {
  this.route('orders');
});
```

**Links**

Although you could use HTML to hard code links to endpoints, it should be avoided. It causes a browser reload which defeats the purpose of using Ember.

The best way to navigate is using the  Handlebars `{{link-to}}` expression. This allows us to navigate without the page requiring a reload.

In* index.hbs*: 
```
{{#link-to "orders"}}Orders{{/link-to}}
```

The `#` at the start of the expression tells Handlebars that we are using a blockform of the helper and lets us put content inside the link just like a standard anchortag. The block is then closed with a `/` and the name of the helper `link-to`.
If you look at the html markup, it looks like a standard link but because we used the link-to help, Ember now knows about it. It's watching for a click and it will intercept that click. Rather than having the browser perform the navigation, Ember will navigate the router and rerender the page automatically on the client side for us. This is significantly faster. 

We can also easily customize our tag by passing additional attributes to `{{link-to}}`
![](https://i.imgur.com/x2TN2pw.jpg?1)

If you had to customize that tag even more, we could add a "tagName property to change the generated HTML tag. 
![](https://i.imgur.com/gSbOixs.jpg?1)

Ember ships with many other Handlebars helpers for tag generation & logic.
![](https://i.imgur.com/rJ8G5CJ.jpg?1)

*If all page changes are happening on the client side, why bother updating the URL?*
1. Ember uses the URL to keep track of where the user is in the app. (Application State) 
2. Updating the URL allows to share links and still use the browser's back button


**Routes**

Ember has been automatically generating a hidden layer between the router and the templates that collects the needed data and renders templates. This layer is called Routes.

 Routes are responsible for collecting data and rendering the proper templates. The router talks to routes, and routes talks to templates. 
 
 Ember auto-generates routes that have the same name as the template. In the case of my application, the generated orders route renders the "orders" template.
 
 Ember CLI provides a generator for creating a route and updating the router. 
 
 `$ ember generate route <route-name>`
 
 ![](https://i.imgur.com/8CsPBQd.jpg?1)
 
 Routes are defined in app/routes with a file name matching their route name. You can customize the route's model by adding a model function known as a hook. In our example I'll return my name. 
 
 ```
export default Route.extend({
  model() {
    return 'Anthony';
  }
});
```

We can then go our orders.hbs template and render that function using Handlebars `{{model}}`. The routes model is available to the template as "model". It's a built-in Ember convention. The model function can return anything. 

If we wanted to return an object it would look like this:

![](https://i.imgur.com/5vcoaE8.jpg?1)
 
 

If we wanted to return an array, it would look like this:

![](https://i.imgur.com/ELnhPy4.jpg?1)

In the template we would use the #each helper. The each helper is an iterator. It's called using **#each** **collection name** **as ** and the  **name of each instance**.  In the example above, model is the collection name. This bloc k is going to iterate once for each item in the collection and in that block we render out each order's id and name. 

**Navigating to a Single Item**
To link to a single item, we need a route that can load and render a single item matching that order id. The first step is to create a new state that represents viewing a receipt for a single order. To map the new endpoint we add it to the router.

```
Router.map(function() {
  this.route('orders');
  this.route('order', {path: '/orders/:order_id' })
});
```

The `:order_id` is known as a dynamic segment. It instructs the router that it will match anything thats at that location in the URL, in this case, the order number. 

*How exactly does this work?*

When a request comes in to view the receipt for order 1 for example: 
1. The browser will try to go to */orders/1*
2. The router sees that URL and will try to interpret it comparing it against all of its known routes.
3. It will first compare it against the */orders* route which does not match *orders/1*
4. It will then go down to the next route which is */orders/:orders_id* in this case it matches because the order portion matches and the dynamic segment matches any value. Her e it will match the *1*. 
5. The router realizes it has dynamic values and it captures it by extracting the dynamic portion, in this case the *1*.
6. The router takes the *1* and maps it to an *order_id* variable and put its into a hash `{order_id: 1}`
7. The hash data is sent to the router to tell it which order the user requested. Now it needs to get that data to the route so it can be used.
8. The model hook in routes/orders.js takes optional parameters. Usually called params. It's whatever dynmaic data the router has found that it is handing down to the route. 
9. In this case, the passed in params data {order_id: 1} hash is used to filter the data down to one object. 


This ends part 1 of my intro to Ember. Stay tuned for part 2 in the next 1-2 weeks.

