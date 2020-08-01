# SQL
 make the Dillard’s database your default database.  To do that, execute the following command: 
 DATABASE ua_dillards; 
 
 Instead of using SHOW or DESCRIBE to get a list of columns in a table, use: 
 HELP TABLE [name of table goes here; don’t include the brackets when executing the query] 
 
 
 To get information about a single column in a table, you could write: 
 HELP COLUMN [name of column goes here; don’t include the brackets when executing the query] 
 
 One thing that is missing from the information outputted by HELP is whether or not a column is a primary or foreign key.  In order to get that information, use a SHOW command: 
 SHOW table [insert name of table here; don’t include the brackets when executing the query]; 
 However, SHOW does something different in Teradata than it does in MySQL.  Teradata uses SHOW to give you the actual code that was written to create the table. 
 
 Exercise 1.  Use HELP and SHOW to confirm the relational schema provided to us for the Dillard’s dataset shows the correct column names and primary keys for each table.  
 
 
 
Most of the syntax you use to look at your data in Teradata is the same you use in MySQL.  One of the main differences is Terdata uses a TOP operator instead of a LIMIT operator to restrict the length of a query output. 


 The following statement would select the first 10 rows of the strinfo table, ordered in ascending alphabetical order by the city name (you would retrieve names that start with “a”): 
 SELECT TOP 10 * FROM strinfo ORDER BY city ASC 
 
 The following statement would select the first 10 rows of the strinfo table, ordered in descending alphabetical order by the city name (you would retrieve names that start with “w” and “y”): 
 SELECT TOP 10 * FROM strinfo ORDER BY city DESC 
 
 The following query would retrieve 10 random rows from the strinfo table:   
 SELECT * FROM strinfo SAMPLE 10 
 
 The following query would retrieve a random 10% of the rows from the strinfo table: 
 
SELECT * FROM strinfo SAMPLE .10 
 
 -­‐ DISTINCT and LIMIT can be used in the same query statement in MySQL, but DISTINCT and TOP cannot be used together in Teradata 
 -­‐ MySQL accepts either double or single quotation marks around strings of text in queries, but Teradata will only accept single quotation marks 
 -­‐ MySQL will accept the symbols “!=” and “<>” to indicate “does not equal” but Teradata will only accept  “<>” (other operators, like “IN”, “BETWEEN”, and “LIKE” are the same: http://www.teradatawiki.net/2013/09/Teradata-Operators.html) 
 
 
 
