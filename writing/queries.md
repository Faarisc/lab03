# Database Systems (CS305) Lab 3 Assignment (Part 2)

Please add your responses to this file.

#### Name

Add Your Name Here

#### GitHub Account Name

Add Your Name Here

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

In your words: TODO

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

In your words: TODO

3. Find the one protein which is found simultaneously in all four tables; `mprot`, `nprot`, `sprot` and `sars`

``` SQL
TOOD

```

4. Find the number of distinct `protID` entities which are found in the `sars` table AND are also found in `mprot` as well.

``` SQL
TODO

```

5. Write a query to list all distinct `Organisms` which are found simultaneously in both the `sprot` and `nprot` tables.

``` SQL
TODO
```


6. Write a query to list all distinct `Organisms` which are found simultaneously in both the `mprot` and `nprot` tables.

``` SQL
TODO
```


7. Write a query to list all `distinct` `entryName` entities which are found simultaneously in the tables `nprot` , `sprot` and `mprot`.

``` SQL
TODO
```

8. Write a query to list the `protID` and `organism` entities from the `sars` table where the length of the protein is equal to 240.

``` SQL
TODO
```

9. Write a query to obtain a listing of `distinct` `ProteinNames` which are found simultaneously in the tables; `sars`, `mprot` and `nprot`.

``` SQL
TODO
```


10. Write a query to find out the average length of the proteins in the sars table for the organism "Mus musculus (Mouse)"

``` SQL
TODO
```


11. Write a question of your own that uses all four tables to answer, then provide the query to respond to your question involving the four tables.


In your words: TODO

``` SQL
TODO
```
---

(Did you remember to add your name at the top of this document?)
