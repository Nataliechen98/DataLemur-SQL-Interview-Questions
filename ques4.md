![image](https://user-images.githubusercontent.com/94289230/195768065-8eb8768b-253e-4325-9586-ba972eda22cf.png)
![image](https://user-images.githubusercontent.com/94289230/195769073-883b2288-dbc6-4942-80dc-7afdc74cb7e0.png)

SOLUTION
```SQL
SELECT 
  SUM(CASE WHEN device_type = 'laptop' THEN 1 ELSE 0 END) AS laptop_views,
  SUM(CASE WHEN device_type IN ('tablet', 'phone') THEN 1 ELSE 0 END) AS mobile_views
FROM viewership;
 ```
