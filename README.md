# mongo-maintain
Run your scripts in your mongodb with security for each environnement

## Download

[See here](http://4sh-projects.github.io/mongo-maintain/ "Download")

## For users :

### What to know ?

When you work on a project with mongo (or any other database), you will need to execute some scripts to populate db or update schema of your data. A script is useful because it can be shared with others developpers and can be launched in test and prodution environments. But when you develop you don't really want to take care if a new script must be launched or not. 

mongo-maintain is here to help you for that. The idea is to have a specific folder to store these scripts and launch mongo-maintain that will execute these scripts in the order defined by name of script (sow below explanation). mongo-maintain will create a collection (named mongomaintain) in your database to store execution informations about scripts : name, status, date, md5, error detail... 

The naming convention for scripts is :
* prefix: v
* version: Dots or underscores separate the parts, you can use as many parts as you like. Parts must be digit characters. Leading zeroes are ignored in each part
* separator: __ (two underscores)
* description: any characters
* suffix: .js

Example :
* v1__init.js
* v2.0.1__update.js
* v2_0_2__insert many documents.js
* v2_0.3__insert_one_document.js
* v002.0.004__delete.js

### How to use mongo-maintain ?

#### Command line

mongo-maintain program takes some arguments :
* __scripts__ -> path to the folder than contains scripts to launch
* __url__ -> url to connect to mongo
* __database__ -> database to connect to
* _user_ -> username to connect to mongo. Optional
* _password_ -> password of the user to connect to mongo. Optional

#### Java integration

Coming soon


## For devs :

### Install go

Defines GOPATH environnement variable

### Install mgo (mongo driver for go)

  $go get gopkg.in/mgo.v2

### Launch the code
  $ go run main.go mongo.go params.go script-file.go utils.go -scripts=./MongoMaintain -url=localhost:27017 -database=test

### Build the code
  $ go build

  $ ./mongo-maintain -scripts=/Users/dro/Documents/MongoMaintain -url=localhost:27017 -database=test2

### Cross compilation

Coming soon