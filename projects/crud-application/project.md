# CRUD Application

You are part of a development team that has been contracted to build a web application for a business that manufactures and sells robots. The business needs the application to keep track of their inventory of robots. They need to be able to add new robots to their inventory, view information about existing robots, edit information about existing robots, and remove existing robots from the inventory. They also need to be able to keep track of how many of each type of robot are available in their inventory at any given time. Ideally, they'd also like to be able to use the application to process orders and update their inventory accordingly.

![a screencast depicting usage of a CRUD application. the application displays a table of records. an individual record is displayed in detail when clicked. buttons are clicked and forms are submitted to create new records and edit records. buttons are pressed to delete records and restore the entire set of original records.](demo.gif)

As a senior member of your development team, the professor has already finished designing and developing a database to store all this information. The professor has also developed a RESTful JSON API to help you interface with the database. The professor has published the web service in production at https://southernct-443-robots-api.herokuapp.com/ and has provided API documentation at https://github.com/prof-rossetti/robots-api-express/blob/master/DOCUMENTATION.md.

Your job is to create a front-end web application to allow users within the company to interface with the back-end web service to perform all desired tasks. Don't worry about user authentication, which is outside the scope of this project.

![a whiteboard depicting a user interfacing with a client application and that client application interfacing with the back-end web service](/projects/crud-application/checkpoints/app-deployment/client-server-architecture-diagram.png)

Your application should be built using Node.js and the Express web application framework. It should be hosted in production on a Heroku application server.

## Instructions

The first three checkpoint exercises helped you prepare the application's style, structure and interactivity for future development:

  + [Checkpoint I - Structure](/projects/crud-application/checkpoints/structure/checkpoint.md)
  + [Checkpoint II - Style](/projects/crud-application/checkpoints/style/checkpoint.md)
  + [Checkpoint III - Interactivity](/projects/crud-application/checkpoints/interactivity/checkpoint.md)

Now it's time to actually build the CRUD application. For detailed instructions, refer to the following checkpoint exercises:

  + [Checkpoint IV - Application Generation](/projects/crud-application/checkpoints/app-generation/checkpoint.md)
  + [Checkpoint V - Application Deployment](/projects/crud-application/checkpoints/app-deployment/checkpoint.md)
  + [Checkpoint VI - Application Navigation and Routing)](/projects/crud-application/checkpoints/app-navigation/checkpoint.md)
  + [Checkpoint VII - Application CRUD (Reading Records)](/projects/crud-application/checkpoints/app-receiving-data/checkpoint.md)
  + [Checkpoint VIII - Application CRUD (Creating, Updating, and Destroying Records)](/projects/crud-application/checkpoints/app-sending-data/checkpoint.md)

If you have completed the first three checkpoint exercises, feel free to use your work to help you more quickly and easily complete the remaining checkpoint exercises. If you have not completed the first three checkpoint exercises, you are advised to only focus on the remaining checkpoint exercises, which might take a little longer to complete as a result.

## Submission Instructions

When your application is ready for evaluation, add its identifying information, including your GitHub username, a link to your app's repository, and a link to your hosted application, to the [submissions list](submissions.md). Use the following workflow to accomplish this:

  1. Fork [this repository](https://github.com/SCSU-CSC-Department/201701-csc-443-01/) to your own account.
  2. Edit the submissions list in your forked repo via the online editor, or by downloading your forked repo, making local commits, and pushing them back up to GitHub.
  3. Submit a Pull Request for your changes to be merged into this repo.

> NOTE: If you would prefer for any reason to submit your work privately, you may alternatively send the professor your links via email or Slack DM. Your project will still be evaluated, and peer-evaluated, but its identifying information will not be publicly accessible as part of this course repository.

Also be prepared to deliver a 5-10 minute presentation to demonstrate usage of your website and describe your planning and design process, as desired.

## Evaluation Criteria

Your CRUD Application will be evaluated according to the following criteria:

criteria | weight
--- | ---
Implementation | 75%
Peer Evaluation | 25%

Partial credit may be given to highlight areas of improvement.

### Implementation Evaluation

Your CRUD Application implementation will be evaluated based on its demonstrated ability to meet all of the following criteria:

  1. Is hosted on the Internet and publicly accessible.
  2. Contains clear, concise, and engaging content free of typographical or grammatical mistakes.
  3. Usable design free of usability quirks or bugs.
  4. Is built using Node.js and Express.js.
  5. Incorporates ("includes") at least one EJS view template to minimize duplication of front-end HTML code.
  6. Enables navigation between at least all of the following routes:
    + Home Page (`/`)
    + Robots Index Page (`/robots`)
    + New Robot Page (`/robots/new`)
    + Robot Show Page (`/robots/:id`)
    + Edit Robot Page (`/robots/:id/edit`)
    + New Order Page (`/orders/new`) -- optional extra credit
  7. Interfaces with the provided web service (or your own) to allow users to perform the following CRUD operations:
    + View all robots (List/Index)
    + Create a new robot (Create)
    + View a given robot (Show)
    + Edit a given robot (Update)
    + Delete a given robot (Destroy)

#### [Peer Evaluation](peer-evaluation.md)

All members of the learning community, including the professor, will evaluate an assigned list of five submitted CRUD Applications, and will assign each peer project a score from 1 to 10. A weighted average of these individual scores will produce the overall Peer Evaluation Score.
