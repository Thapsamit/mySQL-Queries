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
