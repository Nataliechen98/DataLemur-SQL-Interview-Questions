![image](https://user-images.githubusercontent.com/94289230/196367694-205e8595-dd09-4468-b632-dd4b8697e7ba.png)
![image](https://user-images.githubusercontent.com/94289230/196367741-561b6a4e-7fcb-4770-a321-4c63f64607a1.png)

SOLUTION
```SQL
SELECT profile_id
FROM personal_profiles AS P
JOIN company_pages AS c 
ON p.employer_id = c.company_id
WHERE p.followers > c.followers
ORDER BY profile_id; --ques say order by id
```
