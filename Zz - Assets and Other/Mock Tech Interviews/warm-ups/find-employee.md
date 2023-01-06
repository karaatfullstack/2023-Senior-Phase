# Technical Mock Interview

## Overview


### Question 

#### Find Employee (5 mins)

Write an SQL query to find names of employee start with ‘A’.

```sql

CREATE TABLE EMPLOYEES(
  ID INT PRIMARY KEY,
  FULL_NAME TEXT
);
```


#### Solution



```sql

SELECT * FROM EMPLOYEES WHERE FULL_NAME like 'A%';
```

More robustly, you can slightly alter this query to be case-insensitive:

```sql

SELECT * FROM EMPLOYEES WHERE FULL_NAME ilike 'a%';
```


### Notes

* N/A