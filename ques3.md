![image](https://user-images.githubusercontent.com/94289230/195605654-1ddbdf60-4194-4ba5-8b6f-097c817290bf.png)

SOLUTION
```sql
SELECT DISTINCT(part)
FROM parts_assembly 
WHERE finish_date IS NULL;
```
