---
layout: post
title:      "Backpacker Upgraded – Adding JQuery to my Rails App"
date:       2018-05-16 20:43:41 -0400
permalink:  backpacker_upgraded_adding_jquery_to_my_rails_app
---


For my JQuery/Rails project I modified my pre-existing Rails app, BackPacker. This was my first experience
modifying an already existing application which proved to be quite tricky, but also rewarding.

Even after going through and then reviewing all of the JS, AJAX, and Rails material, I was still uncertain exactly how all of these components worked together. This project was a great way to see all I had learned but also provided me with a working example to recognize my gaps in knowledge.

One of the first changes I made to the project was setting up my Active Model Serialization and switching over my
controller actions to render the JSON responses instead of using Rails. I struggled a bit after this to get my
JavaScript files loaded and learned along the way that the CoffeeScript files were taking precedence over my JS
files. Once this got sorted out, I began building my Trips JavaScript Model Objects and then worked out a serious of
functions to render my trips index page using jQuery GET request which loads JSON data from the server. I applied
a lot of the same logic to my Items files as well.

Some sample code:

```
Trip.prototype.indexTemplate = function() {
    let tripHtml = `
    <a href="/trips/${ this.id }" data-id="${this.id}">
      <li>${ this.location }</li>
    </a>
    `
    return tripHtml
}


//render all trips via json
function getTrips() {
    $("a.all-trips").on("click", function(e) {
        e.preventDefault()
        $('#trips-container').html('')

        $.getJSON(this.href, function(tripsData) {
            renderTrips(tripsData)
        })
    })
}

//append trip link to dom when index trips are loaded
function renderTrips(tripsData) {
    tripsData.forEach(trip => {
        let newTrip = new Trip(trip)
        let tripHtml = newTrip.indexTemplate()
        $('#trips-container').append(tripHtml)

    })
}
```


The project had certain requirements to fulfill including, translating JSON responses into JS model objects, using
GET and POST with AJAX/JSON, and creating JS prototype methods. I also added in some click events with JQuery
to enhance my form for creating a trip.

I plan to revisit this assignment as I build my portfolio to fix up a few things in the CSS and build out more of the
front end using JQuery.
