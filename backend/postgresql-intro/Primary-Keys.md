# Primary Keys

Each table in our SQL schema should have a `PK` (primary key) column that will identify each row.

The **PK must be unique**. We generally use the `PK` column to query or update the database for a single row.

  

The `PK` will usually be the `ID` column, but it can also be any other column (username / email / phone ....)

It can also be a combination of more than one column, but that's not important right now.

  

There are a few ways to add a `PK`, but the simplest is to define it when you define your table:

  
```sql
CREATE TABLE Worker(
    email VARCHAR(80) NOT NULL PRIMARY KEY,
    username VARCHAR(20)
);
```

  

You'll note a couple of new things:

-   `NOT NULL` - this will force us to enter data when we do `INSERT INTO` - i.e. we cannot leave this field blank
-   `PRIMARY KEY` - this is the syntax to make a field a `PK`

  

----------

  

  

Another way to add a Primary Key is to set it as a number that _automatically increments_ with each new `INSERT` into the DB:

```sql
CREATE TABLE table_name(
    id SERIAL PRIMARY KEY,
    ...
);
```
  

This is similar to before, but now we're using `SERIAL` which automatically creates an auto-incrementing integer column - this means we **do not** need to pass in the `id` value when we `INSERT` a row; PostgreSQL handles it for us.
