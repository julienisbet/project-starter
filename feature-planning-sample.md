# FEATURES
​
## User Stories
------------
1. As a typical user, I want to see tequila-based meetups in my home city so that I can meet and drink with strangers. 
2. As a typical user, I want to receive suggestions based on my interest so that I can meet like-minded strangers. 
3. As a host, I want to create new tequila-based events so that I can help organize events to bring people together. 
4. As a lurker, I want to see what is happening in my city and either judge others or live vicariously through Tequila Time events. 
​
## Features - MVP
--------------
- [ ] Sign-Up page where users submit their name, email, and home city, and create a password. 
- [ ] Log-in page where users provide their email and password to log into the site. 
- [ ] A viewable table of upcoming Tequila Times, with ability to filter by user's home city.
- [ ] A viewable Tequila Time details page.  
- [ ] A viewable dashboard of joined/hosted Tequila Times. 
- [ ] Ability to join and leave a Tequila Time in your city. 
- [ ] Ability to create and cancel a new Tequila Time. 
​
## Additional Features
-------------------
- [ ] Display upcoming Tequila Times as a calendar view, with distinctions between past and upcoming events. 
- [ ] Ability to apply to be a host (host application form & approval process).
- [ ] Google Map API showing events based on location.
- [ ] Suggestions based on event details and user profiles.
- [ ] Display attending users on event detail page, ability to view profile pages/host pages. 
- [ ] Adjust event details for local time zones. 
- [ ] Limit number of people attending each event. 
​
## Tables
------
1. Users
    - name
    - email
    - password hash
    - cityId (belongsTo to Cities.id)
    - isHost (Boolean)
​
2. Cities
    - id (hasMany Users, Events)
    - city name
    - constraint: unique (& pre-defined list)
​
3. Events
    - cityId (belongsTo Cities.id)
    - date & time
    - venue/address
    - name
    - description
    - hostId (belongsTo Users.id)
    - [additional feature] number of people attending
    - [additional feature] limit number of people attending
​
4. Joint Table
    - userId (belongsToMany Users.id)
    - eventId (belongsToMany Events.id)
​
​
## Pages & Routes
--------------
### Sign-Up
-------
- Form generated with `get` request, submit will `post` name, email, password, home city. 
- Utilize Bcrypt for user authentication & authorization (storing password hash to database).
​
### Log-In
------
- Form generated with `get` request, submit will `post` email & password. 
- Utilize Bcrypt for user authentication & authorization.
​
### Table of Events
------------------
- Table generated with `get` request, pulling data from existing events [add'l = calendar].
- Clicking on event will bring you to event details page. 
- Ability to filter by user's city (user's city is stored upon sign-up).
​
### Host/Create New Event
----------
- Form generated with `get` request, submit will `post` which will create a new Event row/entry (automatically make user an attendee of event). 
​
### Event Details Page
------------
- Details generated with `get` request (attending users viewable as an additional feature).
- Host user has the ability to cancel an event (`delete` Event row/entry).
- User has the ability to join event (`post` request would generate an entry in the Joint Table).
​
### Dashboard of joined events/hosted events
----------------------------------------
- Table of joined/hosted events generated with `get` request. 
- Clicking on event will bring you to event details page. 
- [Additional feature] different styling of cell if hosted event. 
​
### Bonus: Google Map API showing events based on location
------------------------------------------------------
- Add to "Table of Events" page. 
- Use Event.address with API to display events based on location.
​
### Bonus: Suggestions based on event details and user profiles
-----------------------------------------------------------
- Users to select interests upon signup.
- Hosts to assign interest groups to new events when created. 
- Include on designated "Suggestion" page and/or on Events Dashboard. 
