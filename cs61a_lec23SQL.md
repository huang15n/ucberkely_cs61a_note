
# Lecture23 SQL II

sqlite3 --init 22.sql 



we are studying this idea of paradigm that are useful in different areas of computing 



SQL is what known as declarative programming 
we extend your knowledge


# Tables 
a table stores data . it consists 
a fixed number of colums 
data entires stored in rows 

to make a table in SQL, use a CREATE TABLE statement:
CREATE TABLE [name] AS ...;

to create rows of data , UNION together SELECT statements 


SELECT [exp] as [name], [expr] AS [name], .... UNION 
SELECT [exp] as [name], [expr] AS [name], .... UNION 
SELECT [exp] as [name], [expr] AS [name], .... UNION 
SELECT [exp] as [name], [expr] AS [name]..... ;

and so on and so forth,
to create rows of data from existing tables, use a SELECT statement with a FROM clause 

SELECT [columns] FROM [table] WHERE [condition]
ORDER BY [order] [ASC/DESC] LIMIT [number];

where allows us to specify rows and columns and limit the number of rows has a certain number of records 



Joins 
given multiple tables, we can join them together by specifying their names
separate by commas, in the FROM clause of a SELECT statement 
SELECT * FROM table1, table2;
when we join two tables , we get a new table with one row for each combinationof rows from the orginal tables 

it is kinda mouthful 
the cross product is you match up product where you match up every single row from one table with every single row from the other table


we include every single combination from all of the tables that we join together 

we have parents and chilren denoting that this crresponding to this 

again to reiterate, in order to put data into this data, i am using a bunch of select statement with data 


we get every single possible combination we include every column from all of the tables that we join together 

SELECT * FROM parents 
SELECT * FROM dogs 


joining tables is more interesting 
i want the names of all of certains types, in orer to do that we have to joi these ttablese together 

SELECT name FROM dogs WHERE fur = 'long';

 SELECT fur FROM parents, dogs WHERE parent = 'fillmore';
 SELECT name, parent, fur FROM parents, dogs WHERE parent = 'fillmore';


 sqlite> SELECT name, parent, fur FROM parents, dogs WHERE name = child AND parent = 'fillm
abraham|fillmore|long
delano|fillmore|long
grover|fillmore|short
that is a super important thing to remember when you are joining two tables you want to include some condition in your where caluse that allows you to keep only matching rows 




# Aggregation 
perrow operations: single table queries 
so far, our SQL statement have referred to the values in a single row at a time 



prerow opeations : single table queries 
so far, our SQL statement have referred to the values in a single row at a time 

write a query that outputs the name of xx that either have xx or are named xxx 
 SELECT name FROM dogs WHERE fur = 'long' OR name = 'grover';

when we use this WHERE clause, we use this value one at a time 
i mean i only look at one row at a time 

we can see the same thing happens with joins
write a query that outputs the names and types of all children 
SELECT name, fur FROM dogs, parents;



once i have this cross porduct, AND 
SELECT name, fur FROM dogs, parents WHERE parent = 'fillmore' AND name = child;
until i get something that matches my condition



# Aggregation is the process of doing operations on groups of rows instead of just a single row 
SQL provides aggregate functions whose return values can be used as entries in a column 


SELECT AVG(something) as another_thing FROM table_name;
the aggregation happens on this entire all these rows 

output the total number of rows:
SELECT COUNT(*) AS count FROM dogs;


because I do not care about the number of colums though they are all gonna have the same number of values 
we know star means all the number of columns 

the point of aggregration operation we are doing all points of colums 

Aggregation functions
MAX([columns]) the maximum value in the given columns 
MIN([columns]) the minimum value in the given columns 
AVG([columns]) the average value in the given column 
COUNT([columns]) the number of values in the given colum 
SUM([columns]) the sum of the values in the given column 

that takes in one column or start it can return you the number of values in the colum 

let's see this in actions more 
SELECT MIN(parents) AS first_alphabetically FROM dogs ;


# Groups 
by default, aggregation is performed over all the rows of the table 
if i count the rows i count all of the rows 
we can specify that we want to group rows based on values in a particuar column using GROUP BY calsue in a SELECT statement 


SELECT XX, AVG(something) as another_thing FROM table+name GROUP BY xxx;

more dtails on GROUP BY 
you can GROUP BY any valid SQL exprsesion , which includes using multiple column names and operators 


SELECT [colums] FROM [table] WHERE [condition] GROUP BY [order] [ASC/DESC] LIMIT [number] GROUP BY [exprssion];
a single group consists of all rows for which [expression] evalautes to the same value 
the output table will have one row per group 


Filtering groups 
we know how to filter individual rows using the WHERE clause 
the filter groups , use the HAVING [condition] clause 
HAVING which only specifies the xxx 
you can not do this in a WHERE clause because we can not specify each value there are by simply doing a where clause 

i want only if the minimum is xx ,if i match up xx 
the having clause takes care of xxxx




# Mutating tables 
in real database, is common pratice to initalize empty tables and add rows as new data is introduced 

to creat an empty table, use the CREATE TABLE statement , specifying the table name and colum names and possible default values 
CREATE TABLE [name]([columns]);
CREATE TABLE parents(parent, child);
CREATE TABLE dogs(value1,1, phrase DEFAULT, 'something')
this default value is to say if i ever insert some row into this 
and i do not specify a phrase , then the default value will just be nothing 


### to remove a table from our database, use the DROP TABLE statement:
DROP TABLE [IF EXIST] [name];
DROP TABLE something; 
DROP TABLE IF EXISTS something;

# Inserting records 
to insert rows into a table: 
INSERT INTO [table]([columns]) VALUES([values]),([values]);
CREATE TABLE something(xxx,xxx,phrase DEFAULT , 'xxx');
INSERT INTO table(column1,column2) VALUES(1,'2');
INSERT INTO table VALUES('1','one','three');
INSERT INTO table(col1, col2) VALUES ('one','two');


# Updating records 
to update existing entries in a table 
UPDATE [table] SET [colum] = [expression] WHERE [condition] 
to delete existing rows in a table 
DELETE FROM [table] WHERE [condition];



UPDATE table_name SET row1 = 'SOMETHING' WHERE col1 = 'something'
DELETE FROM table_name WHERE col = 'something' and row1 = 'SOMETHING';
i am gonna go ahead and change that row 


# Summary 
we can use aggregate functions to perform operations on a set of rows rather than on indivudla rows 
to specify an exprssion by which to group rows, use the GROUP BY clasue 
to filter groups based on condition over the whole group, use the HAVING clasue 
in real databases, we commonly initalize empty tables and insert, update or remoe records over time 










