```
import sqlite3                              
flag = 0                                        
try:                                                
    #Connecting to an existing database                                             
    conn, flag = sqlite3.connect('file:test.db?mode=ro', uri=True), 1                                           
    print('Connected to database')                                      
                                            
except sqlite3.Error as error:                                      
    print('Error occured - ', error)                                    
                                                
#Closing database Connection                                       
if flag:                                        
    conn.close()                                    
    print('Connection closed')  
```
    
![](images/connection.png)
