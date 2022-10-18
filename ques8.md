![image](https://user-images.githubusercontent.com/94289230/196330438-c5f9a283-94cb-436d-8a2e-f7b79f818135.png)

![image](https://user-images.githubusercontent.com/94289230/196330471-416604d8-3f5e-49e2-8d67-b42f63e7c71c.png)

![image](https://user-images.githubusercontent.com/94289230/196330492-3795fe0c-b61e-427b-a921-e518895f6dac.png)

MISTAKE
```sql
SELECT user_id, COUNT(tweet_id) AS total_tweets, tweet_date
-- column "tweets.tweet_date" must appear in the GROUP BY clause or be used in an aggregate function (line 1)
FROM tweets
WHERE tweet_date BETWEEN '2022-01-01' AND '2022-12-31'
GROUP BY user_id;
```

SOLUTION
```sql
WITH total_tweets
AS(
  SELECT user_id, COUNT(tweet_id) AS tweets_num
  FROM tweets
  WHERE tweet_date BETWEEN '2022-01-01' AND '2022-12-31'
  GROUP BY user_id
)

SELECT tweets_num, COUNT(user_id)
FROM total_tweets
GROUP BY tweets_num;
```
