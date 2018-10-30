---
layout: post
title:      "Learning a New Programming Language (Python) & Turning an Idea into an App "
date:       2018-10-29 21:14:48 -0400
permalink:  learning_a_new_programming_language_python_and_turning_an_idea_into_an_app
---


**"They say knowledge is power. I disagree. Knowledge is potential. Skill is what you do with knowledge. And that is power."**
-Kyle Simpson

I've been really wanting to learn Python because of how versatile and crucial it is for data science. Especially algorithms and machine learning which are interests of mine. I've also been wanting to build a financial themed application and thought Python would be the perfect language to write it in. The most common language at FinTech companys is either Python or Java so I decided to get started with Python based on it's ease of learning. 

**App Vision**

The greatest part of being a software engineer is the almost instantaneous ability to take a thought and turn into something. That's one of the reasons I made this career change to turn my thoughts into products that make the world a better place. 

One of my passions is trading in the stock market. In the last few years, I've taken a step back and focused more on software engineering just because of the amount of time it takes to be a profitable trader. One of my favorite people in that industry is Warren Buffet, who only invests in things he understands. I've noticed the common middleclass person shys away from investing in the stock market just because of how complicated things may appear. If you only rely on one income, you may be working past retirement. Diversifying and having multiple income streams is the path to financial freedom which many people achieve. 

The problem is, only the upperclass have access to these easy to understand investments, many categorized as alternative investments. These investments include things like real estate, commercial loans, startup businesses loans, personal lending, & legal. The best part is that most of these investments are backed by real assets so your cash stays safe. Now some companies have started to offer these investments, but there's a new one popping up everyday.

My idea was to create an alternative asset investment marketplace where consumers can see every investment available from many companies. Users can invest directly without the need of an advisor or middleman. This gives power back into the hands of the individual. You can find exactly what you feel comfortable investing in and that aligns with your ideals. 


**Tech Stack**

For my tech stack I chose Python, Django, & Postgres.

Python is a very popular general purpose language used for typically used for web development, utilities, automation, machine learning, and data analysis.

Django and Flask are the two most popular frameworks for Python. 

Flask is low level and can be described as a micro framework. It has very few features with just a basic structure. This leads to a lot of freedom but also more room for error. 

Django on the other hand is more high level, gives a specific way to structure your files and write your code. It's much better for someone just learning Python and also provides very fast development by giving tons of command line tools. It also has great security features like authentication and an admin area built-in. 

**Frontend Pages**

* Home - Includes the 6 latest offerings sorted by newest - Search form
* About - Includes affiliate of the month, about us section, and all partners & affiliates
* Featured Offerings - displays 3 latest offerings with pagination
* Single Offering - displays more info on the offering and up to 5 photos with ability to inquire with a pop out contact form
* Search - When using the search feature, the search has it's own page to display results that match the criteria
* Register - Simple sign up page
* Login - Simple login page
* Dashboard (Inquiries) - When logged in, if a user makes an inquiry, they can keep track on the dashboard page
* Admin - backend interface where a user with staff permissions can add offerings, view inquiries, and add affiliates

**Functionality Specs**

*	Manage offerings, affiliates, contact inquiries and website users via admin
*	Role based users (staff and non-staff)
*	Display offerings in app with pagination
*	Ability to set offerings to unpublished or closed
*	Search offerings by keyword, term, annual interest, industry and minimum investment (Homepage & search page)
* Search stays populated with your search critera
*	List affiliates on about page with “affiliate of the month” (Control via admin)
*	Offering page has ability to add up to 5 images with lightbox
*	Lightbox scrolls through images
*	Offering page has a form to submit inquiry for that investment offering
* User form info is auto populated from the database
*	Form info goes to the database and notifies affilate(s) with an email
*	Frontend register/login to track inquiries
* User dashboard keeps track of your inquiries
*	Both unregistered and registered users can submit form. If registered, can only submit one per investment offering


**Future Functionality **

Each user of the platform will have the ability to also rate and leave reviews. When leaving your money in the hands of someone else, you should be able to view real reviews. I'm pretty sure that's more important than restaurant reviews yet this type of feature is nowhere to be found today. I'd also like to work with affiliates and tie into their API to retrieve up-to-date data of their new offerings.

**Conclusion**

This was one of the more advanced feature -rich apps I've made and proud to have been able to learn a new language and put it into practice immediately. Python was fairly easy to learn as the foundational concepts are similar to Ruby or JavaScript except for some differences in syntax. If you would compare Django to something like Rails, Django is not as easy to use. Especially with the architecture of making a new "app" for every page/feature and then those files within the app have the same name as every other app. The structure of Rails is much more straight forward and easier to use, I don't see any advantages to use Django except for it's built-in admin management system.


To see my code, please visit: [https://github.com/Anthony-Mendola/WealthAlchemy](http://)

To see my app live, please visit: [www.wealthalchemy.co](http://)



