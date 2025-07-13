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
    POWER(MIN(LONG_W) - MAX(LONG_W), 2)
  ), 
  4
)
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


