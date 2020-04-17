
# Lecture22 SQL I



this is the first part in a two part 
SQl is useful in creating tables, can manipulate and change the and get stuff from them 
SQL is a programming language that deals with data and database 
it is useful in creating tables you can create types of tables, you can manipulate them and change them and get stuff from them 

that would be a shame 

that includes your extra credit 



do not share code with anyone else beside your partner 
it is a way for you to be creative and create art 
heavyweight for people to 

first place winner 
you are not doing this alone 



write some blurbs 
a typical one 
have a vision for something 
this does not apply anymore 

make sure to check that out 
drop-in mentoring, fill it out 
reoccuring section 

artistic, this does not apply anymore 


# course overview 
every week will center around a theme with a specific set of goals 
study some additional paradigms that are useful in different areas of computing 



# declarative languages are basically a type of model or paradigm a way for us to compute things 

###### database - a structured set of data held in a computer. it is a big collection of data 

###### database manamagement system DBMS -- the software that creates software and manges databses 


###### the structured query language SQL (sequel) a programmign language that interacts with the DBMS. it is perhaps the most widely used programming language 
 it is most widely used, it is cross the fields, accountants use it 
###### a table is a collection of records which are rows that have a value for each column 

a table has columns and rows 
a column has a name and type 
a row has a value for each column 

these are strings presumbly and numbers 


# declarative versus imperative programming 
python & scheme are imperative programming languages 
imperative programming languages : 
1 a program is a description of computation processes. describe things are calculated 
2 the interpreter carrires out execution / evaluation rules 


SQL is a declarative programming language. declarative language: 
a program is a descritption of the desired result 
the interpreter figures out how to generate the results 
iterate through and prepare 

declarative programming ask someone for a table, it is the other person's job to do it 


Declarative programming - give me a table 

sqlite3 


sqlite> CREATE TABLE cities AS
   ...> SELECT 38 AS latitude, 122 AS longitude, "Berkeley" AS name UNION
   ...> SELECT 42,             71,            "Stanford"          UNION
   ...> SELECT 45,             93,           "Harvard";
sqlite> SELECT * FROM cities;
38|122|Berkeley
42|71|Stanford
45|93|Harvard

it says look at the first row 
sqlite> SELECT "west coast" as region, name FROM cities WHERE longitude >= 90 UNION
   ...> SELECT "other",    name from cities where longitude < 90
   ...> ;
other|Stanford
west coast|Berkeley
west coast|Harvard

it does a lot of complex optimization 


# SQL Overview 
the SQL language varies across implementations but we will lok at some sahred concepts 

## a SELECT statement creates a new table, either from scratch or by projecting a table 
## projecting a table means given an existing table, i can create another table from exisiting table 
## a CREATE TABLE statement gives a global name to a table 
select will just output it but won't save it into a name 
lots of other statements exist: DELETE, INSERT, UPDATE etc 




## getting started with SQL 
## SELECTing value literals 
## a select statement always includes a comma-separate list of column descriptions 

## a column description is an expression, optionally fllowed by AS and column name 
SELECT [expression] as [NAME], [expression] as [name],....;
SELECTing literals creates a one-row table 
## the UNION of two SELECT statements is a table containing the rows of both of their resultsets 


# Naming tables 
## SQL is often used as an interactive language 
## the result of a SELECT statement is displayed to the user, but not stored 
## a CREATE TABLE statement gives the result a name 
CREATE TABLE [name] AS [SELECT statements];


## projecting tables 
## SELECT statements project existing tables 
## a SELECT statement can specify an input table using a FROM clause 
## a subset of the rows of the input table can be selected using a WHERE clauses 
## remaining rows do not have an order or at east not in the scope of this, so orderin over the remaining rows can be declaring using an ORDER BY clause 



## column description determine how each input row is projected to a result row: 
## SELECT [columns] from [table] where [condition] ORDER BY[order][ASC/DESC]  LIMIT [number];


sqlite> SELECT * FROM cities ORDER BY name ASC;
38|122|Berkeley
45|93|Harvard
42|71|Stanford


even though technically you can leave this out , it is ordering in alphabetical order 

sqlite3 --init name.sql 



CREATE TABLE cities AS
  SELECT 38 AS latitude, 122 AS longitude, "Berkeley" AS name UNION
  SELECT 42,			 71,			   "Cambridge"        UNION
  SELECT 45,			 93,			   "Minneapolis";

