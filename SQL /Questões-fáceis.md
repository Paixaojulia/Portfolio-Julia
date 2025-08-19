
   # Questões fáceis de SQL 
 ## Segue uma lista selecionada de questões fáceis de SQL retiradas diretamente do site HackerRank.

## 1 - Select All
Consulte todas as colunas (atributos) para cada linha na tabela CITY. 
 A tabela CITY é descrita da seguinte forma: 
 
![image](https://github.com/user-attachments/assets/951472ee-3f83-44de-8d3e-ed018beb3137)

##### Resposta: 
```SELECT * FROM city```

## 2 - Japanese Cities' Attributes
Consulte todos os atributos de cada cidade japonesa na tabela CITY. O COUNTRYCODE para o Japão é JPN.
A tabela CITY é descrita da seguinte forma:

![image](https://github.com/user-attachments/assets/4bd8692a-fe60-45e7-84ce-4eb187eddf96)

##### Resposta:

```
   SELECT *
   FROM CITY
   WHERE COUNTRYCODE = 'JPN'
   ```

## 3 - Japanese Cities' Names
Consulte os nomes de todas as cidades japonesas na tabela CITY. O COUNTRYCODE para o Japão é JPN.
A tabela CITY é descrita da seguinte forma:

![image](https://github.com/user-attachments/assets/69c009d8-f31f-41dc-936f-975000506f5f)

##### Resposta:
```
SELECT NAME 
FROM CITY 
WHERE COUNTRYCODE = 'JPN'
```

## 4 - Select By ID
Consultar todas as colunas de uma cidade em CITY com o ID 1661.
A tabela CITY é descrita da seguinte forma:

![image](https://github.com/user-attachments/assets/49fa4eee-f43a-4b34-a7bf-1186397ed29c)

##### Resposta:
```
SELECT *
FROM CITY
WHERE ID = 1661
```
## 5 - Revising the Select Query I
Consulte todas as colunas de todas as cidades americanas na tabela CITY com populações maiores que 100.000. O CountryCode para América é EUA.
A tabela CITY é descrita da seguinte forma:

![image](https://github.com/user-attachments/assets/7d87b1a4-42fc-4e7a-8903-80ef4db1fc50)

##### Resposta:
```
SELECT *
FROM CITY 
WHERE COUNTRYCODE = 'USA'
  AND POPULATION > 100000 
```
## 6 - Revising the Select Query II
Consulte o campo NAME para todas as cidades americanas na tabela CITY com populações maiores que 120.000. O CountryCode para América é EUA.
A tabela CITY é descrita da seguinte forma:

![image](https://github.com/user-attachments/assets/a4366c08-6069-414c-8577-7e255777b897)

##### Resposta:
```
SELECT NAME
FROM CITY 
WHERE POPULATION > 120000
AND COUNTRYCODE = 'USA'
```

## 7 - Weather Observation Station 1
Consulte uma lista de CIDADE e ESTADO da tabela ESTAÇÃO.
A tabela STATION é descrita da seguinte forma:

![image](https://github.com/user-attachments/assets/12abeae4-8a96-49e3-be1e-0931f595fd16)

Onde LAT_N é a latitude norte e LONG_W é a longitude oeste.

##### Resposta:
```
SELECT CITY, STATE 
FROM STATION 
```
## 8 - Weather Observation Station 2
Consulte os dois valores a seguir na tabela STATION:
A soma de todos os valores em LAT_N arredondada para uma escala de 2 casas decimais.
A soma de todos os valores em LONG_W arredondada para uma escala de 2 casas decimais.
Input Format
A tabela STATION é descrita da seguinte forma:

![image](https://github.com/user-attachments/assets/ef388eb2-20f3-4690-b861-85931ffe5dae)

onde LAT_N é a latitude norte e LONG_W é a longitude oeste.
Output Format
Seus resultados devem estar no formato:
lat lon
Onde lat é a soma de todos os valores em LAT_N e é a soma de todos os valores em LONG_W. Ambos os resultados devem ser arredondados para uma escala de 2 casas decimais.

##### Resposta:
```
SELECT ROUND (SUM(LAT_N), 2) , ROUND(SUM(LONG_W), 2) 
FROM STATION
```

## 9 - Weather Observation Station 3
Consulte uma lista de nomes de CIDADES de ESTAÇÃO para cidades que tenham um número de identificação par. Exiba os resultados em qualquer ordem, mas exclua duplicatas da resposta.
A tabela STATION é descrita da seguinte forma:

![image](https://github.com/user-attachments/assets/4510ccb1-6097-4284-8a75-dd0c593e1e8e)

Onde LAT_N é a latitude norte e LONG_W é a longitude oeste.

##### Resposta:
```
SELECT DISTINCT CITY
FROM STATION 
WHERE ID % 2 = 0;
```
## 10 - Weather Observation Station 4 
Encontre a diferença entre o número total de entradas CITY na tabela e o número de entradas CITY distintas na tabela.
A tabela STATION é descrita da seguinte forma:

![image](https://github.com/user-attachments/assets/6ed735f1-7509-4b55-95c1-2dde1ffad7d4)

Onde LAT_N é a latitude norte e LONG_W é a longitude oeste.

Por exemplo, se houver três registros na tabela com os valores CITY 'New York', 'New York', 'Bengalaru', haverá 2 nomes de cidades diferentes: 'New York' e 'Bengalaru'. A consulta retorna , porque número total de registros - número de nomes de cidades exclusivos = 3 - 2 = 1.

##### Resposta:
```
SELECT
COUNT (CITY) - COUNT (DISTINCT CITY)
FROM STATION;
```
## 11 - Weather Observation Station 6
Consulte a lista de nomes de CIDADES que começam com vogais (por exemplo, a, e, i, o ou u) em STATION. Seu resultado não pode conter duplicatas.
 Input Format
A tabela STATION é descrita da seguinte forma:

![image](https://github.com/user-attachments/assets/11592738-098a-4ea8-a1d6-5b5613e37108)

Onde LAT_N é a latitude norte e LONG_W é a longitude oeste.

##### Resposta:
```
SELECT CITY
FROM STATION 
WHERE LEFT (CITY, 1) IN ('A', 'E', 'I', 'O', 'U')
```
## 12 - Weather Observation Station 7
Consulte a lista de nomes de CIDADES terminados em vogais (a, e, i, o, u) da ESTAÇÃO. Seu resultado não pode conter duplicatas.
Input Format
A tabela STATION é descrita da seguinte forma:

![image](https://github.com/user-attachments/assets/171a1fef-36ca-4530-a86e-78b96415beaf)

Onde LAT_N é a latitude norte e LONG_W é a longitude oeste.

##### Resposta:
```
SELECT DISTINCT CITY
FROM STATION
WHERE RIGHT (CITY, 1) IN ('A', 'E', 'I', 'O', 'U');
```
## 13 - Weather Observation Station 8
Consulte a lista de nomes de CIDADES de ESTAÇÃO que possuem vogais (por exemplo, a, e, i, o e u) como primeiro e último caracteres. Seu resultado não pode conter duplicatas.

Input Format

A tabela STATION é descrita da seguinte forma:

![image](https://github.com/user-attachments/assets/222c3e79-bf0d-4c31-a114-cd8a271d2ec2)

Onde LAT_N é a latitude norte e LONG_W é a longitude oeste.

##### Resposta:
```
SELECT DISTINCT CITY
FROM STATION
WHERE LEFT(CITY, 1) IN ('A', 'E', 'I', 'O', 'U')
AND RIGHT(CITY, 1) IN ('A', 'E', 'I', 'O', 'U');
```
## 14 - Weather Observation Station 9
Consulte a lista de nomes de CIDADES de ESTAÇÃO que não começam com vogais. Seu resultado não pode conter duplicatas.

Input Format

A tabela STATION é descrita da seguinte forma:

![image](https://github.com/user-attachments/assets/1bcf570d-99de-4cf4-99d2-3c2aa283ad5a)

Onde LAT_N é a latitude norte e LONG_W é a longitude oeste.

##### Resposta:
```
SELECT DISTINCT CITY
FROM STATION
WHERE NOT LEFT(CITY, 1) IN ('A', 'E', 'I', 'O', 'U');
```
## 15 - Weather Observation Station 10
Consulte a lista de nomes de CIDADES da ESTAÇÃO que não terminam com vogais. Seu resultado não pode conter duplicatas.

Input Format

A tabela STATION é descrita da seguinte forma:

![image](https://github.com/user-attachments/assets/fa978753-1df7-4640-9beb-2cf34b0fb41f)

Onde LAT_N é a latitude norte e LONG_W é a longitude oeste.

##### Resposta:
```
SELECT DISTINCT CITY
FROM STATION
WHERE NOT RIGHT(CITY, 1) IN ('A', 'E', 'I', 'O', 'U');
```

## 16 - Weather Observation Station 11
Consulte a lista de nomes de CIDADES da ESTAÇÃO que não começam com vogais ou não terminam com vogais. Seu resultado não pode conter duplicatas.

Input Format

A tabela STATION é descrita da seguinte forma:

![image](https://github.com/user-attachments/assets/299b4107-6557-4cc1-8218-a341f87199a5)

Onde LAT_N é a latitude norte e LONG_W é a longitude oeste.

##### Resposta:
```
SELECT DISTINCT CITY
FROM STATION
WHERE NOT LEFT(CITY, 1) IN ('A', 'E', 'I', 'O', 'U')
OR NOT RIGHT(CITY, 1) IN ('A', 'E', 'I', 'O', 'U');
```

## 17 - Weather Observation Station 12
Consulte a lista de nomes de CIDADES da ESTAÇÃO que não começam com vogais e não terminam com vogais. Seu resultado não pode conter duplicatas.

Input Format

A tabela STATION é descrita da seguinte forma:

![image](https://github.com/user-attachments/assets/7c6ee490-da0c-41b8-8f84-0243b85980cf)

Onde LAT_N é a latitude norte e LONG_W é a longitude oeste.

##### Resposta:
```
SELECT DISTINCT CITY
FROM STATION
WHERE LEFT(CITY, 1) NOT IN ('A', 'E', 'I', 'O', 'U')
AND RIGHT(CITY, 1) NOT IN ('A', 'E', 'I', 'O', 'U');
```
## 18 - Weather Observation Station 13 
Consultar a soma das latitudes do norte (LAT_N) da ESTAÇÃO com valores maiores que 38.7880 e menos de 137.2145. Trunque sua resposta para 4 casas decimais.

Input Format

A tabela STATION é descrita da seguinte forma:

![image](https://github.com/user-attachments/assets/e8e9c6bf-1699-4de9-8151-73a4f99154cb)

onde LAT_N é a latitude norte e LONG_W é a longitude oeste.

##### Resposta:
```
SELECT ROUND (SUM(LAT_N), 4) 
FROM STATION 
WHERE LAT_N > 38.7880 AND LAT_N < 137.2345
```
## 19 - Weather Observation Station 14
Consultar o maior valor das latitudes do norte (LAT_N) da ESTAÇÃO que seja menor que 137.2345. Trunque sua resposta para 4 casas decimais.
Input Format
A tabela STATION é descrita da seguinte forma:

![image](https://github.com/user-attachments/assets/4552dfa3-bd40-4f38-9427-4514d01a50a6)

onde LAT_N é a latitude norte e LONG_W é a longitude oeste.

##### Resposta:
```
SELECT ROUND (MAX(LAT_N), 4) 
FROM STATION
WHERE LAT_N < 137.2345
```
## 20 - Weather Observation Station 15
Consulte a Longitude Ocidental (LONG_W) para encontrar a maior Latitude Norte (LAT_N) em STATION que seja menor que 137.2345. Arredonde sua resposta para 4 casas decimais.
Input Format
A tabela STATION é descrita da seguinte forma:

![image](https://github.com/user-attachments/assets/79588633-8b87-49ff-97ce-76cf3bb4aaaa)

onde LAT_N é a latitude norte e LONG_W é a longitude oeste.

##### Resposta:
```
SELECT ROUND (LONG_W, 4) 
FROM STATION 
WHERE LAT_N < 137.2345 
ORDER BY LAT_N 
DESC LIMIT 1;
```
## 21 - Weather Observation Station 16
Consultar a menor latitude norte (LAT_N) da ESTAÇÃO que seja maior que 38.7780. Arredonde sua resposta para 4 casas decimais.
Input Format
A tabela STATION é descrita da seguinte forma:

![image](https://github.com/user-attachments/assets/d9fd75ef-6e01-4b50-817e-47f0773ea7a2)

onde LAT_N é a latitude norte e LONG_W é a longitude oeste.

##### Resposta:
```
SELECT ROUND (LAT_N, 4)
FROM STATION 
WHERE LAT_N  >  38.7780 
ORDER BY LAT_N 
LIMIT 1;
```
## 22 - Weather Observation Station 17
Consulte a Longitude Ocidental (LONG_W) onde a menor Latitude Norte (LAT_N) em STATION é maior que 38.7780. Arredonde sua resposta para 4 casas decimais.
Input Format
A tabela STATION é descrita da seguinte forma:

![image](https://github.com/user-attachments/assets/09668a62-9967-4f7c-bf12-f1b336248e46)

onde LAT_N é a latitude norte e LONG_W é a longitude oeste.
##### Resposta:
```
SELECT ROUND (LONG_W,  4)
FROM STATION 
WHERE LAT_N > 38.7780 
ORDER BY LAT_N ASC 
LIMIT 1;
```

## 23 - Higher Than 75 Marks
Consulte o nome de qualquer aluno em STUDENTS que tenha pontuação superior 75 a pontos. Ordene sua saída pelos três últimos caracteres de cada nome. Se dois ou mais alunos tiverem nomes terminados nos mesmos três últimos caracteres (por exemplo: Bobby, Robby, etc.), ordene-os secundariamente por ID crescente.
Input Format
A tabela STUDENTS é descrita da seguinte forma:

![image](https://github.com/user-attachments/assets/aeab6145-bf5c-491b-99db-73461089b3bd)

A coluna Name contém apenas letras maiúsculas (A-Z) e minúsculas (a-z).

Sample Input

![image](https://github.com/user-attachments/assets/a055ee86-b291-4d68-bb36-662b9437866b)

Sample Output
Ashley
Julia
Belvet

Explicação
Somente Ashley, Julia e Velvet têm pontos > 75. Se você olhar para os três últimos caracteres de cada um dos seus nomes, não há duplicatas e 'ley' < 'lia' < 'vet'.

##### Resposta:
```
SELECT Name
FROM STUDENTS
WHERE Marks > 75
ORDER BY RIGHT(Name, 3), ID ASC;
```
## 24 - Employee Names
Escreva uma consulta que imprima uma lista de nomes de funcionários (por exemplo: o atributo name) da tabela Employee em ordem alfabética.
Input Format
A tabela Employee, que contém os dados dos funcionários de uma empresa, é descrita da seguinte forma:

![image](https://github.com/user-attachments/assets/26d7b718-06e5-4484-84e7-2279ab42809b)

Onde employee_id é o número de identificação do funcionário, name é o nome dele, months é o número total de meses que ele trabalha na empresa e salary é o salário mensal.

Sample Input

![image](https://github.com/user-attachments/assets/5521950d-6523-4418-a6b6-5d41ff990496)

Sample Output
Angela
Bonnie
Frank
Joe
Kimberly
Lisa
Michael
Patrick
Rose
Todd

##### Resposta:
```
SELECT name
FROM Employee
ORDER BY name ASC
```
## 25 - Employee Salaries
Escreva uma consulta que imprima uma lista de nomes de funcionários (por exemplo: o atributo name) para funcionários com salário superior a US$ 2.000 por mês e que estejam empregados há menos de 10 meses. Classifique o resultado em ordem crescente de employee_id.
Input Format
A tabela Employee contendo dados de funcionários de uma empresa é descrita da seguinte forma:

![image](https://github.com/user-attachments/assets/8ab9e71a-f303-4d6a-ba15-37d4c2b9812e)

Onde employee_id é o número de identificação do funcionário, name é o nome dele, months é o número total de meses que ele trabalha na empresa e salary é o salário mensal.

Sample Input

![image](https://github.com/user-attachments/assets/d436daed-efa0-47d4-96de-f6ca483ec7f7)

Sample Output
Angela
Michael
Todd
Joe

Explicação
Angela é funcionária há 1 mês e ganha US$ 3.443 por mês.
Michael é funcionário há 6 meses e ganha US$ 2.017 por mês.
Todd é funcionário há 5 meses e ganha US$ 3.396 por mês.
Joe é funcionário há 9 meses e ganha US$ 3.573 por mês.
Ordenamos nossa saída em ordem crescente de employee_id.

##### Resposta:
```
SELECT name
FROM Employee
WHERE salary > 2000
AND months < 10
ORDER BY employee_id ASC
```
## 26 - Revising Aggregations - The Count Function
Input Format
A tabela CITY é descrita da seguinte forma:

![image](https://github.com/user-attachments/assets/704d00be-9d1a-4aaa-b440-6ba7d16bff0f)

##### Resposta:
```
SELECT COUNT(*)
FROM CITY
WHERE Population > 100000;
```
## 27 - Revising Aggregations - The Sum Function
Consulte a população total de todas as cidades em CITY cujo distrito é Califórnia.
Input Format
A tabela CITY é descrita da seguinte forma:

![image](https://github.com/user-attachments/assets/8fc25c9b-f672-443e-a49e-10f66e7097f1)

##### Resposta:
```
SELECT SUM(POPULATION) AS populacao
FROM CITY
WHERE DISTRICT = 'California';
```
## 28 - Revising Aggregations - Averages
Consulte a população média de todas as cidades em CITY cujo distrito é Califórnia.
Input Format
A tabela CITY é descrita da seguinte forma:

![image](https://github.com/user-attachments/assets/682414c3-8998-45a2-a202-6bc900e107e7)

##### Resposta:
```
SELECT AVG (POPULATION) FROM CITY
WHERE DISTRICT = 'California'
```
## 29 - Average Population
Consulte a população média de todas as cidades em CITY, arredondada para o número inteiro mais próximo.
Input Format
A tabela CITY é descrita da seguinte forma:

![image](https://github.com/user-attachments/assets/a82019a1-b767-463f-b691-e8e9d2c6ca91)

##### Resposta:
```
SELECT FLOOR(AVG(Population)) AS AveragePopulation
FROM CITY;
```
## 30 - Japan Population
Consulte a soma das populações de todas as cidades japonesas em CITY. O COUNTRYCODE para o Japão é JPN.
Input Format
A tabela CITY é descrita da seguinte forma:

![image](https://github.com/user-attachments/assets/685d4dc9-38ae-495c-878a-74708f722f1a)

##### Resposta:
```
SELECT SUM(Population) 
FROM CITY
WHERE COUNTRYCODE = 'JPN'
```
## 31 - Population Density Difference
Consulte a diferença entre as populações máxima e mínima em CITY.
Input Format
A tabela CITY é descrita da seguinte forma:

![image](https://github.com/user-attachments/assets/120f921e-91ae-4933-b5c2-9c128d3f13c4)

##### Resposta:
```
SELECT MAX(population) - MIN(population) AS PopulationDifference
FROM CITY;
```
## 32 - Population Census
Considerando as tabelas CITY e COUNTRY, consulte a soma das populações de todas as cidades cujo CONTINENTE é "Asia".
Observação: CITY.CountryCode e COUNTRY.Code são colunas-chave correspondentes.
Input Format
As tabelas CITY e COUNTRY são descritas da seguinte forma:

![image](https://github.com/user-attachments/assets/8a2a4ea4-1e8e-4b49-a1fd-8f511cbe9051)

![image](https://github.com/user-attachments/assets/82279835-5115-4a3b-898b-d1d4c7fe459d)

##### Resposta:
```
SELECT SUM(CITY.Population) AS TotalPopulation
FROM CITY
JOIN COUNTRY ON CITY.CountryCode = COUNTRY.Code
WHERE COUNTRY.Continent = 'Asia';
```
## 33 - African Cities
Considerando as tabelas CITY e COUNTRY, consulte os nomes de todas as cidades cujo CONTINENT é "África".
Observação: CITY.CountryCode e COUNTRY.Code são colunas-chave correspondentes.
Input Format
As tabelas CITY e COUNTRY são descritas da seguinte forma:

![image](https://github.com/user-attachments/assets/0042ff99-c613-49e2-b219-98d00f9f8188)

![image](https://github.com/user-attachments/assets/5cc80786-5296-41f1-bc68-6beda523adba)

##### Resposta:
```
SELECT CITY.Name
FROM CITY
JOIN COUNTRY ON CITY.CountryCode = COUNTRY.Code
WHERE COUNTRY.Continent = 'Africa';
```
## 34 - Average Population of Each Continent
Considerando as tabelas CITY e COUNTRY, consulte os nomes de todos os continentes (COUNTRY.Continent) e suas respectivas populações médias urbanas (CITY.Population), arredondadas para o número inteiro mais próximo.
Observação: CITY.CountryCode e COUNTRY.Code são colunas-chave correspondentes.
Input Format
As tabelas CITY e COUNTRY são descritas da seguinte forma:

![image](https://github.com/user-attachments/assets/991c0887-0538-4421-94d9-cdb02f6bbd1d)

![image](https://github.com/user-attachments/assets/459300f4-c4da-4462-9080-f54a49f0e17d)

##### Resposta:
```
SELECT COUNTRY.Continent, FLOOR(AVG(CITY.Population)) AS AverageCityPopulation
FROM CITY
JOIN COUNTRY ON CITY.CountryCode = COUNTRY.Code
GROUP BY COUNTRY.Continent;
```
## 35 - Top Earners
Definimos os ganhos totais de um funcionário como sendo o seu salário mensal x meses trabalhados, e os ganhos totais máximos como sendo os ganhos totais máximos de qualquer funcionário na tabela "Employee". Escreva uma consulta para encontrar os ganhos totais máximos de todos os funcionários, bem como o número total de funcionários que têm ganhos totais máximos. Em seguida, imprima esses valores como 2 inteiros separados por espaços.
Top Earners
A tabela Employee contendo dados de funcionários de uma empresa é descrita da seguinte forma:

![image](https://github.com/user-attachments/assets/661c4953-b99d-4047-9cbe-ac1ad05d0f6d)

onde employee_id é o número de identificação do funcionário, name é o nome dele, months é o número total de meses que ele trabalha na empresa e salary é o salário mensal.
Sample Input

![image](https://github.com/user-attachments/assets/f57ef536-41f1-4d77-8ca8-227a259ca8a4)

Sample Output
69952 1

Explicação
A tabela e os dados de ganhos são representados no diagrama a seguir:

![image](https://github.com/user-attachments/assets/324632c1-06fe-4a2c-be9d-7d4a3085c8ec)

O valor máximo de ganhos é 69952. A única funcionária com ganhos = 69952 é Kimberly, então imprimimos o valor máximo de ganhos (69952) e uma contagem do número de funcionários que ganharam $ 69952 (que é 1) como dois valores separados por espaços.

##### Resposta:
```
SELECT months * salary AS earnings, COUNT(*) 
FROM Employee 
GROUP BY months * salary 
ORDER BY earnings DESC 
LIMIT 1;
```
## 36 -  Type of Triangle
Escreva uma consulta identificando o tipo de cada registro na tabela TRIÂNGULOS usando os comprimentos dos três lados. Produza uma das seguintes instruções para cada registro na tabela:

Equilátero: É um triângulo com 3 lados de comprimentos iguais.
Isósceles: É um triângulo com 2 lados de comprimentos iguais.
Escaleno: É um triângulo com 3 lados de comprimentos diferentes.
Não é um triângulo: Os valores fornecidos de A, B e C não formam um triângulo.
Input Format
A tabela TRIÂNGULOS é descrita da seguinte forma:

![image](https://github.com/user-attachments/assets/c29495a5-1238-4b97-813b-7ee6ff5f1cbc)

Cada linha na tabela denota os comprimentos de cada um dos três lados de um triângulo.
Sample Input

![image](https://github.com/user-attachments/assets/d0c7b9b1-f081-45e8-b24e-ea51aae2150c)

Sample Output
Isósceles
Equilátero
Escaleno
Não é um Triângulo

Explicação
Os valores na tupla (20,20,23) formam um triângulo isósceles, pois A ≡ B.
Os valores na tupla (20,20,20) formam um triângulo equilátero, pois A ≡ B ≡ C. Os valores na tupla (20,21,22)
formam um triângulo escaleno, pois A ≠ B ≠ C.
Os valores na tupla (13,14,30) não podem formar um triângulo porque o valor combinado dos lados A e B não é maior que o do lado C.

##### Resposta:
```
SELECT 
  CASE 
    WHEN A + B <= C OR B + C <= A OR A + C <= B THEN 'Not A Triangle'
    WHEN A = B AND B = C THEN 'Equilateral'
    WHEN A = B OR B = C OR A = C THEN 'Isosceles'
    ELSE 'Scalene'
  END AS TriangleType
FROM TRIANGLES;
```

## 37 - The Blunder
Samantha foi encarregada de calcular a média dos salários mensais de todos os funcionários da tabela EMPLOYEES, mas só percebeu que a tecla do seu teclado estava quebrada depois de concluir o cálculo. Ela precisa da sua ajuda para encontrar a diferença entre o erro de cálculo dela (usando salários sem zeros) e o salário médio real.

Escreva uma consulta calculando o valor do erro (por exemplo: real - média dos salários mensais calculados incorretamente) e arredonde para o próximo número inteiro.

A tabela EMPLOYEES é descrita da seguinte forma:

![image](https://github.com/user-attachments/assets/9f483775-881f-4bdf-9dbd-40b2371ac744)

Observação: Salário mensal.

Restrições
1000 < Salário < 10⁵.

Sample Input

![image](https://github.com/user-attachments/assets/a69b4291-eb74-4b2b-9976-bb53a94ff784)

Sample Output
2061

Explicação

A tabela abaixo mostra os salários sem zeros conforme foram inseridos por Samantha:

![image](https://github.com/user-attachments/assets/6cef0c97-bb53-4c59-9498-3ac3e491db43)

Samantha calcula um salário médio de 98,00. O salário médio real é 2159,00.
O erro resultante entre os dois cálculos é 2159,00 - 98,00 = 2061,00. Como é igual ao inteiro 2061, não é arredondado para cima.

##### Resposta:
```
SELECT CEIL (AVG(SALARY) - AVG (REPLACE(SALARY, 0, ''))) 
FROM EMPLOYEES
```

  # Continuação de questões 
 ## Segue uma lista selecionada de questões fáceis de SQL retiradas diretamente do site DataLemur.

## 1 - Average Review Ratings (Amazon SQL Interview Question)
Given the reviews table, write a query to retrieve the average star rating for each product, grouped by month. The output should display the month as a numerical value, product ID, and average star rating rounded to two decimal places. Sort the output first by month and then by product ID.

reviews Table:
Column Name  	Type
review_id	   integer
user_id	      integer
submit_date	   datetime
product_id	   integer
stars	integer  (1-5)

reviews Example Input:
review_id	user_id	submit_date	product_id	stars
6171	123	06/08/2022 00:00:00	50001	4
7802	265	06/10/2022 00:00:00	69852	4
5293	362	06/18/2022 00:00:00	50001	3
6352	192	07/26/2022 00:00:00	69852	3
4517	981	07/05/2022 00:00:00	69852	2

Example Output:
mth	product	avg_stars
6	50001	3.50
6	69852	4.00
7	69852	2.50
Explanation
Product 50001 received two ratings of 4 and 3 in the month of June (6th month), resulting in an average star rating of 3.5.

##### Answer:
```
SELECT
    EXTRACT(MONTH FROM submit_date) AS mth,
    product_id AS product,
    ROUND(AVG(stars), 2) AS avg_stars
FROM reviews
GROUP BY mth, product
ORDER BY mth, product;
```

## 2 - SQL WHERE Practice Exercise (SQL Interview Question)

Given the reviews table, write a query to retrieve the average star rating for each product, grouped by month. The output should display the month as a numerical value, product ID, and average star rating rounded to two decimal places. Sort the output first by month and then by product ID.

reviews      Table:
Column Name	 Type
review_id	 integer
user_id	    integer
submit_date	 datetime
product_id	 integer
stars	integer (1-5)

reviews Example Input:
review_id	user_id	submit_date	product_id	stars
6171	123	06/08/2022 00:00:00	50001	4
7802	265	06/10/2022 00:00:00	69852	4
5293	362	06/18/2022 00:00:00	50001	3
6352	192	07/26/2022 00:00:00	69852	3
4517	981	07/05/2022 00:00:00	69852	2

Example Output:
mth	product	avg_stars
6	50001	3.50
6	69852	4.00
7	69852	2.50
Explanation
Product 50001 received two ratings of 4 and 3 in the month of June (6th month), resulting in an average star rating of 3.5.

##### Answer:
```
SELECT
  EXTRACT(MONTH FROM submit_date) AS mth,
  product_id AS product,
  ROUND(AVG(stars), 2) AS avg_stars
FROM reviews
GROUP BY mth, product
ORDER BY mth, product;
```

## 3 - SQL WHERE Practice Exercise (SQL Interview Question)

Given the reviews table, write a query to retrieve all 3-star reviews using the SQL WHERE clause. Only display the user_id and stars columns 

reviews Table:
Column Name	  Type
review_id	  integer
user_id	     integer
submit_date   datetime
product_id	  integer
stars	integer  (1-5)

reviews Example Input:
review_id	user_id	submit_date	product_id	stars
6171	123	06/08/2022 00:00:00	50001	4
7802	265	06/10/2022 00:00:00	69852	4
5293	362	06/18/2022 00:00:00	50001	3
6352	192	07/26/2022 00:00:00	69852	3
4517	981	07/05/2022 00:00:00	69852	2

Example Output:
user_id	stars
362	3
192	3
Explanation
user_id 362 gave a 3-star review, and so did user_id 192.

##### Answer:
```
SELECT
    user_id,
    stars
FROM
    reviews
WHERE
    stars = 3;
```


## 4 - SQL WHERE AND OR Practice Exercise (SQL Interview Question)
Let's practice using AND along with WHERE to filter Amazon reviews based on these two conditions:

the start count is greater than 2, and less than or equal to 4
the review must come from either user 123, 265, or 362
Pro Tip: Try coding up, and executing, each filtering condition, one at a time. It's too easy to try to code this all up in one go, and mess something up!

reviews      Table:
Column Name	 Type
review_id	 integer
user_id	    integer
submit_date	 datetime
product_id	 integer
stars	integer  (1-5)

reviews Sample Input:
review_id	user_id	submit_date	product_id	stars
6171	123	06/08/2022 00:00:00	50001	4
7802	265	06/10/2022 00:00:00	69852	4
5293	362	06/18/2022 00:00:00	50001	3
6352	192	07/26/2022 00:00:00	69852	3
4517	981	07/05/2022 00:00:00	69852	2

Sample Output:
review_id	user_id	submit_date	product_id	stars
6171	123	06/08/2022  00:00:00	 50001	    4

##### Answer:
```
SELECT * FROM reviews
WHERE stars > 2
AND stars <= 4
AND (user_id = 123 OR user_id = 265 OR user_id = 362);
```

## 5 - SQL BETWEEN Practice Exercise (SQL Interview Question)

Imagine you are a Data Analyst working at CVS Pharmacy, and you had access to pharmacy sales data. Use the BETWEEN SQL command to find data on medicines:

which sold between 100,000 units and 105,000 units
AND were manufactured by either Biogen, AbbVie, or Eli Lilly
Output the manufacturer name, drug name, and the # of units sold.

Hint: this problem requires not just BETWEEN, but also OR, AND, and WHERE clauses!

If you are struggling, be sure to review the old tutorials!

pharmacy_sales   Table:
Column Name	     Type
product_id	     integer
units_sold       integer
total_sales	     decimal
cogs	           decimal
manufacturer	  varchar
drug	           varchar

pharmacy_sales Sample Input:
product_id	units_sold	total_sales	cogs	      manufacturer	drug
9	         37410	      293452.54	208876.01	Eli Lilly	   Zyprexa
34       	94698	      600997.19	521182.16	AstraZeneca	   Surmontil
61	         77023	      500101.61	419174.97	Biogen	      Varicose Relief
136	      144814	   1084258	   1006447.73	Biogen	      Burkhart
...	      ...	      ...	      ...	      ...	         ....

pharmacy_sales Example Output:
manufacturer	 drug	                                   units_sold
AbbVie	       Lidocaine Hydrochloride and Epinephri	  101102
AbbVie	       Hydralazine Hydrochloride	              104368
Biogen	       QUETIAPINE FUMARATE 	                 103246
Eli Lilly	    Androgel	                             102027

##### Answer:
```
SELECT manufacturer, drug, units_sold
FROM pharmacy_sales
WHERE (manufacturer = 'Biogen' OR manufacturer = 'AbbVie' OR manufacturer = 'Eli Lilly')
AND units_sold BETWEEN 100000 AND 105000;
```
## 6 - SQL IN Practice Exercise (SQL Interview Question)

Imagine you are a Data Analyst working at CVS Pharmacy, and you had access to pharmacy sales data. Use the IN SQL command to find data on medicines:

which were manufactured by either Roche, Bayer, or AstraZeneca
and did not sell between 55,000 and 550,000 units
Output the manufacturer name, drug name, and the # of units sold. for all the medicines which match that criteria.

Hint: don't forget about the BETWEEN operator either!

pharmacy_sales     Table:
Column Name        Type
product_id	       integer
units_sold	       integer
total_sales		    decimal
cogs		          decimal
manufacturer		 varchar
drug		          varchar

pharmacy_sales Sample Input:

product_id	 units_sold	  total_sales	  cogs	      manufacturer	drug
9	          37410	      293452.54	  208876.01	   Eli Lilly	   Zyprexa
34	          94698	      600997.19	  521182.16	   AstraZeneca	   Surmontil
61	          77023	      500101.61	  419174.97	   Biogen	      Varicose Relief
136	       144814	      1084258	     1006447.73	Biogen	      Burkhart
...	       ...	          ...	        ...	         ...	         ....

Example Output:
manufacturer	 drug	            units_sold
Roche	          Topcare Tussin	51707
AstraZeneca	    Armour Thyroid	47310

##### Answer:
```
SELECT manufacturer, drug, units_sold FROM pharmacy_sales
WHERE manufacturer IN ('Roche', 'Bayer', 'AstraZeneca')
AND units_sold NOT BETWEEN 55000 AND 550000
```


