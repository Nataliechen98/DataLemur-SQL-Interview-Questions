![image](https://user-images.githubusercontent.com/94289230/197961841-5a09ed54-b708-463f-8068-2a3ee6a9cb53.png)

![image](https://user-images.githubusercontent.com/94289230/197961934-c680e77a-f646-41fd-849c-bcef45313f61.png)

SOLUTION
```SQL
SELECT user_id , MAX(post_date::DATE) - MIN(post_date::DATE) AS days_between
FROM posts
WHERE DATE_PART('year', post_date) = 2021
GROUP BY user_id
HAVING COUNT(user_id) > 1;
```
![image](https://user-images.githubusercontent.com/94289230/197962197-6d8d92f6-80ae-4d6c-99ae-e2624892481d.png)

MISTAKE
```SQL
SELECT user_id , MAX(post_datE) - MIN(post_date) AS days_between
FROM posts
WHERE DATE_PART('year', post_date) = 2021
GROUP BY user_id
HAVING COUNT(user_id) > 1;
```

![image](https://user-images.githubusercontent.com/94289230/197962282-ffa7d57b-8920-4dfd-baff-fa0e510cf327.png)


