## Exercise 7 - aggrecations

Switch to `restraunts` collection

1. Write an aggregation query to return total count of 'A' grades received by each restraunt.

The output should be as follows

```
{ "_id" : "Ponche Taqueria",grade:"A", "count" : 3 }
{ "_id" : "Place To Beach Cantina", grade:"A","count" : 1 }
{ "_id" : "Homecoming", grade:"A","count" : 3 }
{ "_id" : "Fordham Pizza & Pasta",grade:"A", "count" : 3 }

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
