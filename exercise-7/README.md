## Exercise 7 - aggrecations

Switch to `restraunts` collection

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