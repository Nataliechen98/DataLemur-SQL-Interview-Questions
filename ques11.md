![image](https://user-images.githubusercontent.com/94289230/196370337-b0b2157f-d04b-443a-ada0-1784f77d576b.png)

has to write out both DESC, if not it will assume product_num AS ASC

SOLUTION
``` SQL
SELECT user_id, count(product_id) AS product_num
FROM user_transactions
GROUP BY user_id
HAVING SUM(spend) > 1000
ORDER BY product_num DESC, SUM(spend) DESC  
LIMIT 3;
```
