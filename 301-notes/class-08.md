## Complete SQLBolt (Intro, Lessons 1-4, 13-18) FROM https://sqlbolt.com/
Note: CAPS aren't needed, but used so we know which words are SQL keywords vs names. Makes query easier to read.

`SELECT` (queries) - declares what data we are looking for.
When selecting multiples of something (e.g., title and director from movies example) you separate them with a comma. `SELECT title, director FROM movies;`. `SELECT * FROM movies` to select *all* info.

`WHERE` condition

```
SELECT col_name1, col_name2, …
FROM table_name
WHERE condition
    AND/OR another_condition
    AND/OR …;
```
Can use `BETWEEN...AND` for greater than x and less than y. 

All strings must be between quotes in SQL.

Can search text using case-insensitive string comparison and wildcard pattern matching. 
`= // !- // <>` - case sensitive for exact or not exact string comparison.
`LIKE` - case insensitive. Exact string comparison.
`NOT LIKE` - case insensitive. Exact string inequality. 
`NOT (...)` string exists in list
`NOT IN (...)` string doesn't exists in list.

Filtering and Sorting Queries
`DISTINCT` - discard duplicate values
`GROUP BY` - to be more specific.
`ORDER BY col_name ASC/DESC`- sorted alpha-numerically by value ascending or descending 
`LIMIT / OFFSET`
    - LIMIT - reduce the number of rows to return (ex. LIMIT 5 to get the first 5)
    - OFFSET - specify where to begin counting (the rows) from
    - Ex. LIMIT 5 (to get the first five) OFFSET 5 (to get the next five).

List all directors from movie list alphabetically without duplicates

```
SELECT DISTINCT col_name FROM movies
ORDER BY director ASC;
```

**Inserting Rows**
SQL schemas and how to add new data
`INSERT INTO tablename` to insert followed by `VALUES (values here), (more values);`

**Updating Rows**
`UPDATE tablename` to update data
`SET ` to set the data
`WHERE` apply the changes 'where' it satisfies the condition

Note: Best to write a test for the condition and try it using SELECT first to make sure the correct rows are being updated.

**Deleting rows**
`DELETE FROM tablename WHERE condition is this`

**Creating Tables**
`CREATE TABLE` to create table
`CREATE TABLE IF NOT EXISTS tablename`
    `column DataType (INTEGER, TEXT, BOOLEAN, BLOG, DATE,etc.) TableConstraint (ex. PRIMARY KEY, UNIQUE, NOT NULL, etc.) DEFAULT default_value,
    repeat if there is more,`

**Altering Tables**
`ALTER TABLE` statement adds, removes, or modifies columns and table constraints.
`ADD` to add
`DROP` to delete
`RENAME TO` rename 

**Dropping Tables**
`DROP IF TABLE EXITS tablename`
