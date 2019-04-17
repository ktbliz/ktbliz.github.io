---
layout: post
title:      "SQL: Just the Commands!"
date:       2019-04-17 22:10:58 +0000
permalink:  sql_just_the_commands
---


## Another cheat sheet, this time for SQL commands. 

As I was going through the SQL lessons just now, I thought to myself: "OK I need a concise list of just these SQL commands." Then I started making it in my OneNote. THEN I decided I should just cut out the middle man and just make it directly in my blog. So here we are. 

### Command Line

sqlite3 database_name.db

sqlite3 database_name.db < sql_code.sql


### SQL Commands

.help

.quit

CREATE TABLE table_name(id INTEGER PRIMARY KEY, column1 TEXT, column2 REAL); 

.tables  

.schema  

ALTER TABLE table_name ADD COLUMN column_name TEXT;  

DROP TABLE table_name;  

INSERT INTO table_name (column1, column2, column3) VALUES ("Hey", 10, 2.5); 

SELECT column1, column2 FROM table_name;  

* Or: SELECT * FROM table_name;

SELECT DISTINCT column2 FROM table_name;
 
WHERE
 
* SELECT * FROM table_name WHERE column_name = some_value;  

* SELECT * FROM table_name WEHRE age < 2;  

 UPDATE table_name SET column_name = "new_name" WHERE column_name = "old_name";   

DELETE FROM table_name WHERE column_name = "value";  

ORDER BY  

* SELECT column_name FROM table_name ORDER BY column_name ASC|DESC; 

LIMIT  
