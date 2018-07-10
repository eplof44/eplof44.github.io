---
layout: post
title:      "Setlist - a React/Redux App"
date:       2018-07-09 20:19:26 -0400
permalink:  setlist_-_a_react_redux_app
---



Wow. That’s it. 'Finished' my last Flatiron School project. I created an app that allows users to keep track of concerts they attended and the songs the band played. I see this an open source app where users can edit and collaborate on the concert setlists.

This project was by far the most challenging. It took a few solid days of react/redux review sessions, a few tantrums at the computer, and reading A LOT of open source projects to get this one complete. Overall, I’m pretty happy with it and I didn’t compromise on any of the features I wanted to add.

With the help of a few blogs, I thankfully had little trouble setting up my rails backend. The API setup served as a good refresher for ActiveRecord migrations and I was able to take this opportunity to install PostgreSQL for later deployment to Heroku.

Next, I set up my database, models, serializers, routes, controllers, and seeded my database for testing. I saw that my JSON was loaded with my concerts and associated comments. I was feeling good at this point and I decided to create my react client files within the rails app with 'create-react-app.'

After setting up the initial front end structure  I figured the actions and reducers made the most sense so I could test the API by writing some fetch requests.

Actions

```
export const setConcerts = concerts => {
  return {
    type: 'GET_CONCERTS',
    concerts
  }
}

```
```
export const getConcerts = () => {
  return dispatch => {
    return fetch(`${API_URL}/concerts`, {
      method: "GET",
    })
    .then(res => res.json())
    .then(concerts => {
      dispatch(setConcerts(concerts))
    })
    .catch(error => console.log(error));
  }
}
```
Reducer

```
    case 'GET_CONCERTS':
    return {...state, concerts: action.concerts}
```

At this point, it took me a bit of time to get started on the components.  I read through a lot of code and went through past labs to carefully map the flow of data. Eventually I got my concert form working and seeing the JSON update with my form inputs was *very* exciting. The concert show pages slowly working after that. Then a lot of break, fix, break, fix, break, repeat.

After this I tackled my comments form, ‘I attended’ counter button, and at the end added a ‘random’ concert button to generate for the user a random concert. 

Something I struggled with for a while was getting my comments to show up on the corresponding concert card. After a screen-share with a tech coach I eventually got this feature working.

I then added some custom CSS, which turned out simple but stylish. I always enjoy this part and seeing the project come to life.

I’m sure this app can be consolidated and refactored in many ways. It’s not the ‘DRYest’ and I continue to find React pretty confusing...but...

This entire project really allowed me to demonstrate (for myself) everything I have learned over the past year at Flatiron. I was very happy to hit the submit button on this final project (with the full understanding that this is really just the beginning).

