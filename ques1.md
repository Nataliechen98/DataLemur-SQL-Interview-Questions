![image](https://user-images.githubusercontent.com/94289230/195591896-105c59b8-8181-4bf5-b5dc-a53c0d049ece.png)


MISTAKES
```sql
SELECT candidate_id, COUNT(skill) as skill_count
FROM candidates
WHERE skill IN ('Python' , 'Tableau' , 'PostgreSQL')
GROUP BY candidate_id
HAVING skill_count = 3 --Can't use alias for an aggregate in a HAVING clause.
--The HAVING clause is evaluated before the SELECT - so the server doesn't yet know about that alias.
ORDER BY candidate_id;
```

SOLUTION
```sql
SELECT candidate_id
FROM candidates
WHERE skill IN ('Python' , 'Tableau' , 'PostgreSQL')
GROUP BY candidate_id
HAVING COUNT(skill) = 3  --aggregate function has to use HAVING, cannot use WHERE
ORDER BY candidate_id;
```
