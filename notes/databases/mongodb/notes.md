# MongoDB Overview (Optional)

Databases are not within the scope of this course. But if you're already somewhat familiar with databases and database management and you're attempting the optional extra credit project: then you'll probably benefit from a brief overview of [MongoDB](https://www.mongodb.com/).

> MongoDB stores data using a flexible document data model that is similar to JSON. Documents contain one or more fields, including arrays, binary data and sub-documents. Fields can vary from document to document. This flexibility allows development teams to evolve the data model rapidly as their application requirements change. When you need to lock down your data model, optional document validation enforces the rules you choose. - [MongoDB website](https://www.mongodb.com/what-is-mongodb)

Source Code: https://github.com/mongodb/mongo.

Documentation:

  + [Mongo Shell](https://docs.mongodb.com/manual/mongo/)
  + [CRUD Operations](https://docs.mongodb.com/manual/crud/)

## Installation

Mac OS:

```` sh
brew install mongodb
brew services start mongodb
````

Windows OS:

```` sh
# TBA
````

## Usage

```` sh
which mongo
mongo --version
mongo
> db # to show the active database
> show dbs # to show all databases
> use myNewDatabase # create/use a new database
> show collections # list all collections in the current database
> db.getCollectionNames() # list all collections in the current database (alternate)
> db.myCollection.insert( { x: 1 } ); # insert a new record
> db.myCollection.insert( { y: 2 } );
> db.myCollection.find().pretty() # print collection
> db.myCollection.find({x:1}).pretty() # find a record matching given query conditions
> exit
````
