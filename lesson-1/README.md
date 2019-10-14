# MongoDB Shell Basics
The goal is to get a basic idea of Mongo Shell commands and how to use them

### 1. Start mongo daemon 
```
C:\> net start MongoDb  // if installed as windows service

OR 

C:\> mongod  // PATH variable should be set correctly

OR

C:\> "C:\Program Files\MongoDB\Server\4.2\bin\mongo.exe"
```

### 2. Start mongo shell
```
C:\> mongo
```

Note: This will connect using the default port `27017`. Use `--port` for specifying a different port.

You should get something similar to this:

```
MongoDB shell version v4.2.0
connecting to: mongodb://127.0.0.1:27017
Implicit session: session { "id" : UUID("2323-8as8-23aa-8fsa") }
MongoDB server version: 4.2.0
>
```

From this moment on, everything you’ll type will be executed in the mongo shell.

### 3. List databases
Your server may host several databases you have access to.

```
> show dbs
admin      0.000GB
config     0.000GB
local      0.000GB
```

### 4. Find the database you're using
```
> db
test
```

### 5. Switch / Create a database
To switch the database, you can run the `use` command.
If the database doesn't exist, it will be created for you.

```
> use shop

> db
shop
```

Note: `show dbs` will not show the new database because it is empty.

### 6. Create collection
```
> db.createCollection("products")

OR

> db.products.insertOne({name:"paper",price:10, description:"A4 size papers"})
```

Collections can be capped by setting size / max documents.

### 7. Run few insert commands to insert some data
```
> db.products.insertOne({name:"Book",price:10, description:"A book"})
```

### 8. List collections
```
> show collections
products
```

### 9. Find all documents
```
> db.products.find()

> db.products.find().pretty()
```

### 10. View logs
```
> show log global
```

### Some more commands
You can always use `help` command to get list of all available commands.

To list database specific commands, you may use `db.help()`.

```
> db.dropDatebase()
> db.getState()

```
