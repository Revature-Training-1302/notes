## Get to RDS
1. Click on Services.
2. Click on Database
3. Click on RDS

## Create the RDS instance
1. Click on DB Instances
2. Click "Create Database"
3. Standard Create
4. PostgreSQL
5. Choose 14.4 (or closest version)
6. *** IMPORTANT *** FREE TIER ***IMPORTANT ***
7. Give a DB instance identifier 
8. Keep the master username as postgres or change it
9. Fill out the master password and confirm. Remember this!
10. Keep Instance Configuration default
11. Keep Storage default
12. Under connectivity, set public access to yes
13. Keep the rest of the settings as default.

## Connecting to the Instance:
1. Click on the db identifier
2. Click on the security group under VPC security groups
3. Click on inbound rules
4. Click on "Edit inbound rules"
5. Click on Add Rule
6. For this new rule, select PostgreSQL under Type
7. Under Source, select my IP, the IP address should auto fill.
8. Click on Save Rules on the bottom right
9. Navigate back to the RDS instance to get the connection information. 
    - Particularly, the endpoint which should something like pet.cmm7dyyeb3rr.us-east-1.rds.amazonaws.com
10. Test out the connection on DBeaver. 
    - The database name is NOT the db identifier. It is probably still "postgres" if you didn't change it.
    - The password is whatever you configured on AWS
11. When you're done, you can configure your application.properties file to look something like this:
```
spring.jpa.properties.hibernate.dialect = org.hibernate.dialect.PostgreSQLDialect
spring.jpa.hibernate.ddl-auto=update
spring.jpa.hibernate.show-sql=true
spring.datasource.url=jdbc:postgresql://pet.cmm7dyyeb3rr.us-east-1.rds.amazonaws.com/postgres
spring.datasource.username=postgres
spring.datasource.password=harrypotter5!
```