CREATE TABLE parents AS
  SELECT "delano" AS parent,	"herbert" AS child UNION
  SELECT "abraham",			"barack"			  UNION
  SELECT "abraham",			"clinton"		  UNION
  SELECT "fillmore",			"abraham"		  UNION
  SELECT "fillmore",			"delano"			  UNION
  SELECT "fillmore",			"grover"			  UNION
  SELECT "eisenhower",		"fillmore";

CREATE TABLE dogs AS
  SELECT "abraham" AS name,	"long" AS fur	UNION
  SELECT "barack",			"short"			UNION
  SELECT "clinton",			"long"			UNION
  SELECT "delano",			"long"			UNION
  SELECT "eisenhower",		"short"			UNION
  SELECT "fillmore",			"curly"			UNION
  SELECT "grover",			"short"			UNION
  SELECT "herbert",			"curly";

CREATE TABLE grandparents AS
  SELECT a.parent AS grandog, b.child AS granpup
  FROM parents AS a, parents AS b
  WHERE b.parent = a.child;

CREATE TABLE restaurant AS
  SELECT 101 AS "table", 2 AS single, 2 AS couple UNION
  SELECT 102 		     , 0			    , 3			  UNION
  SELECT 103 	     	 , 4			    , 1;

CREATE TABLE ints AS
  SELECT "zero" AS word, 0 AS one, 0 AS two, 0 AS four, 0 AS eight UNION
  SELECT "one"         , 1	   , 0		, 0        , 0          UNION
  SELECT "two"         , 0	   , 2		, 0        , 0          UNION
  SELECT "three"       , 1	   , 2		, 0        , 0          UNION
  SELECT "four"        , 0	   , 0		, 4        , 0          UNION
  SELECT "five"        , 1	   , 0		, 4        , 0          UNION
  SELECT "six"         , 0	   , 2		, 4        , 0          UNION
  SELECT "seven"       , 1	   , 2		, 4        , 0          UNION
  SELECT "eight"       , 0	   , 0		, 0        , 8          UNION
  SELECT "nine"        , 1	   , 0		, 0        , 8;

CREATE TABLE nouns AS
  SELECT "dog" AS phrase	UNION
  SELECT "cat"		   	UNION
  SELECT "bird";

CREATE TABLE ands AS
  SELECT first.phrase || " and " || second.phrase AS phrase FROM nouns AS first, nouns AS second WHERE first.phrase <> second.phrase;





sqlite> SELECT child AS kids from parents;
barack
clinton
herbert
fillmore
abraham
delano
grover

we can rename the column name to something else 



# Arithmetic in SELECT Expressions 
## in a SELECT expression, column names evaluate to row values 
arithmetic expressions can combine row values and constants 


# joining two tables 
two tables A & B are joined by a comma to yield all combintions of a row from A & a row from B 
this is known as the cross product and will give num_rows in A * num_rows in B output rows 

this is called product, when we join them together, we have several rows 


sqlite> CREATE TABLE dog AS 
   ...> SELECT "abraham" AS name, "long" AS fur UNION 
   ...> SELECT "barack", "short"         UNION
   ...> SELECT "clinton",     "long"     UNION
   ...> SELECT  "delano",      "long"    UNION 
   ...> SELECT "elsenhower",    "short"   UNION
   ...> SELECT "filmore",      "curly";


now we have some tables to represent it 
select the parents of curly-furred dogs 

it is pretty methodical about this 

SELECT * FROM parents, dogs;

