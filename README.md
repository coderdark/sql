# SQL

## SELECT
```SQL
--All Users
SELECT users.email FROM user

--User with id 12345
SELECT users.email FROM user WHERE user.id = 12345

--Users that have ids in profile
SELECT users.email FROM users WHERE users.id IN (SELECT profile.auid FROM profile)
```

## JOINS
+ INNER JOIN
Retrieves records that contain matching values in both tables.
```SQL
        XXXXXXXXXXX        XXXXXXXXXXX        
     XXX           XXX  XXX           XXX     
   XX                 XXX                XX   
  X                  X▒▒▒X                 X  
 X                  X▒▒▒▒▒X                 X 
X                  X▒▒▒▒▒▒▒X                 X
X                  X▒▒▒▒▒▒▒X                 X
X                  X▒▒▒▒▒▒▒X                 X
 X                  X▒▒▒▒▒X                 X 
  X                  X▒▒▒X                 X  
   XX                 XXX                XX   
     XXX           XXX  XXX           XXX     
        XXXXXXXXXXX        XXXXXXXXXXX

SELECT users.email 
FROM users 
INNER JOIN profile 
ON users.id = profile.auid      
```
+ LEFT OUTER JOIN
Retrieves all records from the left table and the corresponding matched records from the right table.
```
        XXXXXXXXXXX        XXXXXXXXXXX        
     XXX▒▒▒▒▒▒▒▒▒▒▒XXX  XXX           XXX     
   XX▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒XXX                XX   
  X▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒X▒▒▒X                 X  
 X▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒X▒▒▒▒▒X                 X 
X▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒X▒▒▒▒▒▒▒X                 X
X▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒X▒▒▒▒▒▒▒X                 X
X▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒X▒▒▒▒▒▒▒X                 X
 X▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒X▒▒▒▒▒X                 X 
  X▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒X▒▒▒X                 X  
   XX▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒XXX                XX   
     XXX▒▒▒▒▒▒▒▒▒▒▒XXX  XXX           XXX     
        XXXXXXXXXXX        XXXXXXXXXXX

SELECT users.email 
FROM users 
LEFT OUTER JOIN profile 
ON users.id = profile.auid       
```
+ RIGHT OUTER JOIN
Retrieves all records from the right table and the corresponding matched records from the left table.
```
        XXXXXXXXXXX        XXXXXXXXXXX        
     XXX           XXX  XXX▒▒▒▒▒▒▒▒▒▒▒XXX     
   XX                 XXX▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒XX   
  X                  X▒▒▒X▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒X  
 X                  X▒▒▒▒▒X▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒X 
X                  X▒▒▒▒▒▒▒X▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒X
X                  X▒▒▒▒▒▒▒X▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒X
X                  X▒▒▒▒▒▒▒X▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒X
 X                  X▒▒▒▒▒X▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒X 
  X                  X▒▒▒X▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒X  
   XX                 XXX▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒XX   
     XXX           XXX  XXX▒▒▒▒▒▒▒▒▒▒▒XXX     
        XXXXXXXXXXX        XXXXXXXXXXX

SELECT users.email 
FROM users 
RIGHT OUTER JOIN profile 
ON users.id = profile.auid        
```
+ FULL OUTER JOIN
Retrieves all records that have a match in either the left or right table.
```
        XXXXXXXXXXX        XXXXXXXXXXX        
     XXX▒▒▒▒▒▒▒▒▒▒▒XXX  XXX▒▒▒▒▒▒▒▒▒▒▒XXX     
   XX▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒XXX▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒XX   
  X▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒X▒▒▒X▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒X  
 X▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒X▒▒▒▒▒X▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒X 
X▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒X▒▒▒▒▒▒▒X▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒X
X▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒X▒▒▒▒▒▒▒X▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒X
X▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒X▒▒▒▒▒▒▒X▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒X
 X▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒X▒▒▒▒▒X▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒X 
  X▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒X▒▒▒X▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒X  
   XX▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒XXX▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒XX   
     XXX▒▒▒▒▒▒▒▒▒▒▒XXX  XXX▒▒▒▒▒▒▒▒▒▒▒XXX     
        XXXXXXXXXXX        XXXXXXXXXXX

SELECT users.email 
FROM users 
FULL OUTER JOIN profile 
ON users.id = profile.auid       
```
