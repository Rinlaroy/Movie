```
import sqlite3
flag = 0
try:
    #Connecting to an existing database
    conn, flag = sqlite3.connect('movie.db'), 1
    print('Connected to database')

    #Creating cursor
    cur = conn.cursor()
    
    insert = """INSERT INTO movies values ("Inception", "Leonardo DeCaprio", "Marion Cottillard", 2010, "Christopher Nolan");
                INSERT INTO movies values ("Bangalore days", "DulquerSalman", "Nazriya", 2014, "AnjaliMenon");
                INSERT INTO movies values ("KGF", "Yash", "Shrinidhi Shetty", 2018, "Prashanth Neel");
                INSERT INTO movies values ("KGF2", "Yash", "Shrinidhi Shetty", 2022, "Prashanth Neel");
                INSERT INTO movies values ("The Prestige", "Matthew McConaughey", "Anne Hathaway", 2006, "Christopher Nolan");
                INSERT INTO movies values ("Ohm Shanthi Oshana", "Nivin Pauly, "Nazriya", 2011, "Rajan");
                INSERT INTO movies values ("Drishyam", "Mohanlal", "Menna", 2020, "JeethuJoseph");
                INSERT INTO movies values ("Interstellar", "Christian Bale", "Scarlett Johansson", 2014, "Christopher Nolan");
                INSERT INTO movies values ("Premam", "NivinPauly", "Sai Pallavi", 2005, "rajan");
                INSERT INTO movies values ("Veera", "Ajith", "Ramya", 1999, "kango");
            """

    cur.executescript(insert)
    conn.commit()
    print("Record inserted successfully into movies table ")

except sqlite3.Error as error:
    print('Error occured - ', error)
  
# Closing database Connection
if flag:
    conn.close()
    print('Connection closed')
```
![](images/insert.png)
