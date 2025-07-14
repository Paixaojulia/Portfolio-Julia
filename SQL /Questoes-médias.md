 # Questões medianas de SQL 
## Segue uma lista selecionada de questões medianas de SQL retiradas diretamente do site HackerRank.

## 1 - Weather Observation Station 18
Consider P1 (a, b) and P2 (c, d) to be two points on a 2D plane.

 happens to equal the minimum value in Northern Latitude (LAT_N in STATION).
 happens to equal the minimum value in Western Longitude (LONG_W in STATION).
 happens to equal the maximum value in Northern Latitude (LAT_N in STATION).
 happens to equal the maximum value in Western Longitude (LONG_W in STATION).
Query the Manhattan Distance between points P1 and P2 and round it to a scale of 4 decimal places.

Input Format

The STATION table is described as follows:
 
![image](https://i.postimg.cc/PxKBwNSY/imagem-2025-06-16-190640207.png)

where LAT_N is the northern latitude and LONG_W is the western longitude.

##### Answer: 
```
SELECT ROUND(ABS(MIN(LAT_N) - MAX(LAT_N)) + ABS(MIN(LONG_W) - MAX(LONG_W)), 4)
FROM STATION;

```
## 2 - Weather Observation Station 19

Consider P1 (a, c) and P2 (b, d) to be two points on a 2D plane where (a, b) are the respective minimum and maximum values of Northern Latitude (LAT_N) and (c, d) are the respective minimum and maximum values of Western Longitude (LONG_W) in STATION.

Query the Euclidean Distance between points P1 and P2 and format your answer to display 4 decimal digits.

Input Format

The STATION table is described as follows:

![image](https://github.com/user-attachments/assets/05c1ddb0-6002-48cb-a363-44241458e9b5)

where LAT_N is the northern latitude and LONG_W is the western longitude.

##### Answer: 
```
SELECT ROUND(  SQRT(
    POWER(MIN(LAT_N) - MAX(LAT_N), 2) + 
    POWER(MIN(LONG_W) - MAX(LONG_W), 2)), 4)
FROM STATION;
```
## 3 - Binary Tree Nodes

Write a query to find the node type of Binary Tree ordered by the value of the node. Output one of the following for each node:

Root: If node is root node.
Leaf: If node is leaf node.
Inner: If node is neither root nor leaf node.
Sample Input

![image](https://github.com/user-attachments/assets/54b6c477-0458-470e-ad49-b7b3ea4fec66)

Sample Output

1 Leaf
2 Inner
3 Leaf
5 Root
6 Leaf
8 Inner
9 Leaf

Explanation

The Binary Tree below illustrates the sample:

![image](https://github.com/user-attachments/assets/cad7a05c-07dd-49b5-86ec-c1b7804c4f93)

##### Answer:

## 4 - Placements 

You are given three tables: Students, Friends and Packages. Students contains two columns: ID and Name. Friends contains two columns: ID and Friend_ID (ID of the ONLY best friend). Packages contains two columns: ID and Salary (offered salary in $ thousands per month).

![image](https://i.postimg.cc/T3Q8bk8Y/imagem-2025-07-13-202150981.png)

Write a query to output the names of those students whose best friends got offered a higher salary than them. Names must be ordered by the salary amount offered to the best friends. It is guaranteed that no two students got same salary offer.
Sample Input

![image](https://i.postimg.cc/FKn2W7sM/imagem-2025-07-13-202238545.png)

Sample Output

Samantha
Julia
Scarlet

Explanation

See the following table:

![image](https://i.postimg.cc/W15Kzhrd/imagem-2025-07-13-202325933.png)
Now,

- Samantha's best friend got offered a higher salary than her at 11.55
- Julia's best friend got offered a higher salary than her at 12.12
- Scarlet's best friend got offered a higher salary than her at 15.2
Ashley's best friend did NOT get offered a higher salary than her
The name output, when ordered by the salary offered to their friends, will be:

- Samantha
- Julia
- Scarlet
 ##### Answer: 
``` 
SELECT S.Name
FROM Students S
JOIN Friends F ON S.ID = F.ID
JOIN Packages SP ON S.ID = SP.ID       
JOIN Packages FP ON F.Friend_ID = FP.ID
WHERE FP.Salary > SP.Salary
ORDER BY FP.Salary;
```
## 5 - Weather Observation Station 20

A median is defined as a number separating the higher half of a data set from the lower half. Query the median of the Northern Latitudes (LAT_N) from STATION and round your answer to  decimal places.

Input Format

The STATION table is described as follows:

![image](https://i.postimg.cc/vTJsTDVR/imagem-2025-07-13-205514931.png)

where LAT_N is the northern latitude and LONG_W is the western longitude.

 ##### Answer: 
``` 
SELECT ROUND(LAT_N, 4)
FROM (SELECT LAT_N,
           ROW_NUMBER() OVER (ORDER BY LAT_N) AS row_num,
           COUNT(*) OVER () AS total_rows
    FROM STATION) AS ordered
WHERE row_num IN
    (FLOOR((total_rows + 1) / 2),  
    CEIL((total_rows + 1) / 2)
);
```

## 6- SQL Project Planning
You are given a table, Projects, containing three columns: Task_ID, Start_Date and End_Date. It is guaranteed that the difference between the End_Date and the Start_Date is equal to 1 day for each row in the table.

![image](https://i.postimg.cc/c4hpPDDy/imagem-2025-07-13-210007083.png)

If the End_Date of the tasks are consecutive, then they are part of the same project. Samantha is interested in finding the total number of different projects completed.

Write a query to output the start and end dates of projects listed by the number of days it took to complete the project in ascending order. If there is more than one project that have the same number of completion days, then order by the start date of the project.

![image](https://i.postimg.cc/8cHYQ5mB/imagem-2025-07-13-210112215.png)

Sample Output

2015-10-28 2015-10-29
2015-10-30 2015-10-31
2015-10-13 2015-10-15
2015-10-01 2015-10-04

Explanation

The example describes following four projects:

Project 1: Tasks 1, 2 and 3 are completed on consecutive days, so these are part of the project. Thus start date of project is 2015-10-01 and end date is 2015-10-04, so it took 3 days to complete the project.
Project 2: Tasks 4 and 5 are completed on consecutive days, so these are part of the project. Thus, the start date of project is 2015-10-13 and end date is 2015-10-15, so it took 2 days to complete the project.
Project 3: Only task 6 is part of the project. Thus, the start date of project is 2015-10-28 and end date is 2015-10-29, so it took 1 day to complete the project.
Project 4: Only task 7 is part of the project. Thus, the start date of project is 2015-10-30 and end date is 2015-10-31, so it took 1 day to complete the project.

 ##### Answer: 
```
WITH ordered_tasks AS (
  SELECT *,
     ROW_NUMBER() OVER (ORDER BY Start_Date) AS rn
  FROM Projects),
grouped_tasks AS (
  SELECT *,
     DATE_SUB(Start_Date, INTERVAL rn DAY) AS group_key
  FROM ordered_tasks)
SELECT 
  MIN(Start_Date) AS start_date,
  MAX(End_Date) AS end_date
FROM grouped_tasks
GROUP BY group_key
ORDER BY DATEDIFF(MAX(End_Date), MIN(Start_Date)) ASC, MIN(Start_Date);
```
