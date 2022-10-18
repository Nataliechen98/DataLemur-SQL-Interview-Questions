![image](https://user-images.githubusercontent.com/94289230/196364264-9aa88965-280f-44ce-a724-4943e5d0cc6e.png)

SOLUTION
```SQL
SELECT EXTRACT(MONTH FROM submit_date) AS mth, product_id AS product, ROUND(AVG(stars),2) as avg_stars
FROM reviews
GROUP BY mth, product
ORDER BY mth, product;
```
