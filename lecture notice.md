
Chapter 1: Introduction

Are you Behind a Firewall?
In order to continue in this course, you must be able to make outgoing requests from your computer to database servers we have set up in MongoDB Atlas. Those servers run on port 27017 in Amazon AWS.

Please confirm that port 27017 is not blocked by clicking http://portquiz.net:27017.

If successful, you will see a page load that indicates you can make outgoing requests on port 27017.

If a page does not load and your request eventually times out, outgoing traffic to port 27017 is probably blocked on your local network. If this is the case, please contact your IT department to see if there is a workaround or try to make the request from another location.

Other useful tests to perform if it seems that you have difficulty connecting would be:

Connect to the host and port of the Atlas cluster with:
telnet cluster0-shard-00-00-jxeqq.mongodb.net 27017
Simpler test to see if you can reach Atlas
ping cluster0-shard-00-00-jxeqq.mongodb.net

Lecture Notes
In this course we will make extensive use of MongoDB Compass for learning how to use MongoDB.

1. Please download Compass from the MongoDB Download Center . If you downloaded Compass before today, please make sure you are using Compass 1.15.4 (Stable) version or later and upgrade if necessary.

2. Install Compass on your computer from the download. Please, either update or install Compass 1.15.4 (Stable) version or later.

Launch Compass.
When Compass opens you will see a page titled "Connect to Host".

https://s3.amazonaws.com/edu-static.mongodb.com/lessons/M001/compass_connect_screen.png
Use the following information to complete this form, but do not click "Connect" yet.

Hostname: cluster0-shard-00-00-jxeqq.mongodb.net

Username: m001-student

Password: m001-mongodb-basics

Replica Set Name: Cluster0-shard-0

Read Preference: Primary Preferred

Click "Add to Favorites" and enter M001 RS as the Favorite Name. Adding this connection as a favorite will enable you to easily connect to our class MongoDB deployment after closing and restarting Compass at some point in the future.

Now, click "Connect" and load the databases in the M001 class MongoDB deployment.

Lecture Notes
Please use the following command to connect to the class Atlas cluster. You should issue this command in the cmd shell, the OSX Terminal application, or another command-line interface of your choice.

mongo "mongodb://cluster0-shard-00-00-jxeqq.mongodb.net:27017,cluster0-shard-00-01-jxeqq.mongodb.net:27017,cluster0-shard-00-02-jxeqq.mongodb.net:27017/test?replicaSet=Cluster0-shard-0" --authenticationDatabase admin --ssl --username m001-student --password m001-mongodb-basics
Note

While connecting to your MongoDB Atlas cluster, or any MongoDB server, from the mongo shell, you may see the following warning message:

... WARNING: shell and server versions do not match
This warning message can be safely dismissed for the purposes of this course. The purpose of this message is to let you know that the version of the server/cluster that you are connecting to has a different version then the one of your client mongo shell. Given the different versions between server and client, there might be some incompatibility commands/features not supported by either the client shell or the server. However, in this course, you will not encounter any such issue.
