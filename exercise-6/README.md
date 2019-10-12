### Exercise 6 - Update / Delete Operation Deep Dive continue


### Import collection

First import [users](/data-sets) json.

```
c:\> mongoimport users.json -d userData - c users --jsonArray --drop 
```

`mongoimport` tool imports content from an Extended JSON, CSV, or TSV export created by mongoexport, or potentially, another third-party export tool.

Options

    -   -d  specify name of database
    -   -c specify name of collection
    -   --jsonArray specify for importing json Array
    -   --drop drops the collection before importing


1. Write a query to update age of users whose age is null.
2. Write a query to increment age of all users by 1.
3. Write a query to add a new field `highFrequency` and set its value to true if a user has frequency greater than 2.
4. Write a query to add new field `weight` and set some value.
5. Write a query to rename `weight` field to `totalWeight`.
6. Write a query to remote `weight` key from all records.
7. Write a query to upsert new user with your name.
8. Write a query to insert hobby in your user record.
9. Write a query to remove first hobby from all user records.
10. Write a query to delete your user records.
11. Write a query to delete entire users collection.
