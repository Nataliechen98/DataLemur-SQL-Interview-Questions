![image](https://user-images.githubusercontent.com/94289230/195769726-5eda2905-cd51-49f3-b538-13505c5f9e64.png)
![image](https://user-images.githubusercontent.com/94289230/195769765-e3e28c78-adcb-496a-ba42-beaab4b4639d.png)

SOLUTION
```sql
SELECT city, count(status) AS total_orders
FROM trades AS t  
JOIN users AS u   
ON t.user_id = u.user_id 
WHERE status = 'Completed'
GROUP BY city
ORDER BY total_orders DESC
LIMIT 3;
```
