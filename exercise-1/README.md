## Exercise 1 - Mongo shell handson

1. Start mongo daemon with a non default port for e.g`27018` and non default data folder for e.g `c:\data\db`
2. Connect mongo shell to above daemon
3. Create a new database and name it `shelter`
4. Create a new collection named `animals`. The collection must have following fields
     ```
     - name
     - type  (cat,dog ..)
     - breed
     - status (adopted, orphaned)
     - age
     ```
5. Write a query to insert 6 records (1 parrot, 2 dogs, 3 cat) in `animals` collection
6. Write a query to find all `cats`
7. Write a query to update parrot's name to `Charlie`
8. Write a query to add a new nested object in all records who status is `adopted`
   ```
   owner: {
       name: "Owner Name"
       location: "karachi"
   }
   ```
9. Write a query to remove all `orphaned` records.
