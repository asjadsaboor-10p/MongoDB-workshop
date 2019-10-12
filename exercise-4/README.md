## Exercise 4 - Find operations deep dive - Part 1

### Import collection

First import [tv-shows](/data-sets) json.

```
c:\> mongoimport tv-shows.json -d movieData - c movies --jsonArray --drop 
```

`mongoimport` tool imports content from an Extended JSON, CSV, or TSV export created by mongoexport, or potentially, another third-party export tool.

Options

    -   -d  specify name of database
    -   -c specify name of collection
    -   --jsonArray specify for importing json Array
    -   --drop drops the collection before importing


Now the data has been imported, lets practise some find queries

1. Write a query to display all the documents.
2. Write a query to get total count of documents.
3. Write a query to display the fields name, type, language,  rating, and genres for all the documents.
4. Write a query to display the fields name, type, language,  rating, and genres, but exclude the field _id for all the documents.
5. Write a query to get count of all the movies in english language. 
6. Write a query to display the first 5 movies whose rating is greater than 8.
7. Write a query to display movies whose genres is comedy or horror
8. Write a query to display top 10 movies by rating in descending order.
9. Write a query to display top movies from 10th position to 20 in descending order.
10. Write a query to display movies whose runtime is between 30-60 minutes.
11. Write a query to display movies whose runtime is greater the 30 and genres is either Comedy or Horror and language is english.