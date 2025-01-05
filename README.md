# SQL

## JOINS
+ INNER JOIN
```
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
```
+ LEFT JOIN
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
```
+ RIGHT JOIN
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
```
+ FULL JOIN
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
```
