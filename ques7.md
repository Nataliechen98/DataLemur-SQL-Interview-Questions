![image](https://user-images.githubusercontent.com/94289230/195810896-bd39f01c-f416-440c-9642-a59f20980220.png)

SOLUTION
```SQL
SELECT 
  account_id,
  SUM (CASE WHEN transaction_type = 'Deposit' THEN amount ELSE -amount END ) AS final_balance
FROM transactions
GROUP BY account_id;
```
