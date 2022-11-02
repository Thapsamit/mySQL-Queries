## Hackerrank Queries



## Day1


# 1 - Binary Tree Nodes Problem


https://www.hackerrank.com/challenges/binary-search-tree-1/problem


Code:-
    
   ``` 
   select N,IF(N in (select P from BST) and P is NULL,"Root",IF(N in (select P from BST)  
   and P is not NULL,"Inner","Leaf")) from BST order by N

   ```


# 2 - PADS Problem


https://www.hackerrank.com/challenges/the-pads/problem?isFullScreen=true


Code:-
    
   ``` 
   
   select CONCAT(Name,'(',SUBSTRING(Occupation,1,1),')') from Occupations order by Name;

   select "There are a total of ",count(Occupation) as OccCount,
   IF(Occupation="Actor","actors.",IF(Occupation="Singer","singers.",IF(Occupation="Doctor","doctors.","professors."))) from Occupations group by Occupation order by OccCount;

   ```



# 3 - Weather Station 8


https://www.hackerrank.com/challenges/weather-observation-station-8/problem?isFullScreen=true


Code:-
    
   ``` 
   
   select CITY from STATION where ((SUBSTRING(CITY,1,1) in ('a','e','i','o','u')) and ((SUBSTRING(CITY,-1,1) in ('a','e','i','o','u'))));

   ```


# 4- Weather Observation Station 18


https://www.hackerrank.com/challenges/weather-observation-station-18/problem?isFullScreen=true


Code:-
    
   ``` 
   
   select round(abs(min(LAT_N)-max(LAT_N))+abs(min(LONG_W)-max(LONG_W)),4) from STATION;


   ```



#  5 - The Report


https://www.hackerrank.com/challenges/the-report/problem?isFullScreen=true


Code:-
    
   ``` 
   
   select IF(G.GRADE<8,NULL,S.NAME),G.GRADE,S.MARKS from STUDENTS as S,GRADES as G where S.MARKS>=G.MIN_MARK and S.MARKS<=G.MAX_MARK order by G.GRADE desc,S.NAME,S.MARKS;


   ```
   
   
   
#  6 - Weather Station 20


https://www.hackerrank.com/challenges/weather-observation-station-20/problem?isFullScreen=true


Code:-
    
   ``` 
   select ROUND(S.LAT_N,4) from STATION as S where(select COUNT(LAT_N) from STATION where LAT_N<S.LAT_N) = (select COUNT(LAT_N) from STATION where LAT_N > S.LAT_N)


   ```
   
   
   
# 7 - Placements


https://www.hackerrank.com/challenges/placements/problem?isFullScreen=true


Code:-
    
   ``` 
   select NAME from STUDENTS S, PACKAGES P1,FRIENDS F,PACKAGES P2 WHERE S.ID=P1.ID AND S.ID=F.ID AND P2.ID=F.FRIEND_ID AND P2.SALARY>P1.SALARY ORDER BY P2.SALARY;


   ```
   
   
   
# 8 - weather-observation-station-11


https://www.hackerrank.com/challenges/weather-observation-station-11/problem?isFullScreen=true


Code:-
    
   ``` 
   
   select distinct(CITY) from STATION where SUBSTRING(CITY,1,1) not in ('a','e','i','o','u') or SUBSTRING(CITY,-1,1) not in ('a','e','i','o','u');


   ```
   
   
   
   
 # 9 - Contest Leaderboard


https://www.hackerrank.com/challenges/contest-leaderboard/problem?isFullScreen=true


Code:-
    
   ``` 
   
  select hacker_id,name,sum(total_score) as total_score 
From(Select s.hacker_id,name,challenge_id,max(score) as total_score
    from hackers h,submissions s where h.hacker_id=s.hacker_id and
    score>0 group by s.hacker_id,challenge_id,name
    ) as subq
group by hacker_id,name
order by total_score desc,hacker_id;


   ```
   
   
   
   
# 10 - Top Competitors


https://www.hackerrank.com/challenges/full-score/problem?isFullScreen=true


Code:-
    
   ``` 
   
  select h.hacker_id,h.name from submissions s join challenges c on s.challenge_id=c.challenge_id join difficulty d on c.difficulty_level=d.difficulty_level join hackers h on h.hacker_id=s.hacker_id where s.score=d.score and c.difficulty_level=d.difficulty_level group by h.hacker_id,h.name having count(s.hacker_id)>1 order by count(s.hacker_id) desc,h.hacker_id;


   ```
   
   
   
   
   
   
# 11 - Top Earners


https://www.hackerrank.com/challenges/earnings-of-employees/problem?isFullScreen=true


Code:-
    
   ``` 
   select max(months*salary),count(*) from Employee where months*salary = (select max(months*salary) from Employee)


   ```
   
   
   
# 12 - Weather Observation 17


https://www.hackerrank.com/challenges/weather-observation-station-17/problem?isFullScreen=true


Code:-
    
   ``` 
   
   select Round(long_w,4) from station where lat_n>38.7780 order by lat_n limit 1


   ```
   
   
   
 # 13 - Higher than 75 marks

https://www.hackerrank.com/challenges/more-than-75-marks/problem?isFullScreen=true


Code:-
    
   ``` 
   select Name from Students where marks>75 order by substr(Name,-3,3),id;


   ```
   


# 14 - The Blunder(using round function in integr)

https://www.hackerrank.com/challenges/the-blunder/problem?isFullScreen=true


Code:-
    
   ``` 
   select ceil(avg(salary)-avg(replace(salary,0,''))) from Employees;


   ```




# 15 - Weather observation 12

https://www.hackerrank.com/challenges/weather-observation-station-12/problem?isFullScreen=true


Code:-
    
   ``` 
   
   select distinct(city) from STATION where lower(substr(city,1,1)) not in('a','e','i','o','u') and lower(substr(city,-1,1)) not in('a','e','i','o','u')

   ```


# 16 - weather-observation-station-19 (Euclidean distance)

https://www.hackerrank.com/challenges/occupations/problem?isFullScreen=true


Code:-
    
   ``` 
   
   select Round((
   SQRT(Power((max(Lat_n)-min(lat_n)),2) + Power((max(Long_w)-min(long_w)),2))
),4) from STATION

   ```
