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
                INSERT INTO movies values ("Upendra", "Upendra", "Prema", 1999, "Upendra Rao");
                INSERT INTO movies values ("KGF", "Yash", "Shrinidhi Shetty", 2018, "Prashanth Neel");
                INSERT INTO movies values ("KGF2", "Yash", "Shrinidhi Shetty", 2022, "Prashanth Neel");
                INSERT INTO movies values ("The Prestige", "Matthew McConaughey", "Anne Hathaway", 2006, "Christopher Nolan");
                INSERT INTO movies values ("Top Gun: Maverick", "Tom Cruise", "Jennifer Connelly", 2022, "Joseph Kosinski");
                INSERT INTO movies values ("Doctor Strange in the Multiverse of Madness", "Benedict Cumberbatch", "Elizabeth Olsen", 2022, "Sam Raimi");
                INSERT INTO movies values ("Interstellar", "Christian Bale", "Scarlett Johansson", 2014, "Christopher Nolan");
                INSERT INTO movies values ("Batman Begins", "Christian Bale", "Katie Holmes", 2005, "Christopher Nolan");
                INSERT INTO movies values ("Vikram", "Kamal Haasan", "Shivani Narayanan", 2022, "Lokesh Kanagaraj");
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
