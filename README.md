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
1. Change the query shown so that it displays Nobel prizes for 1950.
```sql
SELECT yr, subject, winner FROM nobel
 WHERE yr = 1950
```

2. Show who won the 1962 prize for literature.
```sql
SELECT winner FROM nobel
 WHERE yr = 1962 AND subject = 'literature'
```

3. Show the year and subject that won 'Albert Einstein' his prize.
```sql
SELECT yr, subject FROM nobel
WHERE winner = 'Albert Einstein'
```
4. Give the name of the 'peace' winners since the year 2000, including 2000.
```sql
SELECT winner FROM nobel 
WHERE subject = 'peace' AND yr>1999
```
5. Show all details (yr, subject, winner) of the literature prize winners for 1980 to 1989 inclusive.
```sql
SELECT * FROM nobel
WHERE subject = 'literature' AND yr>1979 AND yr<1990
```
6. Show all details of the presidential winners:
```sql
SELECT * FROM nobel
 WHERE winner IN ('Theodore Roosevelt', 'Woodrow Wilson', 'Jimmy Carter', 'Barack Obama')
```
7. Show the winners with first name John
```sql
SELECT winner FROM nobel
WHERE winner LIKE 'John%'
```
8. Show the year, subject, and name of physics winners for 1980 together with the chemistry winners for 1984.
```sql
SELECT yr, subject, winner FROM nobel
WHERE (yr = 1980 AND subject ='physics') OR (yr=1984 AND subject = 'chemistry')
```
9. Show the year, subject, and name of winners for 1980 excluding chemistry and medicine
```sql
SELECT yr, subject, winner FROM nobel
WHERE yr = 1980 AND subject <> 'chemistry' AND subject <> 'medicine'
```
10. Show year, subject, and name of people who won a 'Medicine' prize in an early year (before 1910, not including 1910) together with winners of a 'Literature' prize in a later year (after 2004, including 2004)
```sql
SELECT yr, subject, winner FROM nobel
WHERE (yr<1910 AND subject = 'Medicine') OR (yr>2003 AND subject = 'Literature')
```
11. Find all details of the prize won by PETER GRÜNBERG
```sql
SELECT * FROM nobel
WHERE winner = 'PETER GRÜNBERG'
```
12. Find all details of the prize won by EUGENE O'NEILL
```sql
SELECT * FROM nobel
WHERE winner = 'EUGENE O''NEILL'
```
13. List the winners, year and subject where the winner starts with Sir. Show the the most recent first, then by name order.
```sql
SELECT winner, yr, subject FROM nobel
WHERE winner LIKE 'Sir%'
ORDER BY yr desc, winner
```
14. The expression subject IN ('chemistry','physics') can be used as a value - it will be 0 or 1. Show the 1984 winners and subject ordered by subject and winner name; but list chemistry and physics last.
```sql
SELECT winner, subject FROM nobel
WHERE yr=1984
ORDER BY subject IN ('Physics','Chemistry'), subject, winner
```









## SELECT in SELECT
## SUM and COUNT
## JOIN
## More JOIN
## Using NULL
## Self JOIN
