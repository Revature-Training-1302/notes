## Databases, SQL
- databases are a way to persist our data
- permanent storage rather than "storing" our data in memory of our Java program (temporary)

### SQL
- Structured Query Language
- Language - a set of commands/words that we can type to achieve some sort of functionality
- Query - How we specify what data we want to look at
    - ex: From all the pets, I just want to see the cats with blue eyes
    - ex: I want all dogs with brown fur who aren't adopted yet
- Structured - we define schemas and tables to store our data in an organized way
    - Instead of just something like a file directory where the files exists wherever they want

#### Dialects
- Different dialects of SQL that have slightly different syntax/commands
    - We will be learning PostgreSQL
    - Another common one is MySQL
- Do NOT get this confused with SQL sub-languages
    - SQL sub-languages refer to the grouping of different commands based on what they do
    - The sub-languages are DDL, DML, DQL, TCL, DCL (more on this later)
    - Every Dialect will have the different sub-languages

#### SQL vs NoSQL
- SQL is more about structure
    - rows and columns in our tables
    - rigid rules that tell us how our data is stored
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
    - stored similar to JSON
    ```
    {
        name: "rory",
        languages: ["java", "Javascript", "python"]
    }
    ```