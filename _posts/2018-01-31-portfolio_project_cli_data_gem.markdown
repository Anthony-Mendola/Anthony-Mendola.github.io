---
layout: post
title:      "Portfolio Project: CLI Data Gem"
date:       2018-01-31 00:45:23 -0500
permalink:  portfolio_project_cli_data_gem
---


For my first portfolio project in Flatiron School, I was given the task to create a CLI (Command Line Interface) Ruby Gem. I initiallity started to think of ideas with the intention in mind to create something that people will find very useful. 
After a bit of brainstorming, I remembered that when I worked in the construction industry, it was always difficult for employers to find laborers for short-term projects. At times i'd be given the task to go on Craigslist, type in all my search criteria, different areas, etc which would take lots of time. Wouldn't it be great if I could just boot up my computer, type one word and get a list of laborers who are looking for work, without having to scour through Craigslist?!

**First Step:**

As a new developer, I've learned that my first step should always be to write in words or pseudo code exactly what I want my program to do. In this case, I needed a command line interface that welcomes the user, gives them options of laborers pulled from Craigslist, allows them to select those options, and then provide more details. 

**Second Step:**

Scraping. I used something called Nokogiri which is a Ruby Gem that allowed me to target specific content through the use of CSS and HTML. The information that I found most important was the post name, date, location, url, and detailed body of post. This part of the process took a good amount of time and tinkering to figure out which selectors worked best and were secure. I used Pry which is a debugger that allowed me to play around with code in real time to ensure it provided the necessary data. This data was pulled into a hash and then into an array. During the project, there was an entire day lost of work when my Pry debugger stopped working. I spent many hours trying to figure it out until i finally decided to try to restart my computer which solved the problem. Lesson learned! Always restart first!

**Third Step:**

One of the requirements of this project was that my program should be a collection of objects, not hashes. I turned my hashes into objects which were my parameters: name, date, location, url, & post.  Everything was then tied together, my laborer file, scraper file, and CLI file working in unison. 

**Bonus Points**

As a bonus, I was able to get this application to function as a gem. The user can easily install this gem and then run the app by using the word 'laborer-wanted'. 

**Lessons Learned**

I had days where I was stuck and couldn't figure out an error or what code to use. I rode it through, took a step back, took a walk, slept on it, the answer always came. I became an expert at using Google and Stackoverflow, finding answers to coding errors that allowed my application to run properly while looking cleaner. I went back my times to clean up my code and make it look better or more efficient. It made me realize there are so many ways to do the same thing which is sometimes a hard concept to understand when learning coding. 

**Final Thoughts**

This was a very exciting project for me. I built something that could be useful to certain employers and i was able to do it all on my own. It felt very fulfilling to create and use all the knowledge I learned from Flatiron to good use. I am looking forward to the next project!


