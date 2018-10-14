#### Key
* Superkey is the combination of one or many attribute that can uniquely identify one entity of entityset.  
* candidatekey is the minimum superkey that is uniquely identify the entity of entityset.  
* primary key is the only one key candidate key that choose by the database desirer or DBA as the mean of identify an entity.  
* alternate key is the candidate key that haven't choose by the database adminstrator.  
##### Type of key 
* unique, composite key, surrogate 
* unique key is the key that contain unique value cannot duplicate, cannot updatable, and can contain null value.
* surrogate key is the key that cannot contain unique value bu cannot contain null value and updatable.
* composite key is primary key that contain more than one attribute.  
#### mappint cardinality
* one to one : one entity in entity set  A is associated in only one entity in entity set in B. and one entity in entity set in B can associated with only one entity in entity set in A.  
* one to many : one entity in entity set  A is associated with zero or more entity in entity set in B. and one entity in entity set in B can associated with only one entity in entity set in A.  
* many to one : one entity in entity set  A is associated in only one entity in entity set in B. and one entity in entity set in B can associated with zero or more entity in entity set in A.  
* many to many : one entity in entity set  A is associated in zero or more entity in entity set in B. and one entity in entity set in B can associated with zero or more entity in entity set in A.  
#### Relationship and relationshipset  
* Relationship is the entity is the association amount several entity  
* Relationship set is the set of relationship of the same type.  
#### E-R Diagram
* ER diagram can express the overall logical structure of a database graphically.
* there are 8 major component of ER diagram are: 
* Rectangle is represent the Entity 
* ellipse is represent the attribute 
* Diamond is representing the relationship 
* line denote the link
* double ellipse is denote the multi value attribute
* double line denote total participation
* dash ellipse denote the derive attribute
* Double rectangle denote weak entity set 
* symbol in ER Diagram
* double diamond is weak relationship set
![pic](https://c45442fe-a-62cb3a1a-s-sites.googlegroups.com/site/merasemester/dbm/chapter-3/ERD.bmp?attachauth=ANoY7cpkt-RBFpKmUMXWCNU7ZMjlx9OOouItO3kHppH7TvkOwqNRH2J39zbxs3qVugdmDJ9lFk1ZNrD3yyTCbA3Uap_Kux2_vPNosm0Hb9FfxruRNBlfKBgd2ap-gnfVUkMfVYEwD5Gmddp-Olh0QHska2qjWfqmjHv9fm-Pot-gJnQr5WXRUIZ0fJDUT74G7mTZLXFrgUt7w62zDOtL61enjFPsSWwpo90GGbhO4Fty4Bk9zWDmdUQ%3D&attredirects=0)  
#### mapping in cardinality in er diagram
#### Classification of Entity sets
1. total participate
2. partial participate
#### Relationship Degree
1. binary relationship set
2. ternary relationship set 
3. N-nary relationship set
#### relationship classification == mapping caldinality
#### 
SQL is the most influential commercially marketed relational query language.
The SQL language has several parts:
* Data-definition language (DDL), which provides commands for defining
relation schemas, deleting relations, and modifying relation schemas.
* Data-manipulation language (DML), which includes a query language
and commands to insert tuples into, delete tuples from, and modify tuples
in the database.
#### Data type
The SQL standard supports a variety of built-in types, including:
* char(n): A fixed-length character string with user-specified length n. The full
form, character, can be used instead.
* varchar(n): A variable-length character string with user-specified maximum
length n. The full form, character varying, is equivalent.
* int: An integer (a finite subset of the integers that ismachine dependent). The
full form, integer, is equivalent.
* smallint: A small integer (a machine-dependent subset of the integer type).
* numeric(p, d):Afixed-point numberwith user-specified precision. The number
consists of p digits (plus a sign), and d of the p digits are to the right of
the decimal point. Thus, numeric(3,1) allows 44.5 to be stored exactly, but
neither 444.5 or 0.32 can be stored exactly in a field of this type.
* real, double precision: Floating-point and double-precision floating-point
numbers with machine-dependent precision.
* float(n): A floating-point number, with precision of at least n digits.
#### SQL Constraints
````
CREATE TABLE table_name (
    column1 datatype constraint,
    column2 datatype constraint,
    column3 datatype constraint,
    ....
);
````
SQL constraints are used to specify rules for the data in a table.  
Constraints are used to limit the type of data that can go into a table. This ensures the accuracy and reliability of the data in the table. If there is any violation between the constraint and the data action, the action is aborted.  
Constraints can be column level or table level. Column level constraints apply to a column, and table level constraints apply to the whole table.  
The following constraints are commonly used in SQL:
* NOT NULL - Ensures that a column cannot have a NULL value
* UNIQUE - Ensures that all values in a column are different
* PRIMARY KEY - A combination of a NOT NULL and UNIQUE. Uniquely identifies each row in a table
* FOREIGN KEY - Uniquely identifies a row/record in another table
* CHECK - Ensures that all values in a column satisfies a specific condition
* DEFAULT - Sets a default value for a column when no value is specified
* INDEX - Used to create and retrieve data from the database very quickly

#### Aggregate functions
Aggregate functions are functions that take a collection (a set or multiset) of values  
as input and return a single value. SQL offers five built-in aggregate functions:  
* Average: avg
* Minimum: min
* Maximum: max
* Total: sum
* Count: count
* Group: Group by ... having ...
#### Transaction
A transaction consists of a sequence of query and/or update statements. The SQL
standard specifies that a transaction begins implicitly when an SQL statement is
executed. One of the following SQL statements must end the transaction:
* Commit work commits the current transaction; that is, it makes the updates
performed by the transaction become permanent in the database. After the
transaction is committed, a new transaction is automatically started.
* Rollback work causes the current transaction to be rolled back; that is, it
undoes all the updates performed by the SQL statements in the transaction.
Thus, the database state is restored to what it was before the first statement
of the transaction was executed.
#### View 
A View is nothing more than a SQL statement that is stored in the database with an associated name.  
A View is actually a composition of a table in the form of a predefined SQL query.  
A View can contain all rows of a table.   
A View can be created from a single table, multiple tables or another view, which depends on the written SQL query to create a view.  
````
Create view faculty as
Select ID, name, dept_name
from instructor;
````
we can :  
* insert : Insert not included all the NOT NULL columns.  `insert into faculty values (‘30765’, ‘Green’, ‘Music’);`
* update `update faculty set ID = ‘65498’ where name = ‘Green’;`
* delete `Delete from faculty where ID = ‘65498’;`
* drop view `drop view faculty;`
#### Authorization
⇒ It is the process of giving someone permission to do or to have something.  
Basic Authorization:  
 we can use any one form or combination of the following basic forms of authorizations  
* Resource authorization: Authorization to access any system resource  
* Alternation Authorization: Authorization to add attributes or delete attributes from relations  
* Drop Authorization:   
Authorization to drop a relation   
A file system identified certain privileges on the files or objects that it manages.  
A file system identified certain participants to whom privileges may be granted.   

Database management system allows database administrator to give different access rights to the users as per their requirements. It defines for the database which users are allowed to access and what privileges of use.  
#### Types of Privileges
The 4 main types of privileges are: 
* SELECT: allow user to read tuples in the relation.
* INSERT: allow user to insert tuples into the relation.
* UPDATE: allow user to update any tuple in the relation.
* DELETE: allow user to delete tuples from the relation.  

All privileges: use as a short form for every privileges.  
##### Granting Privileges
* Is done by using the GRANT keyword
* Use to give particular privilege to particular user on particular relation  

Syntax:
`GRANT <privilege lists> on <relation name/view name> to <user/role lists>;`  
Example:  GRANT select on department to Amit, Satoshi;
##### Revoking Privileges
* Is done by using the REVOKE keyword
* Use to take away particular privilege from particular user on particular relation  

Syntax:
`REVOKE <privilege lists> on <relation name/view name> from<user/role lists>`  
Example: REVOKE select on department from Amit, Satoshi;  

##### Transfering Privileges
* Is done by using the WITH GRANT OPTION keywords
* Use to allow particular user that we have grant privileges to be able to pass on those privileges to other user  

Syntax: 
`GRANT <privilege lists> on <relation name/view> to <user/role lists> WITH GRANT OPTION;`
Example: GRANT select on department to Amit WITH GRANT OPTION;  
Now the user Amit has the right to grant privileges to other user also.  
#### Roles
* Use the CREATE ROLE statement to create a role, which is a set of privileges that can be granted to users or to other roles.  
* You can add privileges to a role and then grant the role to a user. The user can then enable the role and exercise the privileges granted by the roles.  

Create role ‘account’;  
Grant instructor to account;  
Grant account to Amit, Satoshi;  
#### Assertions
* Assertion is any condition that the database must always satisfy
* It can only check condition

Form of creating assertion:  
Create assertion <assertion-name> check <predicate>;  
#### Trigger
* We describe triggers, which can be used to specify action that are to be carried out automatically on certain events such as insertion, deletion, or update of tuples in a specified relation.
* A trigger is a statement that the system executes automatically as a side effect of a modification to the database.
* Triggers are also useful mechanisms for alerting humans or for starting certain tasks automatically when certain conditions are met.

#### Data Warehouse
_ is a large store of data gathered from wide range of source and is used to guide management decisions.

Characteristics of data warehouse:
* Integrated: the way data is extracted and transformed is uniform, regardless of its source
* Time-variant: Data is organized via time period
* Non-volatile: data warehouse is not update in real time, to protect from momentary change

Benefits of data warehouse: 
* Provide historical intelligence
* The enablement of good decision making
* Quick and easy data access
* Consistent data quality

Types of data warehouse:
* Enterprise data warehouse
* Data mart
* Virtual warehouse

#### View
 view is a virtual table based on the result-set of an SQL statement.
CREATE VIEW CUSTOMERS_VIEW AS SELECT name, age FROM  CUSTOMERS;

#### Advantages of ER modeling 
* Conceptually it is very simple = simple and easy to draw if we know relationship between the entities and attributes
* Better visual representation = is a diagrammatic representation that we can easily understand 
* Effective communication tool = is an effective communication tool for database designer 
* Highly integrated with relational model  = ER model can be easily converted into relational model 
* Easy conversion to any data model = ER model can be easily converted into another data model 

#### Disadvantages of ER modeling 
* limited constraints 
* loss of information content 
* limited relationship representation 
* no representation of data manipulation 
* popular for high level design 
* no industry standard for notation 