abraham|barack|abraham|long
abraham|barack|barack|short
abraham|barack|clinton|long
abraham|barack|delano|long
abraham|barack|eisenhower|short
abraham|barack|fillmore|curly
abraham|barack|grover|short
abraham|barack|herbert|curly
abraham|clinton|abraham|long
abraham|clinton|barack|short
abraham|clinton|clinton|long
abraham|clinton|delano|long
abraham|clinton|eisenhower|short
abraham|clinton|fillmore|curly
abraham|clinton|grover|short
abraham|clinton|herbert|curly
delano|herbert|abraham|long
delano|herbert|barack|short
delano|herbert|clinton|long
delano|herbert|delano|long
delano|herbert|eisenhower|short
delano|herbert|fillmore|curly
delano|herbert|grover|short
delano|herbert|herbert|curly
eisenhower|fillmore|abraham|long
eisenhower|fillmore|barack|short
eisenhower|fillmore|clinton|long
eisenhower|fillmore|delano|long
eisenhower|fillmore|eisenhower|short
eisenhower|fillmore|fillmore|curly
eisenhower|fillmore|grover|short
eisenhower|fillmore|herbert|curly
fillmore|abraham|abraham|long
fillmore|abraham|barack|short
fillmore|abraham|clinton|long
fillmore|abraham|delano|long
fillmore|abraham|eisenhower|short
fillmore|abraham|fillmore|curly
fillmore|abraham|grover|short
fillmore|abraham|herbert|curly
fillmore|delano|abraham|long
fillmore|delano|barack|short
fillmore|delano|clinton|long
fillmore|delano|delano|long
fillmore|delano|eisenhower|short
fillmore|delano|fillmore|curly
fillmore|delano|grover|short
fillmore|delano|herbert|curly
fillmore|grover|abraham|long
fillmore|grover|barack|short
fillmore|grover|clinton|long
fillmore|grover|delano|long
fillmore|grover|eisenhower|short
fillmore|grover|fillmore|curly
fillmore|grover|grover|short
fillmore|grover|herbert|curly
sqlite> SELECT * FROM parents, dogs;
abraham|barack|abraham|long
abraham|barack|barack|short
abraham|barack|clinton|long
abraham|barack|delano|long
abraham|barack|eisenhower|short
abraham|barack|fillmore|curly
abraham|barack|grover|short
abraham|barack|herbert|curly
abraham|clinton|abraham|long
abraham|clinton|barack|short
abraham|clinton|clinton|long
abraham|clinton|delano|long
abraham|clinton|eisenhower|short
abraham|clinton|fillmore|curly
abraham|clinton|grover|short
abraham|clinton|herbert|curly
delano|herbert|abraham|long
delano|herbert|barack|short
delano|herbert|clinton|long
delano|herbert|delano|long
delano|herbert|eisenhower|short
delano|herbert|fillmore|curly
delano|herbert|grover|short
delano|herbert|herbert|curly
eisenhower|fillmore|abraham|long
eisenhower|fillmore|barack|short
eisenhower|fillmore|clinton|long
eisenhower|fillmore|delano|long
eisenhower|fillmore|eisenhower|short
eisenhower|fillmore|fillmore|curly
eisenhower|fillmore|grover|short
eisenhower|fillmore|herbert|curly
fillmore|abraham|abraham|long
fillmore|abraham|barack|short
fillmore|abraham|clinton|long
fillmore|abraham|delano|long
fillmore|abraham|eisenhower|short
fillmore|abraham|fillmore|curly
fillmore|abraham|grover|short
fillmore|abraham|herbert|curly
fillmore|delano|abraham|long
fillmore|delano|barack|short
fillmore|delano|clinton|long
fillmore|delano|delano|long
fillmore|delano|eisenhower|short
fillmore|delano|fillmore|curly
fillmore|delano|grover|short
fillmore|delano|herbert|curly
fillmore|grover|abraham|long
fillmore|grover|barack|short
fillmore|grover|clinton|long
fillmore|grover|delano|long
fillmore|grover|eisenhower|short
fillmore|grover|fillmore|curly
fillmore|grover|grover|short
fillmore|grover|herbert|curly




i wanted to get only the parents of xxx 
sqlite> SELECT * FROM parents, dogs WHERE fur = "curly";
abraham|barack|fillmore|curly
abraham|barack|herbert|curly
abraham|clinton|fillmore|curly
abraham|clinton|herbert|curly
delano|herbert|fillmore|curly
delano|herbert|herbert|curly
eisenhower|fillmore|fillmore|curly
eisenhower|fillmore|herbert|curly
fillmore|abraham|fillmore|curly
fillmore|abraham|herbert|curly
fillmore|delano|fillmore|curly
fillmore|delano|herbert|curly
fillmore|grover|fillmore|curly
fillmore|grover|herbert|curly


sqlite> SELECT * FROM parents, dogs WHERE child = name;
abraham|barack|barack|short
abraham|clinton|clinton|long
delano|herbert|herbert|curly
eisenhower|fillmore|fillmore|curly
fillmore|abraham|abraham|long
fillmore|delano|delano|long
fillmore|grover|grover|short


we only care about the anything useful 

two tables may share a column names; dot expressions and aliases diambigudate column values 
SELECT [columns] FROM [table] WHERE [condition] ORDER BY [order];
[table] is a comma-separated list of table names with optional aliases 

