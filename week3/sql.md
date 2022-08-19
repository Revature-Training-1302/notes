## Databases, SQL
- databases are a way to persist our data
- permanent storage rather than "storing" our data in memory of our Java program (temporary)
- SQL = Structured Query Language
- Language - a set of commands/words that we can type to achieve some sort of functionality
- Query - How we specify what data we want to look at
    - ex: From all the pets, I just want to see the cats with blue eyes
    - ex: I want all dogs with brown fur who aren't adopted yet
- Structured - we define schemas and tables to store our data in an organized way
    - Instead of just something like a file directory where the files exists wherever they want

### Dialects
- Different dialects of SQL that have slightly different syntax/commands
    - We will be learning PostgreSQL
    - Another common dialect is MySQL
- Do NOT get this confused with SQL sub-languages
    - SQL sub-languages refer to the grouping of different commands based on what they do
    - The sub-languages are DDL, DML, DQL, TCL, DCL (more on this later)
    - Every Dialect will have the different sub-languages

### SQL vs NoSQL
- SQL is more about structure
    - rows and columns in our tables
    - rigid rules that tell us how our data is stored
    - relational databases - we have different tables that are related to each other
    ```
    Programmer
    Name                Language
    Rory                  Python
    Huy                   Java
    Abderrahim       JavaScript
    ```
    - we can set up queries:
    - ex: 
    ```SQL
    select * from Programmer where Language = 'Java';
    ```
- NoSQL - less rigid
    - not relational
    - stored similar to JSON
    ```
    {
        name: "rory",
        languages: ["java", "Javascript", "python"]
    }
    ```

## Relational Databases
- Database - a collection of data, we usually have one or more databases for a single project
    - You wouldn't want one database to be used for multiple projects
    - The default database when we use postgreSQL is called "postgres"
    - A database could have many different tables
- Table - represents a specific entity/object/relation that we want to store
    - ex: Pet, Owner, Book, Account
    - Within a table, we store our data in a certain way
    - Columns - define the fields of our data (name, id, species, age)
        - like our fields in Java
    - Rows - the actual records of our data
        - like instances in Java
    - A row would represent the individual instance of the data, kind of like an instance of an object
        - ex: in a pet table, if we have 50 rows, that would mean we have 50 individual pets
- Relational - meaning we can relate two related tables
    - For example, a pet table and an owner table
    - Account table, item table
    - Player table, sword table

### Single Table in a Database:
- columns are the fields (name, city, salary)
- each row is a completely different entry in the table:

![Single Table](https://cdn.hswstatic.com/gif/relational-database-chart.jpg)

### Multiple Tables in a Database:
- In a single project, we can have many entities/tables
- And they are connected in some way
- An employee can have many different devices
- An employee can also belong to many different departments
- A department could have many different employees

![Multiple Tables](https://www.oreilly.com/library/view/modern-big-data/9781787122765/assets/ac4ab76e-e06b-41b5-9231-f62397744054.png)


### Multiplicity Relationships
- These are relationships between multiple tables
1. One-to-One
    - One entity maps/connects to exactly one entity
    - Person entity to Social Security Card
        - A single person only has 1 social security card
        - A social security card only has one person associated with it
2. One-to-Many
    - One entity has 0 or more relations with another entity whereas the other entity only belongs to 1 entity
    - Social Media, you might see a post with a lot of comments
    - One post could have 0 or more comments
    - But that one comment would only belong to that post
        - One comment can't be associated with multiple posts
3. Many-to-Many
    - One entity connects to many other entities which each can connect to many others
    - Ex: Employees to departments
    - One department is going to have 1 or more employees
    - Employee can belong to multiple departments

## Sub-languages
1. Data Definition Language (DDL) - all about creating tables, setting up the structure, modifying the columns
    - create - create a table in SQL
        - can only create a table once, otherwise SQL will yell at you "Error relation already exists"
        - can check if the table exists
        ```sql
        create table if not exists pet....
        ```
        - the "if not exists" makes sure that the table doesn't exist before we create it
    - alter - alter a pre-existing table in SQL
        - affect the columns, constraints, and the structure of the table, but not necessarily the data itself
        ```sql
        alter table pet rename column foood to food;
        ```
    - drop - get rid of a table
        - check if the table exists
        ```SQL
        drop table if exists pet
        ```
        - the "if exists" checks that the table exists before we try to drop it
    - truncate - completely wipe a table of it's data, keeps the table just without data
    ```sql
    truncate fruits;
    ```
2. Data Manipulation Language (DML) - all about the data in the table, modifying/manipulating the rows (not the columns)
    - insert - add new data to the table
        - we can specify the fields:
        ```sql
        insert into pets (id, name, species, food) values (1, 'ashes', 'cat', 'tuna');
        ```
        - or not
        ```sql
        insert into pets values (1, 'ashes', 'cat', 'tuna');
        ```
        - If we don't specify the fields, we have to make sure we match the order that the fields were defined in the table
    - update - update existing data
        - usually have a where clause to specify which records we're changing
        ```sql
        update pets set name = 'garfield' where id = 1;
        ```
    - delete - remove data from the table
        - should have a where clause to specify which records we are deleting
        ```sql
        delete from pets where id = 1;
        ```
    - Delete and Update commands without a where clause are dangerous, they will affect the entire table!!!
3. Data Query Language (DQL) - all about reading data from our table
    - select - selecting data from table
        - General Structure: ```select <columns> from <table> where <condition>```
        - specify which columns we want to view
        - where condition to specify which rows we want to see
        - the * indicates that we want every column:
        ```sql
        select * from person;

        -- specify columns
        select name, occupation from person;

        -- specify rows:
        select * from person where occupation = 'wizard';
        ```
    - "like" keyword, used to compare strings
    - % sign is a catch-all delimiter
    ```sql
    select * from person where name like '%y';
    ```
    - order by column, order the results in numerical or alphabetical order based on the data type of the column
        - if we specify multiple columns, the additional columns will be used to break ties
        - we can specify asc for ascending or desc for descending, but the default will be ascending if you don't specify
    ```sql
    select * from person order by salary asc, name desc;
    ```
    - limit, lets us limit the number of rows from a query
    ```sql
    select name, salary from person order by salary asc limit 5;
    ```
    - group by - group the results by a certain column
    - having - like "where" but acts on a group of records rather than an an indivual record
    ```sql
    select occupation, avg(salary) from person group by occupation having avg(salary) > 500;
    ```
    - set operations operate on the results of 2 queries
        - union - takes everything from either query
        - intersect - takes records that exist in both queries
        - union all - takes everything from either query and doesn't remove duplicates
        - except - takes everything from the first query except the results from the second query
    ```sql
    (select * from person where occupation = 'wizard')
    intersect -- intersect operation takes records that are in both results
    (select * from person where salary > 500);
    ```
    - sub-query  - using a query within another query:
    ```sql
    select * from person where salary >
    (select avg(salary) from person); -- sub-query because it exists within the outer query
    ```
    - views - temporary storing of the results from a query:
    - The views you create should show up under "views" on the left sidebar in DBeaver
    ```sql
    create view rich_wizards as
    select * from person where occupation = 'wizard' and salary >= 1000;

    select * from rich_wizards;
    ```
4. Transaction Control Language (TCL)
    - transaction - sets of (usually DML) commands in SQL
    - Commands in SQL
        - Begin - begin/start a transaction
        - Commit - at the end of our transaction, once we've written our commands, we can commit or persist those changes to the database
        - Rollback - return to the state before we began the transaction
        - Save point - set custom save points to return to

5. Data Control Language
    - controlling who has access to the data
    - mostly useful when we have mulitple users
    - default username is postgres and the password whatever we set
        - but we can create other users that have different permissions
    - Two commands:
        - grant - give permission to a user certain operations on a table
        - revoke - remove permissions from a user on a table
    ```sql
    revoke insert, update, delete on financial_information from intern;
    grant select on financial_information to intern;
    ```

## Joins
- a way to combine data from multiple tables
    - especially useful if we have multiplicity relationships between tables
### Different Types of Joins:
1. Inner Join - we only take records that has matches in both tables:
    - No null values
```sql
select person.name, pet.name from person join pet on pet.owner_id = person.id order by person.name;
```
2. Left Outer Join - we take all records from the left side, but not everything from the right side
    - We could have null values in the columns from the right table
```SQL
select person.name as person_name, pet.name as pet_name 
from person left outer join pet 
on pet.owner_id = person.id 
order by person.name;
```

3. Right Outer Join - we take all records from the right side, but not everything from the left side
    - Now we could have null values in columns from the left table
```sql
select person.name as person_name, pet.name as pet_name 
from person right outer join pet 
on pet.owner_id = person.id 
order by person.name;
```

4. Full Outer Join - we take all records from both tables, and leave null values where there are no matches:
    - now we can have null values in either table
```sql
select person.name as person_name, pet.name as pet_name 
from person full outer join pet 
on pet.owner_id = person.id 
order by person.name;
```
- anoter example of full outer join https://www.w3schools.com/sql/sql_join_full.asp

![diagram of joins](https://dq-blog-files.s3.amazonaws.com/joins-tutorial/join_venn_diagram.svg)



## Functions in SQL
### Aggregate Functions
- Act on a group of records
- Examples
    - Min
    - Max
    - Avg
    - Sum
    - Count
    - First
    - Last

### Scalar Functions
- Act on a single record
- Examples
    - lower
    - upper
    - length

- Some more examples of functions: https://www.geeksforgeeks.org/sql-functions-aggregate-scalar-functions/

## Truncate vs Delete vs Drop
- truncate is going to wipe out a table completely
- delete is going to delete records based on a condition
    - if there is no condition, it acts the exact same way as truncate
    - delete from fruits is the same as truncate fruits;
- drop gets rid of the entire table




## Data types:
- integer - like an int in Java, store whole numbers
- serial - like an integer, but it allows us to use the default keyword when inserting values to follow the sequence (incrementing by 1)
- varchar - like a String in java, lets us store words, sentences
    - we have to declare the size (how many characters) when we make it, usually I use 50 as the default
- date - store a date with year, month, day
    ```sql
    update person set bday = '1970-01-01';
    ```
    - we can use < to check if a data is earlier
    - we can use > to check if a data is later
- timestamp- store date with time
```sql
insert into work_times values ('2016-06-22 19:10:25-07');
```
- List of data types: https://www.geeksforgeeks.org/postgresql-data-types/ 

## Sequences
- When we use the serial keyword in SQL, we create a sequence table
- The table starts at 1 and goes up by 1 every time we insert into the corresponding table using the default keyword

## Constraints
- Constraints are restrictions we can place on columns to ensure our table acts/works in the way we expect them to
### Keys
#### Primary Keys
- Used to identify a record in a table
- Requires that a column is unique and non-null
    - This is helpful for ids because ids need to be unique, different from each other
    - Non-null because you want a valid value for the id
    - By adding the primary key constraint to a column, it automatically guarantees that the values will be unique and non-null
    
##### Primary Key vs Serial
- While these concepts are related, they do not do the same thing
- The primary key constraint ensures that values placed in the table are
    - non-null, they have a value
    - unique, values can't repeat
- The usage of the serial data type allows for the auto-increment of the values
- We usually use both for an id column

#### Foreign Keys
- foreign keys are used to connect 2 different tables
- they help us to achieve multplicity relationships
- we use the "references" keyword in SQL to set up a foreign key relationship
    - ```references person``` would reference the primary key by default
    - ```references person(age)``` would reference the age field
```sql
create table if not exists pet(id serial primary key, name varchar(50), owner_id integer references person(id));
```
- Foreign keys help to achieve referential integrity
    - We can't reference a record that doesn't exist
##### Referential Integrity
- When an inserting/update a row that references another table, we want to make sure that reference actually exists
    - trying to have a pet reference owner id 3, where there is no owner with id 3
- When deleting/dropping records, we want to make sure no other records/tables rely on what we're deleting
- By using foreign keys, the program will error if this happens
- We can use the "cascade" keyword when deleting to delete all references to objects that are being deleted

### Default
- we can assign a default value for a column by altering it
```sql
alter table food alter column name set default 'pancakes';
```
- when we insert, we can use the default key-word instead of an actual value, and it will insert that value into the database
```sql
insert into food (id, name) values (1, default)
```
- We also use the default keyword when we have a serial data type
    - the default value is the next value in the sequence


### Checks
- when setting up our table we can set up conditions for which all records must pass before they are inserted into the table
- 
```sql
create table if not exists person (id serial primary key, name varchar(50), occupation varchar(50), salary integer check (salary > 0));
```


### Exercises
- [Optional Exercises](https://www.w3schools.com/sql/exercise.asp)