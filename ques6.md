![image](https://user-images.githubusercontent.com/94289230/195773819-1729f166-d88c-4ae2-96b5-c9c0647b2287.png)
![image](https://user-images.githubusercontent.com/94289230/195773850-482f0a3a-61b3-404b-9f21-a3ffe8f550ae.png)

SOLUTION #1 
```sql
WITH job_listings_rank   --CTE
AS (SELECT 
      company_id, 
      title, 
      description, 
      COUNT(job_id) AS job_count
    FROM job_listings
    GROUP BY 
      company_id, 
      title, 
      description
)

SELECT COUNT (DISTINCT company_id)
FROM job_listings_rank 
WHERE job_count > 1;
```

SOLUTION #2 (ROW_NUMBER)
```sql
WITH job_listings_rank    --CTE
AS (
  SELECT
    ROW_NUMBER() OVER (
      PARTITION BY company_id, title, description 
    ) AS ranking, 
    company_id, 
    title, 
    description 
  FROM job_listings
)

SELECT COUNT (DISTINCT company_id)
FROM job_listings_rank
WHERE ranking > 1;
```
*if using ROW_NUMBER, don't have to GROUP BY, just have to SELECT those with ranking =2