SELECT * FROM parents AS a, parents AS b;
abraham|barack|abraham|barack
abraham|barack|abraham|clinton
abraham|barack|delano|herbert
abraham|barack|eisenhower|fillmore
abraham|barack|fillmore|abraham
abraham|barack|fillmore|delano
abraham|barack|fillmore|grover
abraham|clinton|abraham|barack
abraham|clinton|abraham|clinton
abraham|clinton|delano|herbert
abraham|clinton|eisenhower|fillmore
abraham|clinton|fillmore|abraham
abraham|clinton|fillmore|delano
abraham|clinton|fillmore|grover
delano|herbert|abraham|barack
delano|herbert|abraham|clinton
delano|herbert|delano|herbert
delano|herbert|eisenhower|fillmore
delano|herbert|fillmore|abraham
delano|herbert|fillmore|delano
delano|herbert|fillmore|grover
eisenhower|fillmore|abraham|barack
eisenhower|fillmore|abraham|clinton
eisenhower|fillmore|delano|herbert
eisenhower|fillmore|eisenhower|fillmore
eisenhower|fillmore|fillmore|abraham
eisenhower|fillmore|fillmore|delano
eisenhower|fillmore|fillmore|grover
fillmore|abraham|abraham|barack
fillmore|abraham|abraham|clinton
fillmore|abraham|delano|herbert
fillmore|abraham|eisenhower|fillmore
fillmore|abraham|fillmore|abraham
fillmore|abraham|fillmore|delano
fillmore|abraham|fillmore|grover
fillmore|delano|abraham|barack
fillmore|delano|abraham|clinton
fillmore|delano|delano|herbert
fillmore|delano|eisenhower|fillmore
fillmore|delano|fillmore|abraham
fillmore|delano|fillmore|delano
fillmore|delano|fillmore|grover
fillmore|grover|abraham|barack
fillmore|grover|abraham|clinton
fillmore|grover|delano|herbert
fillmore|grover|eisenhower|fillmore
fillmore|grover|fillmore|abraham
fillmore|grover|fillmore|delano
fillmore|grover|fillmore|grover



# Siblings 
SELECT * FROM parents, parents 
this does not work because the tables share a column 
this works ever through the columns are the same, they are aliased and SQL otpmizes for * 
let us now only keep rows where the children share a parent 
SELECT * FROM parents AS a, parents AS b where a.parent = b.parent 
we need to get rid of duplicate because pairs of silings appear twice 
we cand do this by enforcing an arbitrary ordering, a.child M b.child alphabetically 
when we get the two columns we want 

sqlite> SELECT * FROM parents AS a, parents AS b WHERE a.parent = b.parent AND a.child <> b.child;
abraham|barack|abraham|clinton
abraham|clinton|abraham|barack
fillmore|abraham|fillmore|delano
fillmore|abraham|fillmore|grover
fillmore|delano|fillmore|abraham
fillmore|delano|fillmore|grover
fillmore|grover|fillmore|abraham
fillmore|grover|fillmore|delano
sqlite> 



we want to enforce an ordering 

try this on your own 


which select statement evaluates to grandparents and grandchild 
sqlite> CREATE TABLE grandparents AS 
   ...> SELECT a.parent AS gradog, b.child AS granup
   ...> FROM parents as a.parents AS B 
   ...> WHERE b.parent = a.child;
sqlite> SELECT * FROM grandparents


joining multiple tables 
multiple tables can be joined to yield all combinations of rows from each other 
let's use this info to select all grand parents with the same fur as their grandchildren 
sqlite> CREATE TABLE grandparents AS 
   ...> SELECT a.parent AS gradog, b.child AS granup
   ...> FROM parents as a.parents AS B 
   ...> WHERE b.parent = a.child;
Error: table grandparents already exists
sqlite> SELECT * FROM grandparents




i am gonna need three way join , it is a cross product of three things 
sift through this mess 

SELECT * FROM grandparents, dogs AS d1, dogs AS d2;

that is our thought process 


# String expressions 
it is basically how we can use strings in our SQL queries 

string values can be combined to form longer strings 
sqlite> SELECT 'hello,' || 'world';
hello,world


sqlite> SELECT name || "dog" FROM dogs ;


sqlite> CREATE TABLE nouns as 
   ...> SELECT "dogs" || " what" as phrase UNION 
   ...> SELECT "cat" || " how" UNION
   ...> SELECT "birds" || " why" UNION 



SELECT n1.phrase || " and " || n2.phrase FROM nouns as n1, n2 where n1.phrase <> n2.phrase;



may sure the queue stays manageable 
we crammed a lot of materials 
topical ! 
hone in on them 
feel a bit reassured 


SQL is a declarative programming language that is used to create tables and manipulate them. very import 
we can project tables by using the SELECT statement 
FROM, ORDER BY, LIMIT, WHERE 
we can join tables to access multiple tables at the same time and aliasing them with dot notation 








