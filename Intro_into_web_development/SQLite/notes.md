[Slides](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4495782-dt-content-rid-8380796_2/courses/1718-CM6112/Sqlite3.pdf)
The question marks are like parameters
```
conn = sqlite3.connect(DATABASE)     #connect to the database
cur = conn.cursor()
cur.execute("INSERT INTO Students     #execute the SQL command
('firstName', 'surname', … , 'public')\
VALUES (?,?,?,?,?)",
('Ian', 'Cooper', 'Cardiff', ‘Devon', "true") )
conn.commit()   #commit the data
conn.close()    #Close the connection
```
