# Project Management
For your project, we encourage you to utilize user stories and acceptance criteria for planning your work. As a reminder, there are two main messages 
a user story should convey:
​
1. What functionality needs to be developed and who it is for.  (who and what)
2. To help readers understand why this important (why)
​
User stories DO NOT need to only be worked on by a single person -- however they should have a "story owner" whose job it is to breakdown the work into semi-independent chunks
​
Acceptance criteria defines the boundaries of the user story. We use acceptance criteria to determine what needs to be true, in order for this story to be considered done. This can help prevent scope creep as you are agreeing before the work begins what is included and what is not. 
​
# Authorization User Stories
Note: these stories assumes there is a User model / database  available, with an email, username and password field -- generally, model creation would be included as part of a story but since the user is such a building block, it may make sense to pair on that and get it done ASAP.
​
## As an unauthorized user, I want to be able to login to the website, via a form, in order to access my private information
​
#### Questions
* Will the user enter a username or an email address to login?
    * User will login via email and password
* What routes should we use for login?
    * User will login via /login both get / post
* Where should the user be redirected after login?
    * User will be redirected to the "/" homepage
* Will we allow oauth authentication via a third party?
    * Not yet -- maybe in a future story
* What happens if the user doesn't exist yet?
    * Display the message ```Invalid Login :( please try again.```
* What happens if the user enters the wrong password?
    * Display the message ```Invalid Login :( please try again.```
* Should this story include allowing a user to reset their password?
    * Not yet -- maybe in a future story
* Should logging in set a session or use token based authentication?
    * We will use session auth for now
#### Acceptance criteria
- [ ] User can visit the /login route and there's a form with email / password
- [ ] After user enters a valid email and password they are redirected to the homepage
- [ ] If a user enters an invalid email / password, they receive a message ```Invalid Login :( please try again.```
- [ ] If a user enters the wrong password, they receive the message ```Invalid Login :( please try again.```
- [ ] Refreshing the page after login maintains the user session  
​
## As an unauthorized user, I want to be able to sign up for the website via a signup form in order to access this awesome website
### Questions
* How long should session last?
* What information are we collecting from the user?
* Whats the UX like? What does the form look like? How simple is it?
* Where should the user be redirected after signup?
* What happens if the user has signed up previously? (what makes a user unique?)
* What are the password requirements?
* What happens if the user's password isn't strong enough?
* Are we allowing sign up via OAuth?
* Do we need a confirmation email?
* What routes should we use for sign up?
### Acceptance Criteria
