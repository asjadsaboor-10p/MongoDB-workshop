## Exercise 1 - Mongo shell handson

1. Start mongo daemon with a non default port for e.g`27018` and non default data folder for e.g `c:\data\db`
2. Connect mongo shell to above daemon
3. Create a new database and name it `shelter`
4. Create a new capped collection named `animals` with document size limit of 6 documents. The collection must have following fields
     ```
     - name
     - type  (cat,dog ..)
     - breed
     - status (adopted, orphaned)
     - age
     ```
5. Insert 6 records (1 parrot, 2 dogs, 3 cat) in `animals` collection
6. Get all cats
7. Update parrot's name to `Charlie`
8. Add a new nested object in all records who are adopted
   ```
   owner: {
       name: "Owner Name"
       location: "karachi"
   }
   ```
9. Add another records . (should remove the oldest one)
10. remove all orphened records.
