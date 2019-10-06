## Exercise 7 - Aggregation 

In this lesson will will first practise aggregation pipeline and mapReduce.


### Part 1 - Aggregation pipeline

Import the `universities.json` from data-sets folder.


1. write an aggregation query to match universities who are in Salmanaca, Spain.

```
db.universities.aggregate([
{ $match : { country : 'Spain', city : 'Salamanca' } }
])

```

2. write an aggregation query to return only `country`, `city`, `name`.

```
db.universities.aggregate([
  { $project : { _id : 0, country : 1, city : 1, name : 1 } } ])


```

3. write  an aggregation query to unwind students from universities collection

```
db.universities.aggregate([
  { $unwind : '$students' }
])

```

4.  Write an aggregation query to return numbers students by year.

```
db.universities.aggregate([
  { $match : { name : 'USAL' } },
  { $unwind : '$students' },
  { $project : { _id : 0, 'students.year' : 1, 'students.number' : 1 } },
  { $sort : { 'students.number' : -1 } }
])


```

5. Write an aggregatoin query to get the total number of students that have ever belonged to each one of the universities in descending order?

```
db.universities.aggregate([
  { $unwind : '$students' },
  { $group : { _id : '$name', totalalumni : { $sum : '$students.number' } } },
  { $sort : { totalalumni : -1 } }
])


```

-------------------------------------

### Part 2 - mapReduce

1. Insert following students data using insertMany

```
[
{"name" : "Asjad", "subject" : "science", "marks" : 68},
{"name" : "Asjad", "subject" : "maths", "marks" : 98 },
{"name" : "Asjad", "subject" : "sports", "marks": 70},
{"name" : "Umair", "subject" : "science", "marks": 75},
{"name" : "Umair", "subject" : "maths", "marks": 85},
{"name" : "Umair", "subject" : "sports", "marks": 82},
{"name" : "Owais", "subject" : "science", "marks": 80},
{"name" : "Owais", "subject" : "maths", "marks": 90},
{"name" : "Owais", "subject" : "sports", "marks": 40},

]

```

2. create map function.

```
var map = function() {emit(this.name,this.marks);};

```

3. create Reduce function.


```
var reduce = function(name,marks) {return Array.sum(marks);};
```


4. Write a query using mapReduce


```
db.students.mapReduce(
map,
reduce,
    { out: "totals" }
);

```


You will get following output

```
{
    "result" : "totals",
    "timeMillis" : 599,
    "counts" : {
        "input" : 9,
        "emit" : 9,
        "reduce" : 3,
        "output" : 3
    },
    "ok" : 1
}
```

5. Now lets run find on the newly created collectoin `totals`.

```
db.totals.find()

{ "_id" : "Asjad", "value" : 243 }
{ "_id" : "Umair", "value" : 235 }
{ "_id" : "Owais", "value" : 243 }

```