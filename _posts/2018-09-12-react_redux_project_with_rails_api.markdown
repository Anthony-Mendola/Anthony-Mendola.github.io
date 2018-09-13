---
layout: post
title:      "React Redux Project with Rails API"
date:       2018-09-13 02:37:56 +0000
permalink:  react_redux_project_with_rails_api
---


For my final assessment, I decided to create a Wellness Shopping site. The concept was inspired by one of my hobbies of volunteering as a nutrition coach. I love helping people and very often they ask me what health products I use. I thought it would be a great idea to create this application and integrate it with another one of my passions.

The project required to use React and Redux with a Rails backend. I wanted to make the application function similar to the shopping experience on amazon.com which would involve many components that needed to be built and connected. React is based on JavaScript in a syntax they call JSX. This syntax allows us to write HTML right in your JavaScript which makes things much more cohesive. I found it amazing to be able to create components and reuse, nest, or combine them. It gave me a much better understanding of how Facebook works under the hood. 

Another amazing discovery while making this app was Semantic UI. Basically, it's like Bootstrap for React. Its so easy to use and has so many styling options. I found it much more intuitive and faster to style than Bootstrap, I will definitely use it again in the future. 

The first step in creating the application was using the "new rails api" command. This is a stripped down skelton of the Rails framework just for APIs. Once this was loaded, I used "create-react-app" which automatically creates all the files and folders needed for a React app. To connect the frontend to backend, a gem called Foremen was used and a proxy was added to the client package.json file. 

The second part involved setting up my backend with my database, models, controllers and routes. My models were User, Item, Cart, and Cart Items. I also installed the active model serializer gem to make it easier to render the specific data i needed in json format. Once my backend was setup, I moved on to building out my components for the frontend. 

I layed out everything I needed and slowly started to build out each component like Menu, Items, Cart. After I had the skelton of the app, I started to add features like requiring to be logged in to add items to the cart and getting an order confirmation screen.

My components with state were connected to the Redux store with fetch actions to the API. There was a good amount of debugging involved with small errors that kept popping up. The great thing about React is that it tells you EXACTLY what's wrong. It's seriously amazing, it even gives you a link to the line of code that has an issue. The create-react-app itself isn't without bugs though. There were a few errors with no logical explaination so I decided to restart my server and computer which completely made it go away. 

Overall I'm very happy with how my app turned out. It was a great learning process as sometimes React/Redux can get very confusing, especially with understanding the flow of things. I'm glad Flatiron had a ton of resources and videos to explain this and make it much easier! 
