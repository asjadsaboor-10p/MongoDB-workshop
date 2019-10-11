## Exercise 8 - Indexes

### Import collection

First import [companies](/data-sets) json.

```
c:\> mongoimport companies.json -d companyData - c companies --drop 
```

1. Write a query to find any company by `name` and note down its execution time along with the execution plan.

2. Write a query to create necessary index to reduce execution time of above query and check the execution time again.

3. Write a query to create an index to optimzie the following query

```
    db.companies.find({"funding_rounds.raised_amount": {$gt: 20000000},"founded_year":{$gt:2005}}, {funding_rounds:1})
```

4. Write a query to find companies with semiconductor business, Also the company must not be a startup. The query should return only company name and description.

Hint: create a text index