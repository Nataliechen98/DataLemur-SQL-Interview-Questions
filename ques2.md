![image](https://user-images.githubusercontent.com/94289230/195599107-ba86e7f3-89fd-4418-8c3e-7c7a06a3e8b6.png)

first attempt
```sql
SELECT p.page_id  
FROM pages AS p  
JOIN page_likes AS pl 
ON p.page_id = pl.page_id
WHERE p.page_id NOT IN (SELECT pl.page_id FROM page_likes)
GROUP BY p.page_id;
```
SOLUTION
```sql
SELECT p.page_id  
FROM pages AS p  
LEFT JOIN page_likes AS pl 
ON p.page_id = pl.page_id
WHERE pl.liked_date IS NULL
ORDER BY p.page_id  ;
```
