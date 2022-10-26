## Hackerrank Queries



## Day1


# 1 - Binary Tree Nodes Problem


https://www.hackerrank.com/challenges/binary-search-tree-1/problem


Code:-
    
   ``` 
   select N,IF(N in (select P from BST) and P is NULL,"Root",IF(N in (select P from BST) and P is not NULL,"Inner","Leaf")) from BST order by N

   ```

