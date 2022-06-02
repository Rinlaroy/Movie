```
import sqlite3
flag = 0
try:
    #Connecting to an existing database
    conn, flag = sqlite3.connect('movie.db'), 1
    print('Connected to database')

    #Creating cursor
    cur = conn.cursor()

    select = """SELECT * FROM movies;"""
    cur.execute(select)
    result = cur.fetchall()
    print(result)

    param = """SELECT * 
            FROM movies 
            WHERE lead_actor='Yash';
            """
    cur.execute(param)
    print(cur.fetchall())

except sqlite3.Error as error:
    print('Error occured - ', error)
  
# Closing database Connection
if flag:
    conn.close()
    print('Connection closed')
```
![](images/query.png)
