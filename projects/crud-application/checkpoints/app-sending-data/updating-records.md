# CRUD Operations - Updating Records

## Instructions

### Routing to the Edit Page

Add an "Edit" button (or link) to the robot show page. When the "Edit" button is clicked it should bring the user to a different destination URL, for example to `/robots/:id/edit`, where `:id` is the robot's unique identifier.

Click the button to find an error complaining about a routing issue. Create a router function to handle requests to this URL path and respond by rendering a view, for example `views/robots/edit.ejs`, a.k.a the "edit page".

Refresh the page and click the "Edit" button again to find an error complaining about the edit page not existing. Create it now. The page should contain a robots form. The robots form should be very similar to the one you used during the [Creating Records](creating-records.md) exercise, except you will need to pre-populate form input values using the actual `robot` values you pass from the router to the form.

### Pre-populating Form Input Values

Refresh the edit page to find an error complaining about the `robot` variable being undefined. Edit the router function now to make a `GET` request to the proper API endpoint to get the robot's information and pass it to the edit page.

Refresh the edit page to find the form pre-populated with the robot's information.

Confirm your ability to modify form input values. Next we will prepare to submit the form.

### Submitting the Form

Ensure that when the form "Submit" button is clicked, it issues a `PUT` request to the proper API endpoint, passing the appropriate data in the request body. When the client receives a return response from the API, it should either redirect to the robot show page, or it should display error message(s) to the user.

You should be able to leverage the [Creating Records](creating-records.md) exercise to find an example of how to make a request like this and redirect the user appropriately.
