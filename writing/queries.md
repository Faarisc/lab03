# Database Systems (CS305) Lab 3 Assignment (Part 2)

Please add your responses to this file.

#### Name

Faaris 

#### GitHub Account Name

Faarisc

---

The below queries have been written with a new notation where the table's names are defined by an initial. The initial is then used to denote the table in the query code. Spend a moment to study the new syntax and ask questions as necessary.

1. In your own words, write a question to describe what the following query is answering.

``` SQL
SELECT
 count(sa.protID) 
FROM
 nprot n, sars sa
WHERE
 sa.protID == n.protID;
```

In your words: Find out the number of Protein ID's commonly found in nprot n, sars sa

2. In your own words, write a question to describe what the following query is answering.

``` SQL
SELECT
 count(distinct(sa.protID))
FROM 
 nprot n, sars sa, mprot m
WHERE
 sa.protID == n.protID
AND
 sa.protID == m.protID;
```

In your words: What was the total number of protID's across all databases?

3. Find the one protein which is found simultaneously in all four tables; `mprot`, `nprot`, `sprot` and `sars`

``` SQL
SELECT
 count(distinct(sa.protID))
FROM
 nprot n
JOIN 
 sars sa ON sa.protID = n.protID
JOIN
 mprot m ON sa.protID = m.protID
JOIN 
 sprot s ON sa.protID = s.protID;
```

4. Find the number of distinct `protID` entities which are found in the `sars` table AND are also found in `mprot` as well.

``` SQL
SELECT
 count(distinct(sa.protID))
FROM 
 sars sa
JOIN 
 mprot m 
ON
 sa.protID = m.protID;
```

5. Write a query to list all distinct `Organisms` which are found simultaneously in both the `sprot` and `nprot` tables.

``` SQL
SELECT
 count(distinct(sp.Organisms))
FROM
 nprot n, sprot s
WHERE
 s.Organisms == n.Organisms;
```


6. Write a query to list all distinct `Organisms` which are found simultaneously in both the `mprot` and `nprot` tables.

``` SQL
SELECT
 count(distinct(m.Organisms))
FROM 
mprot m
WHERE m.Organisms IN (SELECT Organisms FROM nprot);
```


7. Write a query to list all `distinct` `entryName` entities which are found simultaneously in the tables `nprot` , `sprot` and `mprot`.

``` SQL
SELECT(distinct(n.entryName))
FROM nprot n
WHERE s.entryname IN (SELECT entryname FROM sprot)
AND m.entryname IN (SELECT entryName FROM mprot);
```

8. Write a query to list the `protID` and `organism` entities from the `sars` table where the length of the protein is equal to 240.

``` SQL
SELECT (protID, organism)
FROM sars
WHERE LENGTH(protein) = 240;
```

9. Write a query to obtain a listing of `distinct` `ProteinNames` which are found simultaneously in the tables; `sars`, `mprot` and `nprot`.

``` SQL
SELECT (distinct(s.ProteinNames))
FROM sars s, nprot n, mprot m 
WHERE s.ProteinName == m.ProteinName
AND s.ProteinName == n.ProteinName
AND m.ProteinName == n.ProteinName;
```


10. Write a query to find out the average length of the proteins in the sars table for the organism "Mus musculus (Mouse)"

``` SQL
SELECT (avg(s.Length)) 
FROM sars s 
WHERE s.Organism == "Mus musculus (Mouse)";
```


11. Write a question of your own that uses all four tables to answer, then provide the query to respond to your question involving the four tables.


In your words: What is the total amount of ProtID's found across all tables?

``` SQL
SELECT
 count(distinct(protID))
FROM sars
WHERE protID IN (
    SELECT n.protID FROM nprot n
    JOIN mprot m ON n.protID = m.protID
    JOIN sprot s ON n.protID = s.protID
);
```
---

(Did you remember to add your name at the top of this document?)
