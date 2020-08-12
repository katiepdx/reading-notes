## SQLBolt Lessons 5-8 FROM https://sqlbolt.com/lesson/select_queries_review
5 - review 
**6 - Multi-Table Queries with JOINs**
Normalization - working across many databases. 
Primary key - used to identify that entity uniquely across the DB.
INNER JOIN is just JOIN

**7 - OUTER JOINs**
OUTER is used for SQL-92 compatibility. LEFT OUTER JOIN and LET JOIN. 
SELECT DISTINCT building FROM employees; - DISTINCT (different) only returns the building but without duplicating.

**8 - A short note on NULLs**
Best to reduce the possibility of NULLs.
WHERE (something) IS/IS NOT NULL

## Database Normalization (Explained in Simple English) FROM https://www.essentialsql.com/get-ready-to-learn-sql-database-normalization-explained-in-simple-english/
Database normalization - organize databases into tables and columns.
- Main reasons 
    - Minimize duplicate data
    - Avoid modification issues
    - Simplify searches

Duplicate info is difficult to maintain, increases storage, decreases performace.

Search and sort 

Forms of Database normalization - Progressive (3 normal forms) - 1NF, 2NF, 3NF
- First normal form
- Second normal form
- Third normal form

## Visual Representation of SQL Joins FROM https://www.codeproject.com/Articles/33052/Visual-Representation-of-SQL-Joins
- INNER JOIN 
- LEFT JOIN
- RIGHT JOIN 
- OUTER JOIN 
- LEFT JOIN EXCLUDING INNER JOIN 
- RIGHT JOIN EXCLUDING INNER JOIN 
- OUTER JOIN EXCLUDING INNER JOIN 

Think of two circles overlapping in the middle. 

```
//FROM SITE
SELECT <select_list>
FROM Table_A A
**RIGHT JOIN** Table_B B
ON A.Key = B.Key
```

- Inner join - most common one. Returns all the records from table A that have a match in table B. Overlap. 
- Left join - returns all records from table A regardless if there is a match on table B. 
- Right join - returns all records from table B regardless if there is a match on table A. 
- Full outer join / Full join - returns all records from both tables (A and B).
- Left excluding Join - records that match table A but do not match any in table B. 
- Right excluding Join - records that match table B but do not match any in table A. 
- Outer excluding JOIN - used for searching all the records in the table A and table B table that do not match. 

## Chapter 11 - Understanding Joins 
- JOIN lets you retrieve data from multiple tables in a single SELECT query.
- FROM left table JOIN right table ON something_id = id.
- Table aliases used to shorten names.
- CROSS JOIN - get all possible combinations
- SELF JOIN 
- INSERT INTO