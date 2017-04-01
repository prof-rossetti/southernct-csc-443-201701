# CRUD Application

You have been contracted to build a web application for a business that manufactures and sells robots. The business needs the application to keep track of their inventory of robots. They need to be able to add new robots to their inventory, view information about existing robots, edit information about existing robots, and remove existing robots from the inventory. They also need to be able to keep track of how many of each type of robot are available in their inventory at any given time.

As a member of your development team, the professor has already finished designing and developing a database to store all this information. The professor has also developed a RESTful JSON API to help you interface with the database. The professor has published the web service in production at _____ and has provided API documentation at __________.

Your job is to create a front-end web application to allow users within the company to interface with the back-end web service.

![a screencast depicting usage of a CRUD application. the application displays a table of records. an individual record is displayed in detail when clicked. buttons are clicked and forms are submitted to create new records and edit records. buttons are pressed to delete records and restore the entire set of original records.](demo.gif)

## Instructions

The first three checkpoint exercises listed below helped you prepare the application's style, structure and interactivity for future development. Now it's time to use Node.js to actually build the CRUD application. For detailed instructions, refer to the following checkpoint exercises:

  + [Checkpoint IV - Generation](_______)
  + [Checkpoint V - Hosting](________)
  + [Checkpoint VI - Navigation and Routing](________)
  + [Checkpoint VII - Listing and Showing Records](________)
  + [Checkpoint VIII - Listing and Showing Records](________)
  + [Checkpoint IX - Listing and Showing Records](________)

## Submission Instructions

When your application is ready for evaluation, add its identifying information, including your GitHub username, a link to your app's repository, and a link to your hosted appplication, to the [submissions list](submissions.md). Use the following workflow to accomplish this:

  1. Fork [this repository](https://github.com/SCSU-CSC-Department/201701-csc-443-01/) to your own account.
  2. Edit the submissions list in your forked repo via the online editor, or by downloading your forked repo, making local commits, and pushing them back up to GitHub.
  3. Submit a Pull Request for your changes to be merged into this repo.

> NOTE: If you would prefer for any reason to submit your work privately, you may alternatively send the professor your links via email or Slack DM. Your project will still be evaluated, and peer-evaluated, but its identifying information will not be publicly accessible as part of this course repository.

Also be prepared to deliver a 5-10 minute presentation to demonstrate usage of your website and describe your planning and design process, as desired.

## Evaluation Criteria

Your data visualization will be evaluated according to the following criteria:

criteria | weight
--- | ---
Planning | 15%
Implementation | 60%
Peer Evaluation | 25%

Partial credit may be given to highlight areas of improvement.

### Planning Evaluation

TBA

### Implementation Evaluation

Your CRUD Application implementation will be evaluated based on its demonstrated ability to meet all of the following criteria:

  1. Is hosted on the Internet and publicly accessible.
  2. Is built using an application framework that incorporates view templates to eliminate or minimize duplication of front-end HTML code.
  3. Contains clear, concise, and engaging content free of typographical or grammatical mistakes.
  4. Usable design free of usability quirks or bugs.
  5. Allows the user to navigate between at least all of the following pages:
    + `index.html`
    + `robots/index.html`
    + `robots/show.html`
    + `robots/new.html`
  6. Allows the user to perform the following actions:
    + View all robots (List)
    + View a single object (Show)
    + Delete a single object (Delete)
    + Edit a single object (Edit)
    + Create a new object (New)
  7. Enables CRUD operations by interfacing with the provided back-end web service in all of the following ways:
    + Issues GET requests for all objects (Read)
    + Issues GET requests for a single object (Read)
    + Issues POST requests to delete a single object (Destroy)
    + Issues POST requests to create a single object (Create)
    + Issues POST requests to update a single object (Update)

#### Peer Evaluation

All members of the learning community, including the professor, will evaluate an assigned list of five submitted CRUD Applications, and will assign each peer project a score from 1 to 10. A weighted average of these individual scores will produce the overall Peer Evaluation Score.
