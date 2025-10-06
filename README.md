# SQL-Easy Challenges

**Platform:** SolveSQL | HackerRank

**Link:** https://www.hackerrank.com/domains/sql?filters%5Bstatus%5D%5B%5D=unsolved&badge_type=sql 

### Weather Observation Station 3
**Problem::** Query a list of CITY names from STATION for cities that have an even ID number. Print the results in any order, but exclude duplicates from the answer.

**Solution:** 
```sql
SELECT DISTINCT city
FROM station
WHERE id/2 = 0;
```

###  Weather Observation Station 4
**Problem::** Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table.

**Solution:** 
```sql
# Finding Shortest City Name
SELECT city, LENGTH(city) AS city_namelength
FROM station
ORDER BY city_namelength ASC, city ASC
LIMIT 1;

# Finding Longest City Name
SELECT city, LENGTH(city) AS city_namelength
FROM station
ORDER BY city_namelength DESC, city DESC
LIMIT 1;
```

### Weather Observation Station 5
**Problem::** Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from STATION. Your result cannot contain duplicates.

**Solution:** 
```sql
# Start by separating vowels into one
SELECT DISTINCT city
FROM station
WHERE city LIKE 'A%';

SELECT DISTINCT city
FROM station
WHERE city LIKE 'E%';

SELECT DISTINCT city
FROM station
WHERE city LIKE 'I%';

SELECT DISTINCT city
FROM station
WHERE city LIKE 'O%';

SELECT DISTINCT city
FROM station
WHERE city LIKE 'U%';
```

### Weather Observation Station 8
**Problem::** Query the list of CITY names from STATION which have vowels (i.e., a, e, i, o, and u) as both their first and last characters. Your result cannot contain duplicates.

**Solution:** 
```sql
SELECT DISTINCT city
FROM station
WHERE city REGEXP '^[AEIOUaeiou].*[aeiouAEIOU]$';
```

### Weather Observation Station 9
**Problem::** Query the list of CITY names from STATION that do not start with vowels. Your result cannot contain duplicates.

**Solution:** 
```sql
SELECT DISTINCT city
FROM station
WHERE city NOT REGEXP '^[AEIOUaeiou]';
```

### Weather Observation Station 10
**Problem::** Query the list of CITY names from STATION that do not end with vowels. Your result cannot contain duplicates.

**Solution:** 
```sql
SELECT DISTINCT city
FROM station
WHERE city NOT REGEXP '[AEIOUaeiou]$';
```
