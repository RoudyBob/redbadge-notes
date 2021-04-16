# Daily Progress

You are going to keep notes here on what you got accomplished and what you need to do for the next day. You will show this to your LA or instructor for the daily standups that we will have.

## 04/08/2021

I was able to start work on the back end. I was able to get the nodemon server initialized, models defined, framework for controllers create, etc.

I realized that getting all users and returning all attributes might not be a good way to handle what I want to do. I essentially want a list of all coaches so the user can authorize a coach. Getting all users would show everyone regardless of whether or not they're a coach and would also return a bunch of data that we wouldn't want all people to have. I had originally thought this would be an unauthenticated endpoint. Both dumb ideas. So I made it authenticated and then also am only returning id, email, firstname and lastname where coach = true. Much more secure way of doing this.

* all user controller endpoints finished
* tested with postman

What's Next?

* Start working on plan controller next.

## 04/13/2021

I didn't have the associations correct for my plan and workout tables. I spent a good amount of time tonight getting that working properly.

I also realized that the way I was associating users with coaches via the team table was not going to work as I need it to. I ended up creating an association between the user table and team table and will have the user own the team record if they are a coach. Had to redo the user controller so that if a user had the profile set to "coach" it would automatically create the appropriate record in the team table. In that table there will be a column that will store the IDs of runners that have added themselves to that team.

Did get the plan controller completed. Realized that the datatype I had for the date should have been DATEONLY for the plan date and the user birthdate so had to redo that work. 

Started on the workout controller. 

Completed

* DB associations
* user controller
* plan controller

What's Next?

* workout controller
* team controller

## 04/15/2021

had ownerid in my model for workout. didn't need it.

when you put arrays in JSON body it has to have \[ \]

got associations to work to pull in the team if the user is a coach. this will then pull the team record for that user as well as I have access to the user's runners.

```text
User.findOne({
    where: {
        email: req.body.user.email
    },
    include: "team"
})
```

Figured out how to check to see if the coach coaches the runner they're looking up



```javascript
    if (req.user.team) {
        if (req.user.team.runners) {
            if (!req.user.team.runners.includes(parseInt(req.params.id))) {
                // Deny access if not a coach and the id doesn't match one of their runners
                return res.status(403).json({ message: "You are not this runner's coach." })
            } 
        } else if (req.user.team.runners === null) {
                // Deny access if not a coach has no runners
                return res.status(403).json({ message: "You are not this runner's coach." })
        }
    }
```

Completed

* DB associations
* user controller
* plan controller

What's Next?

* workout controller
* team controller

