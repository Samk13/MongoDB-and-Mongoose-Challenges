FCC Mongo & Mongoose Challenges
===============================


<a href="https://learn.freecodecamp.org/apis-and-microservices/mongodb-and-mongoose" target="_blank">Introduction to the MongoDB</a>
=============================================


conditional find in database : 
how we write it : 
db.employees.find(
{"Age": {$ne: "30"}
})

whriting conditions start with $ : 
$gt  means : greater then
$lt  means : less then
$lte means : less then or equal
$gte means : greater then or equal
$ne  means : not equal
$or: [{"condition1":"1"},{"condition 2":"2"}]  means : or ! 



db.employees.find({
    "Skill":"MongoDB", $or: [{"Salary": "85000"},{"Salary": "80000"}]
}).pretty()
