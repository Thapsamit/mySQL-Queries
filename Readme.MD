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
