# Architecture of DBMS

## Abstraction
It is a way of showing only the operation nd hiding their implementation details
The purpose of DBMS is to provide an abstract view of data to the users.The system hides certain details of how the data is stored and maintained
DBMS follows three level of architecture

**Low Level(Physical Level)**:Describes how data is actually stored on disk.Deals with storage structures, indexing, file organization, record placement, and access methods.

**Conceptual Level(Logical Level)**-Describes the entire database structure.Defines tables, relationships, constraints, etc.
***DBA(DataBase Adminstartor)***-A Database Administrator is a person or team responsible for the overall management of a database system. The DBA handles database design, security, backup and recovery, performance tuning, and ensures data integrity and availability.

**External Level(View Level)**-What individual users see.
Different users can have different views of the database.

## Instances and Schemas

**Instance**-An instance is the collection of information stored in a database at a particular point in time. It represents the current state of the database and changes whenever data is inserted, deleted, or updated.

**Schema**-A schema is the logical design or blueprint of a database that defines its structure, including tables, attributes, relationships, and constraints. It remains relatively stable and serves as the framework for storing data.

***Characteristics of Schema***:
- Defines the structure of the database.
- Specified during database design.
- Changes rarely.
- Also called the intension of the database.

**Types of Schema**:
- Physical Schema:Describes how data is stored physically.
- Logical (Conceptual) Schema:Describes tables, attributes, and relationships.
- View (External) Schema:Describes the part of the database visible to a particular user.

## Data Models
A data model is a collection of concepts used to describe the structure of a database, the relationships among data, and the constraints on the data. It provides a way to organize and represent data in a database system.

### Types:
 
#### Hierarchical Data Model
Data is organized in a tree structure.
Parent-child relationship.
Each child has only one parent.

#### Network Data Model
Data is organized as a graph.
A child can have multiple parents.
Supports many-to-many relationships.

#### Relational Data Model
Data is stored in tables (relations).
Rows = Records (tuples)
Columns = Attributes

#### Entity-Relationship (ER) Model
Represents data using:
Entities (objects)
Attributes (properties)
Relationships

#### Object-Oriented Data Model
Stores data as objects similar to OOP concepts.
Supports classes, inheritance, and methods.

## Data Base Languages
Database languages are special languages used to define, manipulate, retrieve, and control data in a database.The main language of database is SQL.SQL has all the features for data manipulation reterival and controlling of data in DB. SQL provides DDL, DML, DQL, DCL, and TCL commands for database management.

### DDL(Data Definition Language)
Used to define and modify the database structure.
**Commands**
- CREATE
- ALTER
- DROP
- TRUNCATE
- RENAME

### DML (Data Manipulation Language)
Used to insert, update, and delete data.
**Commands**
- INSERT
- UPDATE
- DELETE

### DQL (Data Query Language)
Used to retrieve data from the database.
**Command**:
- SELECT

### DCL (Data Control Language)
Used to control user permissions and security.
Commands:
GRANT
REVOKE

### TCL (Transaction Control Language)
Used to manage transactions.
Commands:
COMMIT
ROLLBACK
SAVEPOINT

### Queries:
A query is a request to a database for accessing, retrieving, modifying, or deleting data. Queries are written using SQL and enable users to interact with the database efficiently.

## How Does a Database Access Information from Application Programs (Java, C, etc.)?
Application programs such as Java and C access databases through database connectivity interfaces like JDBC and ODBC. The program sends SQL queries to the DBMS, which processes them and returns the requested data to the application.


## DBMS Application Architectures:
DBMS Application Architecture defines how users, applications, and databases interact.
#### Tier 1 Architecture
User, application, and database are on the same system.
Direct interaction with the database.
Mostly used for development and testing.

**Advantages**:
Simple to set up.
Fast communication.

**Disadvantages**:
Poor security.
Not suitable for multiple users.

#### 2-Tier Architecture (Client-Server)
Client application communicates directly with the database server.
Business logic is usually on the client side.

**Advantages**:
Better than 1-tier.
Easy to develop.

**Disadvantages**:
Limited scalability.
Database exposed directly to clients.

#### 3-Tier Architecture
Most widely used architecture.
Contains three layers:
Presentation Layer (Client)
Application Layer (Business Logic)
Database Layer
Client communicates with an application server, which then communicates with the database server.

Example
When you use Amazon:
Browser/App = Presentation Layer
Amazon's backend server = Application Layer
Database server = Database Layer

**Advantages**:
High security.
Easy maintenance.
Highly scalable.
Better performance for large applications.

**Disadvantages**:
More complex to design.



