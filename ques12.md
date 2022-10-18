![image](https://user-images.githubusercontent.com/94289230/196380508-38c7b2af-91b0-4851-96f7-1961ba0a5f40.png)
![image](https://user-images.githubusercontent.com/94289230/196380554-f4ac207b-c540-4ff1-9b34-c7ceca19f41f.png)

SOLUTION
```SQL
WITH sum_demand
AS(
  SELECT fd.datacenter_id , SUM(monthly_demand) AS sum
  FROM forecasted_demand AS fd
  JOIN datacenters AS dc 
  ON dc.datacenter_id = fd.datacenter_id 
  GROUP BY fd.datacenter_id
)

SELECT s.datacenter_id, SUM(monthly_capacity - sum) AS spare_capacity
FROM sum_demand AS s
JOIN datacenters AS dc 
ON s.datacenter_id = dc.datacenter_id
GROUP BY s.datacenter_id
ORDER BY s.datacenter_id ;
```
