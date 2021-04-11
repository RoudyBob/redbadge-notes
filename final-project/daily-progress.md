# Daily Progress

You are going to keep notes here on what you got accomplished and what you need to do for the next day. You will show this to your LA or instructor for the daily standups that we will have.

## 04/08/2021

I was able to start work on the back end. I was able to get the nodemon server initialized, models defined, framework for controllers create, etc.

I realized that getting all users and returning all attributes might not be a good way to handle what I want to do. I essentially want a list of all coaches so the user can authorize a coach. Getting all users would show everyone regardless of whether or not they're a coach and would also return a bunch of data that we wouldn't want all people to have. I had originally thought this would be an unauthenticated endpoint. Both dumb ideas. So I made it authenticated and then also am only returning id, email, firstname and lastname where coach = true. Much more secure way of doing this.

* all user controller endpoints finished
* tested with postman

What's Next?

* Start working on plan controller next.

