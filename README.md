# Developer Technical Test @ Dataiku

## Some data

You will find a NodeJS server application in [/resources/census-server-dataiku.zip](https://github.com/dataiku/census-challenge/blob/main/resources/census-server-dataiku.zip?raw=true)

The server exposes a SQLite database containing demographical record data. It provides a REST API with 2 endpoints
- `GET /api/columns` returns the list of all columns
- `GET /api/data/<columnName>` returns the list of all unique values found in the database for the column named <columnName>, and for each value its count and the average of the age.

Example: `GET /api/data/sex` returns
```
{
  "count":2,
  "values":[
    { "id":"Female", "count":103984, "average":36 },
    { "id":"Male","count":95539, "average":33 }
   ]
}
```
which means that the database contains only 2 different values in the "sex" column ("Male" and "Female"),
and that there are 103984 women and 95539 men with a respective age of 36 and 33 on average.

## The challenge

Your goal is to create a small web application to visualize data using this API.
 
The application should allow the user to select a column from the database. It should then display - as a table - for each value of the variable, the count of rows with this value and the average of the "age" value. The values should be sorted by decreasing count. It is OK to clip and only keep the first 100 values for a variable. 

It should also display next to the table, one (or 2) charts displaying the same data.

Here is how it could look like:

![charts](https://github.com/dataiku/census-challenge/blob/main/resources/charts.png)
 
Your application should be a single-page web application, i.e. the user must be able to change
the variable without reloading the page.
 
## Final note
There is absolutely no constraint on the technological stack that you might choose to achieve this. Choose whichever you master and think is best suited for the task.

We are looking for **high quality code and visual rendering**: typically something that you would put into production and be proud of.

Have fun!
