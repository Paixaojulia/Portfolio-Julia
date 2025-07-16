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

## 7 - Top Competitors

Julia just finished conducting a coding contest, and she needs your help assembling the leaderboard! Write a query to print the respective hacker_id and name of hackers who achieved full scores for more than one challenge. Order your output in descending order by the total number of challenges in which the hacker earned a full score. If more than one hacker received full scores in same number of challenges, then sort them by ascending hacker_id.

Input Format

The following tables contain contest data:

Hackers: The hacker_id is the id of the hacker, and name is the name of the hacker.

![image](https://i.postimg.cc/mg4MJVns/imagem-2025-07-16-194902666.png)

Difficulty: The difficult_level is the level of difficulty of the challenge, and score is the maximum score that can be achieved for a challenge at that difficulty level.

![image](https://i.postimg.cc/Pq3wLH5X/imagem-2025-07-16-194943546.png)

Challenges: The challenge_id is the id of the challenge, the hacker_id is the id of the hacker who created the challenge, and difficulty_level is the level of difficulty of the challenge.

![image](https://i.postimg.cc/wMJybscM/imagem-2025-07-16-195029905.png)

Submissions: The submission_id is the id of the submission, hacker_id is the id of the hacker who made the submission, challenge_id is the id of the challenge that the submission belongs to, and score is the score of the submission.

![image](https://i.postimg.cc/Bv68fzcd/imagem-2025-07-16-195112241.png)

Sample Input

Hackers Table:

![image](https://i.postimg.cc/bJSss25g/imagem-2025-07-16-195149043.png)

Difficulty Table:

![image](https://i.postimg.cc/prNy8LbH/imagem-2025-07-16-195230903.png)

Challenges Table:

![image](https://i.postimg.cc/pL0TCZbk/imagem-2025-07-16-195423062.png)

Submissions Table:

![image](https://i.postimg.cc/brHYt09x/imagem-2025-07-16-195523677.png)

Sample Output

90411 Joe
Explanation

Hacker 86870 got a score of 30 for challenge 71055 with a difficulty level of 2, so 86870 earned a full score for this challenge.

Hacker 90411 got a score of 30 for challenge 71055 with a difficulty level of 2, so 90411 earned a full score for this challenge.

Hacker 90411 got a score of 100 for challenge 66730 with a difficulty level of 6, so 90411 earned a full score for this challenge.

Only hacker 90411 managed to earn a full score for more than one challenge, so we print the their hacker_id and name as 2 space-separated values.

 ##### Answer: 
```
SELECT s.hacker_id, h.name
FROM Submissions s
JOIN Challenges c ON s.challenge_id = c.challenge_id
JOIN Difficulty d ON c.difficulty_level = d.difficulty_level
JOIN Hackers h ON s.hacker_id = h.hacker_id
WHERE s.score = d.score
GROUP BY s.hacker_id, h.name
HAVING COUNT(DISTINCT s.challenge_id) > 1
ORDER BY COUNT(DISTINCT s.challenge_id) DESC, s.hacker_id;
```
## 8 - Symmetric Pairs

You are given a table, Functions, containing two columns: X and Y.

![image](https://i.postimg.cc/jdLkCqq5/imagem-2025-07-16-200220230.png)

Two pairs (X1, Y1) and (X2, Y2) are said to be symmetric pairs if X1 = Y2 and X2 = Y1.

Write a query to output all such symmetric pairs in ascending order by the value of X. List the rows such that X1 ≤ Y1.
Sample Input

![image](https://i.postimg.cc/YSk3Nt7Q/imagem-2025-07-16-200326433.png)

Sample Output

20 20
20 21
22 23

 ##### Answer: 
```
SELECT DISTINCT
    LEAST(f1.X, f1.Y) AS X,
    GREATEST(f1.X, f1.Y) AS Y
FROM Functions f1
JOIN Functions f2
  ON f1.X = f2.Y AND f1.Y = f2.X
WHERE f1.X != f1.Y OR (f1.X = f1.Y AND EXISTS (
    SELECT 1 FROM Functions f3
    WHERE f3.X = f1.X AND f3.Y = f1.Y HAVING COUNT(*) > 1
))
ORDER BY X;
```

## 9 - New Companies

Amber's conglomerate corporation just acquired some new companies. Each of the companies follows this hierarchy:

![image](https://i.postimg.cc/D0dswXWD/imagem-2025-07-16-200750037.png)

Given the table schemas below, write a query to print the company_code, founder name, total number of lead managers, total number of senior managers, total number of managers, and total number of employees. Order your output by ascending company_code.

Note:

The tables may contain duplicate records.
The company_code is string, so the sorting should not be numeric. For example, if the company_codes are C_1, C_2, and C_10, then the ascending company_codes will be C_1, C_10, and C_2.
Input Format

The following tables contain company data:

Company: The company_code is the code of the company and founder is the founder of the company.

![image](https://i.postimg.cc/T3mczp0z/imagem-2025-07-16-201931085.png)

Lead_Manager: The lead_manager_code is the code of the lead manager, and the company_code is the code of the working company.

![image](https://i.postimg.cc/dtCN8qpV/imagem-2025-07-16-202024474.png)

Senior_Manager: The senior_manager_code is the code of the senior manager, the lead_manager_code is the code of its lead manager, and the company_code is the code of the working company.

![image](https://i.postimg.cc/G2BxdK1m/imagem-2025-07-16-202052327.png)

Manager: The manager_code is the code of the manager, the senior_manager_code is the code of its senior manager, the lead_manager_code is the code of its lead manager, and the company_code is the code of the working company.

![image](https://i.postimg.cc/66cpBXYT/imagem-2025-07-16-202128263.png)

Employee: The employee_code is the code of the employee, the manager_code is the code of its manager, the senior_manager_code is the code of its senior manager, the lead_manager_code is the code of its lead manager, and the company_code is the code of the working company.

![image](https://i.postimg.cc/906xvSR2/imagem-2025-07-16-202203516.png)

Sample Input

Company Table:

![image](https://i.postimg.cc/ZKkzkDh0/imagem-2025-07-16-202234842.png)

Lead_Manager Table:

![image](https://i.postimg.cc/Dyfdz7hN/imagem-2025-07-16-202320397.png)

Senior_Manager Table:

![image](https://i.postimg.cc/HkXxD7K1/imagem-2025-07-16-202626241.png)

Manager Table:

![image](https://i.postimg.cc/T3VRHvLR/imagem-2025-07-16-202707008.png)

Employee Table:

![image](https://i.postimg.cc/sgsXz2RB/imagem-2025-07-16-202748544.png)

Sample Output

C1 Monika 1 2 1 2
C2 Samantha 1 1 2 2
Explanation

In company C1, the only lead manager is LM1. There are two senior managers, SM1 and SM2, under LM1. There is one manager, M1, under senior manager SM1. There are two employees, E1 and E2, under manager M1.

In company C2, the only lead manager is LM2. There is one senior manager, SM3, under LM2. There are two managers, M2 and M3, under senior manager SM3. There is one employee, E3, under manager M2, and another employee, E4, under manager, M3.


 ##### Answer: 
```
SELECT 
    c.company_code,
    c.founder,
    COUNT(DISTINCT lm.lead_manager_code),
    COUNT(DISTINCT sm.senior_manager_code),
    COUNT(DISTINCT m.manager_code),
    COUNT(DISTINCT e.employee_code)
FROM Company c
LEFT JOIN Lead_Manager lm 
    ON c.company_code = lm.company_code
LEFT JOIN Senior_Manager sm 
    ON c.company_code = sm.company_code
LEFT JOIN Manager m 
    ON c.company_code = m.company_code
LEFT JOIN Employee e 
    ON c.company_code = e.company_code
GROUP BY c.company_code, c.founder
ORDER BY c.company_code;
```

![image](
## 10 - Contest Leaderboard

You did such a great job helping Julia with her last coding contest challenge that she wants you to work on this one, too!

The total score of a hacker is the sum of their maximum scores for all of the challenges. Write a query to print the hacker_id, name, and total score of the hackers ordered by the descending score. If more than one hacker achieved the same total score, then sort the result by ascending hacker_id. Exclude all hackers with a total score of  from your result.

Input Format

The following tables contain contest data:

Hackers: The hacker_id is the id of the hacker, and name is the name of the hacker.

![image](https://i.postimg.cc/nLT9gDjc/imagem-2025-07-16-203616626.png)

Submissions: The submission_id is the id of the submission, hacker_id is the id of the hacker who made the submission, challenge_id is the id of the challenge for which the submission belongs to, and score is the score of the submission.

![image](https://i.postimg.cc/RhJ3WpPN/imagem-2025-07-16-203658631.png)

Sample Input

Hackers Table:

![image](https://i.postimg.cc/Njc4wRM1/imagem-2025-07-16-203725762.png)

Submissions Table:

![image](https://i.postimg.cc/rpyNDc5s/imagem-2025-07-16-203759586.png)

Sample Output

4071 Rose 191
74842 Lisa 174
84072 Bonnie 100
4806 Angela 89
26071 Frank 85
80305 Kimberly 67
49438 Patrick 43
Explanation

Hacker 4071 submitted solutions for challenges 19797 and 49593, so the total score = 95 + max(43,96) = 191.

Hacker 74842 submitted solutions for challenges 19797 and 63132, so the total score = max (98,5) + 76 = 174.

Hacker 84072 submitted solutions for challenges 49593 and 63132, so the total score = 100 + 0 = 100.

The total scores for hackers 4806, 26071, 80305, and 49438 can be similarly calculated.



