# REST API

> NOTE: This project is optional. Don't attempt it unless you are comfortable with your implementation of the CRUD Application project. If you do manage to complete this REST API project, you are free to configure your CRUD Application to use it instead of the provided API.

Implement and document a REST API which responds to a specific set of HTTP requests and processes those requests appropriately. The API should respond with data in the JSON format (not XML or other formats). It should be implemented as an Express application hosted on a Heroku application server.

## Instructions

For detailed instructions, follow these checkpoint exercises in order:

  1. [Checkpoint I: Serving Static Responses to GET Requests](/projects/rest-api/checkpoints/static-responses/checkpoint.md)
  2. [Checkpoint II: Seeding the Database](/projects/rest-api/checkpoints/database-seeding/checkpoint.md)
  3. [Checkpoint III: Serving Dynamic Responses to GET Requests](/projects/rest-api/checkpoints/dynamic-responses/checkpoint.md)
  4. [Checkpoint IV: Processing Other Requests](/projects/rest-api/checkpoints/receiving-data/checkpoint.md)

Also feel free to refer to the [working implementation](https://southernct-443-robots-api.herokuapp.com/) of this API, and/or that application's [source code](https://github.com/prof-rossetti/robots-api-express/) for additional information.

### Implementation

#### API Endpoints

Your API should respond to the following requests:

action name | request method | URL endpoint | appropriate server action | response contents
--- | --- | --- | --- | ---
Index | GET | /api/robots | Query the database to retrieve all records in the robots table. | An array of JSON objects, each of which represents a robot.
Show | GET | /api/robots/`:robotId` | Query the database to retrieve the record in the robots table which matches the provided identifier. | A JSON object representing the given robot.
Create | POST | /api/robots | Create a new record in the robots table based on the data passed by the client. | A simple "OK" message, or optionally a JSON object representing the recently-created robot.
Update | PUT | /api/robots/`:robotId` | Update the record in the robots table which matches the provided identifier, using the data passed by the client. | A simple "OK" message, or optionally a JSON object representing the recently-updated robot.
Destroy | DELETE | /api/robots/`:robotId` | Remove from the robots table the record which matches the provided identifier. | A simple "OK" message, or optionally a JSON object representing the recently-deleted robot.

#### Hosting

Push your Express application's source code to a Heroku application server.

### Documentation

In the root directory of your project's repository, whether in the README.md file or another file called `DOCUMENTATION.md`, provide instructions for how clients should expect to interface with your API. Specifically list all of your API's URL endpoints, and for each describe what is supposed to happen when a client makes a request to that endpoint. Make sure to include the type of request they are supposed to make, and an example response they might expect to receive in return. For example:

```` md
# API Documentation

## Endpoints

### List Robots

Issue a GET request to **/api/robots** to retrieve a list of all robot records currently in the database.

Example response:

    [
      {id:1, name: "my bot", description:"does stuff"}, // etc.
      {id:2, name: "other bot", description:"does other stuff"}, // etc.
      // etc.
    ]

### Show Robot

etc.
````

## Submission Instructions

When your project is ready for evaluation, add its identifying information, including your GitHub username, a link to your site's repository, and a link to your hosted site, to the [submissions list](submissions.md). Use the following workflow to accomplish this:

  1. Fork [this repository](https://github.com/SCSU-CSC-Department/201701-csc-443-01/) to your own account.
  * Edit the submissions list in your forked repo via the online editor, or by downloading your forked repo, making local commits, and pushing them back up to GitHub.
  * Submit a Pull Request for your changes to be merged into this repo.

> NOTE: If you would prefer for any reason to submit your work privately, you may alternatively send the professor your links via email or Slack DM. Your project will still be evaluated, and peer-evaluated, but its identifying information will not be publicly accessible as part of this course repository.

Also be prepared to deliver a 5-10 minute presentation to demonstrate usage of your website and describe your planning and design process, as desired.

## Evaluation Criteria

Your REST API will be evaluated according to the following criteria:

criteria | weight
--- | ---
Documentation | 25%
Implementation | 75%

Partial credit may be given to highlight areas of improvement.

### Documentation Evaluation

Your REST API documentation will be evaluated for presence, clarity, and comprehensiveness. It should include instructions on how to use all API endpoints.

### Implementation Evaluation

Your REST API implementation will be evaluated based on its demonstrated ability to meet all of the following criteria:

  1. Is hosted on the Internet and publicly accessible.
  2. Appropriately processes and provides a response for each HTTP request specified in the project instructions.
