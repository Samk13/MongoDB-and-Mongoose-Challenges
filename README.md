FCC Mongo & Mongoose Challenges
===============================


<a href="https://learn.freecodecamp.org/apis-and-microservices/mongodb-and-mongoose" target="_blank">Introduction to the MongoDB</a>
=============================================


conditional find in database : 
how we write it : 
db.employees.find(
{"Age": {$ne: "30"}
})

Modifier	Description
$gt	Greater than
$lt	Less than
$gte	Greater than or equals
$lte	Less than or equals
$in	Check for existence in an array, similar to the 'in' SQL operator.

$or: [{"condition1":"1"},{"condition 2":"2"}]  means : or ! 



db.employees.find({
    "Skill":"MongoDB", $or: [{"Salary": "85000"},{"Salary": "80000"}]
}).pretty()


# Document creation examples

```javascript
var person1 = {name:"John Doe", age:25};
var person2 = {name:"Jane Doe", age:26, dept: 115};
```

Creating collections
```javascript
db.employees.save(person1);
db.employees.save(person2);
```
# A simple MongoDB query
```javascript
> db.employees.find();
// returns
[ 
  {   "_id" : {   "$oid" : "4e363c4dcc93747e68055fa1"   },   
        "name" : "John Doe",   "age" : 25   },
  {   "_id" : {   "$oid" : "4e363c53cc93747e68055fa2"   },   
        "name" : "Jane Doe",   "dept" : 115,   "age" : 26   }
]
```
# Query by one search parameter

```javascript
> db.employees.find({name: "John Doe"});
// returns
[ 
  {   "_id" : {   "$oid" : "4e363c4dcc93747e68055fa1"   },   
  "name" : "John Doe",   "age" : 25   }
]
```
# Query for employees with an age greater than 25
```javascript
> db.employees.find({age:{'$gt':25}});
// returns
[ 
  {   "_id" : {   "$oid" : "4e363c53cc93747e68055fa2"   },   
  "name" : "Jane Doe",   "dept" : 115,   "age" : 26   }
]
```
 # Update an entire record

```javascript
> db.employees.update({
    name:"John Doe",  // Document to update
    {name:"John Doe", age:27} // updated document
  });
  ```
 # Update a single value in a record
```javascript
> db.employees.update({name:"John Doe", 
     { '$set': {age:27} }
  });
```
# Remove John Doe from the employees collection
```javascript
> db.employees.remove({"name":"John Doe"});
> db.employees.find();
// returns
[ 
  {   "_id" : {   "$oid" : "4e363c53cc93747e68055fa2"   },   "name" : "Jane Doe",   
      "dept" : 115,   "age" : 26   }
]
```

