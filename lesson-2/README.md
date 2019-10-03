# CRUD Basics

### Create a database
```
> use airport
```


## Insert

### 1. Insert 2 documents in  collection `flights` using insertOne.
```
>db.flights.insertOne({
    "departureAirport": "KHI",
    "arrivalAirport": "LHR",
    "aircraft": "Airbus A380",
    "distance": 12000,
    "intercontinental": true
  })

>db.flights.insertOne({
    "departureAirport": "LHR",
    "arrivalAirport": "ISL",
    "aircraft": "Airbus A380",
    "distance": 12000,
    "intercontinental": true
  })
```

### 2. Insert 25 passengers in collection `passengers` using insertMany

```
> db.passengers.insertMany([
    {
    "name": "Max Schwarzmueller",
    "age": 29
  },
  {
    "name": "Manu Lorenz",
    "age": 30
  },
  ....
])
```

### 3. Insert a new flight by providing a ID

```
>db.flights.insertOne({
    "_id":"LHR-MUL-1"
    "departureAirport": "LHR",
    "arrivalAirport": "MUL",
    "aircraft": "Airbus A380",
    "distance": 12000,
    "intercontinental": true
  })
```

## Find


### 1. Find all documents

```
>db.flights.find()

>db.passengers.find()
```

Notice that not all passengers will be returned. thats because find returns only top 20 records with cursor. user `it` to return next set of records.

to get all records use toArray()

```
>db.passengers.find().toArray()
```

### 2. Find a document by ID using `findOne`

```
>db.flight.findOne({_id:"LHR-MUL-1"})

```

to return specific fields we can use mongo projections

```
>db.flight.findOne({_id: "LHR-MUL-1"}, {departureAirport:1, arrivalAirport:1 })

```

### Update 

### 1. Update single document  

```
db.flight.updateOne({_id:"LHR-MUL-1"}, {
    $set: { aircraft: "Boeing 777"}
})
```

### 2. Update all documents

```
db.flight.updateMany({}, {
    $set: { aircraft: "Boeing 777"}
})

```

### 3. Replace a document

```
db.flight.replaceOne({_id:"LHR-MUL-1"}, { message: "Hello World"})

OR

db.flight.update({_id:"LHR-MUL-1"}, { message: "Hello World"})
```


## Delete

### 1. Delete single record

```
> db.flight.deleteOne({_id: "LHR-MUL-1"})
```


### 2. deleting the whole collection
```
> db.passengers.drop()
```