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
2. Find the countries that end with y
```sql
SELECT name FROM world
  WHERE name LIKE '%y'
```
3. Find the countries that contain the letter x
```sql
SELECT name FROM world
  WHERE name LIKE '%x%'
```
4. Find the countries that end with land
```sql
SELECT name FROM world
  WHERE name LIKE '%land'
  ```
5. Find the countries that start with C and end with ia
```sql
SELECT name FROM world
  WHERE name LIKE 'C%ia'
```
6. Find the country that has oo in the name
```sql
SELECT name FROM world
  WHERE name LIKE '%oo%'
```
7. Find the countries that have three or more a in the name
```sql
SELECT name FROM world
  WHERE name LIKE '%a%a%a%'
```
8. Find the countries that have "t" as the second character.
```sql
SELECT name FROM world
 WHERE name LIKE '_t%'
ORDER BY name
```
9. Find the countries that have two "o" characters separated by two others.
```sql
SELECT name FROM world
 WHERE name LIKE '%o__o%'
```
10. Find the countries that have exactly four characters.
```sql
SELECT name FROM world
 WHERE name LIKE '____'
```
11. Find the country where the name is the capital city.
```sql
SELECT name FROM world
 WHERE name = capital
```
12. Find the country where the capital is the country plus "City".
```sql
SELECT name FROM world
 WHERE capital = CONCAT(name, ' City')
```
13. Find the capital and the name where the capital includes the name of the country.
```sql 
SELECT capital, name FROM world 
WHERE capital LIKE CONCAT('%', name, '%')
```
14. Find the capital and the name where the capital is an extension of name of the country
```sql
SELECT capital, name FROM world
WHERE capital LIKE CONCAT('%', name, '%') AND capital> name
```
15. Show the name and the extension where the capital is an extension of name of the country.
```sql
SELECT name, REPLACE(capital, name, '') FROM world 
WHERE capital LIKE CONCAT('%', name, '%') AND capital > name;
```






## SELECT from NOBEL
## SELECT in SELECT
## SUM and COUNT
## JOIN
## More JOIN
## Using NULL
## Self JOIN
