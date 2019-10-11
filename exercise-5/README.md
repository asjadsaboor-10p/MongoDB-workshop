## Exercise 5 - Find operations deep dive - Part 2

### Import collection

First import [restraunts](/data-sets) json.

```
c:\> use restrauntdata
c:\> mongoimport restraunts.json - c restraunts
```

`mongoimport` tool imports content from an Extended JSON, CSV, or TSV export created by mongoexport, or potentially, another third-party export tool.

Options

    -   -d  specify name of database
    -   -c specify name of collection
    -   --jsonArray specify for importing json Array
    -   --drop drops the collection before importing


1.  Write a query to find the restaurants who achieved a score more than 90.
2.  Write a query to display the next 5 restaurants after skipping first 5 which are in the borough Bronx.
3.  Write a query to find the restaurants that achieved a score is more than 80 but less than 100.
4.  Write a query to find the restaurants which locate in a latitude value less than -95.754168.
5.  Write a query to find the restaurants that do not prepare any cuisine of 'American' and their grade score more than 70 and lattitude less than -65.754168.
6.  Write a query to find the restaurant Id, name, borough and cuisine for those restaurants which belong to the borough Staten Island or Queens or Bronxor Brooklyn.
7.  Write a query to find the restaurant Id, name, borough and cuisine for those restaurants which achieved a score which is not more than 10.
8.  Write a MongoDB query to know whether all the addresses contains the street or not.
