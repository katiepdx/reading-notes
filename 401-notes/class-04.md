## PostgreSQL Joins FROM https://www.postgresqltutorial.com/postgresql-joins/
**Joins**
- INNER JOIN 
- LEFT JOIN 
- RIGHT JOIN 
- FULL OUTER JOIN
- CROSS JOIN 
- NATURAL JOIN 
- SELF-JOIN (special)

**Inner join example**
```sql
-- EXAMPLE FROM SITE
-- Compares basket_a and joins basket_b. 
-- If fruit_a and fruit_b values are the same, a new row is created that has both values.  
SELECT
    a,
    fruit_a,
    b,
    fruit_b
FROM
    basket_a
INNER JOIN basket_b
    ON fruit_a = fruit_b;
```

**Left join example**
```sql
-- EXAMPLE FROM SITE
-- Compares basket_a and joins basket_b. 
-- If fruit_a and fruit_b values are the same, a new row is created that has both values. If the values are NOT THE SAME, all the rows from fruit_a are kept but the values for column b and fruit_b are filled with null. 
SELECT
    a,
    fruit_a,
    b,
    fruit_b
FROM
    basket_a
LEFT JOIN basket_b 
   ON fruit_a = fruit_b;
-- Added WHERE returns the rows with NULL values. 
WHERE b IS NULL;
```

**Right join example**
```sql
-- EXAMPLE FROM SITE
-- Compares basket_b and joins basket_a. 
-- Opposite left join. If values are equal, they are joined. If fruit_b does not have a match with fruit_a, then fruit_a and a is filled with null. 
-- NOTE: Table output is still "a, fruit_a, b, fruit_b". 
SELECT
    a,
    fruit_a,
    b,
    fruit_b
FROM
    basket_a
RIGHT JOIN basket_b ON fruit_a = fruit_b;
-- Added WHERE returns the rows with NULL values. 
WHERE a IS NULL;
```

**Full outer join example**
```sql
-- EXAMPLE FROM SITE
-- returns all rows from both tables. Rows with out matches are filled with NULL. 
SELECT
    a,
    fruit_a,
    b,
    fruit_b
FROM
    basket_a
FULL OUTER JOIN basket_b 
    ON fruit_a = fruit_b;

-- Added WHERE returns the rows with NULL values. 
WHERE a IS NULL OR b IS NULL;
```


## One-to-one (data model) FROM https://en.wikipedia.org/wiki/One-to-one_(data_model)
One-to-one is a relationship between the two entities A and B. 
This is the relationship between two entities. One element (A) only has one element (B). 
- Database: One table row is linked to only one row in another table. 
- A country only has one capital. 1 to 1. 

## One-to-many (data model) FROM https://en.wikipedia.org/wiki/One-to-many_(data_model)
One-to-many is a relationship between the two entities A and B. . 
(A) can have many of (B). Example: A book can have many pages. Database: One table row (A) can be linked to MANY rows in another table (B). 

There is also *many-to-one*, the opposite of one-to-one. For example, student and projects. A project can have many students and a student can be on many projects. 

## Many-to-many (data model) FROM https://en.wikipedia.org/wiki/Many-to-many_(data_model)
- In Database Management Systems (DBMS), a many-to-many example is an author (A) can write many books (B) and a book (B) can have many authors (A).
    - implemented using *associative tables (AKA join tables)*. 
        - two one-to-many tables joined. 
    - (A) [Books -- **Authors**] (B) [**Books** -- Authors]
    - Authors/Books join