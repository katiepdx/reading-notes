## Inside a Computer FROM https://edu.gcfglobal.org/en/computerbasics/inside-a-computer/1/
- Circuit board - motherboard 
    - contains CPU - the processor, the brain of the computer
        - gets hot so heat sink draws heat away 
        - measured in MHz megahertz or GHz gigahertz.
    - RAM - short term memory. Can't save to this. RAM cleared when computer is shutoff. 
    - Hard drive - long term memory. New computers use SSD (faster, more durable, more expensive)
    - Expansion slots (video cards for graphics, sound card, wireless card, etc.) - most laptops don't have this. 
    - Power supply unit - for powering computer. Laptop has built in battery. 

## PostgreSQL INSERT FROM https://www.postgresqltutorial.com/postgresql-insert/
`INSERT` to insert a new row into a table. 

```sql
-- EXAMPLE FROM SITE
-- Insert columns into a table. 
INSERT INTO table_name(column1, column2, …)
VALUES (value1, value2, …)
RETURNING output_expression AS output_name;
-- RETURNING is optional. AS is used to rename. 
```

## PostgreSQL SELECT FROM https://www.postgresqltutorial.com/postgresql-select/
`SELECT` to query data from a table.
SQL is not case sensitive. 

**Select followed by the following:**
- DISTINCT
- WHERE
- LIMIT / FETCH 
- GROUP BY
- HAVING 
- INNER JOIN / LEFT JOIN / FULL OUTER JOIN / CROSS JOIN 
- UNION / INTERSECT / EXCEPT 

```sql 
-- EXAMPLES FROM SITE
-- Selects all the first names from the customer table. 
SELECT first_name FROM customer;

-- Can select multiple column names by separating them with commas. 
SELECT
   first_name,
   last_name,
   email
FROM
   customer;

-- NOTE: Select * // star is for all. 

-- Concatenation || to add two columns together. The following returns the first and last name together in one column and email. 
SELECT 
   first_name || ' ' || last_name,
   email
FROM 
   customer;
```

## PostgreSQL UPDATE FROM https://www.postgresqltutorial.com/postgresql-update/
`UPDATE` is for modifying data in a table. Used with `SET` keyword. Can also be used with `RETURNING` clause. 

```sql 
-- Update the animal field to dog where the owner_id is equal to 3. Once updated, you will see "UPDATE 1" to verify that it was updated. Add a RETURNING * under the WHERE line to get the entire table back after making the update. 
UPDATE table_name_animals
SET column_name_animal = 'dog' 
WHERE owner_id = 3;
```

## PostgreSQL DELETE FROM https://www.postgresqltutorial.com/postgresql-delete/
`DELETE` used to delete from a table. Commonly used as `DELETE FROM` with the `WHERE` clause. Can also be used with the `RETURNING` keyword. 

```sql
-- EXAMPLE FROM SITE

-- delete the row where id is 7. NOTE: if id does not exist, you will see "DELETE 0". If successful, "DELETE 1"
DELETE FROM links
WHERE id = 7
-- add the following to get the deleted row back.
RETURNING *;

-- DELETE multiple rows using the IN keyword. 
DELETE FROM links
WHERE id IN (value1, value2)

-- DELETE ALL ROWS FROM TABLE 
DELETE FROM links;
```