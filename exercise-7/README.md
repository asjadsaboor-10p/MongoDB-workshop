## Exercise 6 - Aggregation

In this exercise will will first practise aggregation stages on `universities` data , then we will move to a `restraunts` data set and create aggregation pipeline.


### Part 1

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

## Part 2

Now, let's switch to `restraunts` collection

1. Write an aggregation query to return total count of 'A' grades received by each restraunt.

The output should be as follows

```
{ "_id" : "Ponche Taqueria", "count" : 3 }
{ "_id" : "Place To Beach Cantina", "count" : 1 }
{ "_id" : "Homecoming", "count" : 3 }
{ "_id" : "Fordham Pizza & Pasta", "count" : 3 }

```


Hint , The order of the stages will be as follows

```
db.restaurants.aggregate([
    {$unwind: ...},
    {$match: ...
    {$addFields: ...},
    {$project: ...},
    {$group: ...}
])

```