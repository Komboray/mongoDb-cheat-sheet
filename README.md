# mongoDb-cheat-sheet
This is a cheat sheet that has all the simple commands used to connect to mongoDb database. 

//This is a non-relational database that uses the structure of DATABASE-> COLLLECTION -> DOCUMENTS -> FIELDS

//NOTE: mongoDb is used in the json format i.e, list[] then maps{} which are inside the maps e.t.c

//You need to install the mongoDb shell and the community version before you start https://www.mongodb.com/try/download/community

//Though we are programmers, we definetly need the shell https://www.mongodb.com/docs/mongodb-shell/install/

1.//In the shell such as in screenshot (53).png in my files, run $mongosh

2.$ cls - clears the screens

3.$ exit - exits the the mongodb

4. $ show dbs  //shows the databases that you have in mongoDb
5. 
6. $ use school  //creates a database called school
7. 
8. $ db.createCollection("students")  //creates a collection in the database
 
9. $ db.dropDatabase()   //drops the database
 
10. db.students.insertOne({
            name: "James",
            gpa: 3.2,
            age: 30,})
            
11. db.students.find()  //prints out the document that you have created
12. db.students.insertMany( [{},{},] ) - create a list of maps. A map is like the one in the 10th step


13.db.students.insertOne({
                           name:"James",
                           gpa: 3.2,
                           age: 30,
                           graduationDate: null,
                           courses:[ "Biology", "Chemistry"],
                           address: {
                           street: "123, street",
                           city: "Bikini" }
                           })
14.db.students.find({}, {_id:false, name: true}) //returns every document but only with the name

15. db.students.find({gpa:4.0}) //gets the document with the gpa of 4.0 

16. db.students.find().sort({gpa:-1}).limit(1) //Gets the documents with gpa and they are limited only to one

17. db.students.updateOne({name:"James"}, {$set:{fullTime:true}}) //it updates the document with the fulltime variable, if it is not there it creates it
 
18. db.students.deleteOne({name: "Jame"})
 
19. db.students.deleteMany({registerDate: {$exists: false}})
            


