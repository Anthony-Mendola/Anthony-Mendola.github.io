---
layout: post
title:      "Rails Parking app with jQuery Front End "
date:       2018-08-20 14:55:48 +0000
permalink:  rails_parking_app_with_jquery_front_end
---

The goal of this project was to build on my previous Rails portfolio application to include jQuery functionality. This would allow my application to be dynamic by utilizing JSON and AJAX to render information without a page refresh as well as other requirements listed below. This sounded like it would be a simple task had my application been simple but due to the advanced functionality of my rails app, it proved to be one of the most difficult I've tackled. In my Rails application, I used many gems like paperclip for photos, geocoder for google maps, and simple form for my forms. I kept getting errors, especially in my javascript files. After much debugging and research on StackOverflow, I decided to rebuild a simpler version of my app with these gems excluded. This was a lesson in itself, making a difficult decision to continue debugging which was taking days or to reinforce my  Rails skills and rebuild the app. The latter proved to be the more efficient way and I made the right decision. I could see this situation occurring in a work setting, where I may be tasked with either rebuilding an application or debugging its issues. Having a balance of patience, efficiency, and using your intuition of what is best is key. 

**Project Requirements and how I implemented them

1.  Must render one index page via jQuery and an Active Model Serialization JSON Backend.

      * This requires that the application be set up with a JSON backend to serve any JSON requests and to properly serialize the data. The Listings Index page displays all active parking listings. On load, the page makes an API call to /listings which returns a JSON object containing all listings. The backed end is setup with an ActiveModel::Serializer file for the Listing model which allows it to return the indicated data and present it in JSON format.  I also added a "More Info" button that expands a section under each listing to include the full description without redirecting the user to the individual listing. 

2.  Must render one show page via jQuery and an Active Model Serialization JSON Backend.

      * Similar to the above requirement. The Listings show page has a "Next" button and "Previous" button that allows the user to navigate through all the Listings without redirecting. Upon clicking on the buttons, form data is received via a JSON call which is serialized with Active Model Serializer and rendered onto the show page. 

3. The Rails API must reveal at least one has-many relationship in the JSON that is then rendered to the page.

     * On the listing index page, a User has many Listings.
 
     * On the show page, a Listing has many Reviews.

4. Must use your Rails API to create a resource and render the response without a page refresh.
     
      * On the Listings show page, you can add a new review without a page refresh as well as load all comments without a          fresh. When a user adds a review, the review is serialized, submitted via an AJAX POST request, and the response is the JSON object which is appended to the DOM.

5. Must translate the JSON responses into Javascript Model Objects. The Model Objects must have at least one method on the prototype.

     * For this requirement, I created a constructor function to build a prototype for a Review object. When a review is submitted, a new Review object is created according to the Review Model Object function with its properties of id, content, and user. I added a method called postReview which formats the data and appends it to the DOM.

I really enjoyed working on this project. I learned so much, not only in JavaScript & jQuery but also in research and making difficult decisions. 

 
 
