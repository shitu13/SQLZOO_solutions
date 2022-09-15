# SQLZOO Solutions

## Sections:
1. [SELECT basics](#select-basics)
2. [SELECT from WORLD](#select-from-world)
3. [SELECT from NOBEL](#select-from-nobel)
4. [SELECT in SELECT](#select-in-select)
5. [SUM and COUNT](#sum-and-count)
6. [JOIN](#join)
7. [More JOIN](#more-join)
8. [Using NULL](#using-null)
9. [Self JOIN](#self-join)

## SELECT basics

1. Introducing the world table of countries
```sql
SELECT population FROM world
  WHERE name = 'Germany'
```
2. Scandinavia
```sql
SELECT name, population FROM world
  WHERE name IN ('Sweden', 'Norway', 'Denmark');
```
3. Just the right size
```sql
SELECT name, area FROM world
  WHERE area BETWEEN 200000 AND 250000
```

## SELECT from WORLD
1. Find the country that start with Y
```sql
SELECT name FROM world
  WHERE name LIKE 'Y%'
```

## SELECT from NOBEL
## SELECT in SELECT
## SUM and COUNT
## JOIN
## More JOIN
## Using NULL
## Self JOIN
