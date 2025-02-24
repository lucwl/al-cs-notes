[PMT Notes](https://www.physicsandmathstutor.com/pdf-pages/?pdf=https%3A%2F%2Fpmt.physicsandmathstutor.com%2Fdownload%2FComputer-Science%2FA-level%2FNotes%2FAQA%2F10-Fundamentals-of-Databases%2FAdvanced%2F10.%20Fundamentals%20of%20Databases%20-%20Advanced.pdf)

# Databases

A database is an organised collection of structured information. 

## Data models

A *data model* is an abstract model of what to store and what information to record. It is made up of *entities* and *relationships*.

An *entity* is a thing about which data should be stored, e.g. a user.

An *attribute* is a characteristic or other piece of information about an entity, e.g. a username. 

A *relationship* is the way entities are related to one another.

Databases are formed of *tables* which are used to store multiple entities. Each entity is assigned its own row, with fields of that row storing the entity's attributes.

A database consisting of one table is known as a *flat file database*, while a database consisting or 2 or more tables is known as a *relational database*.

### Entity identifiers 

An entity identifier is a piece of data that uniquely identifiers a specific entity in a table. This is a key concept in relational database design, enabling the creation of *primary keys* and *foreign keys*.

In some tables, multiple attributes are combined to form an entity identifier, or *composite primary key*.

### Entity description

An entity description is used to describe what information is stored about an entity in a table:

Customer (<u>CustomerID</u>, CustomerName, CustomerAddress, CustomerEmail)

Underlined attributes form part of the entity identifier.

## Relational databases

The tables in a database can be related to each other, linked by common attributes.

There are three possible types of relationship between tables in a database:
- One-to-one
- One-to-many
- Many-to-many

### Entity-relationship diagrams

Entity-relationship diagrams (or ER diagrams) are used to graphically represent the relationships between tables in a database:
- Tables are shown as rectangles
- Lines represent different kinds of relationship

![[Pasted image 20250224182427.png]]

### Primary and foreign keys

A *primary key* is an attribute that provides a unique identifier for every entity in a database table. When tables are linked by a shared attribute, the attribute must be a primary key in one table and is called a *foreign key* in the other.

A primary key can be composed from multiple attributes in a single table, which is called a *composite primary key*.

## Database normalisation

Databases are normalised so that they can be more efficient without any compromise to the integrity of their data. Normalising databases involves ensuring that entities contain no redundant or repeated data.

A database that has been normalised allows for faster searching and sorting than an unnormalised database thanks to the smaller tables created in the normalisation process. They are also easier to maintain, duplication of data is minimised and data consistency is improved.

This helps reduce the number of update, insertion and deletion anomalies that occur.

### First normal form (1NF)

For a database to be in *first normal form*, it must have:
- **No repeating attributes**
- **All attributes must be atomic (no column contains more than one value)**

### Second normal form (1NF)

For a database to be in *second normal form*, it must have:
- **Satisfied first normal form**
- **No partial key dependencies (all attributes must depend on the entire composite key)**

### Third normal form (1NF)

For a database to be in *third normal form*, it must have no non-key dependencies.

> *All non-key attributes depend on the key, the whole key and nothing but the key*

## Structured Query Language (SQL)

SQL is a language used with databases. It is a declarative language, meaning that the programmer describes the result that's required rather than describing the process which should be followed.

There are four main SQL commands:
- SELECT
- UPDATE
- INSERT
- DELETE

### SQL Data Types

| Data type              | Description                                                                                                                         |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| CHAR(size)             | A string with the number of characters specified by size                                                                            |
| VARCHAR(size)          | A variable-length string with any number of characters specified to size                                                            |
| INT(size)              | A whole number of the number of bits provided by size                                                                               |
| FLOAT(size, precision) | A number stored using the number of bits specified by size with digits after the decimal point up the number specified by precision |
| DATE                   | A date in the form "YYYY-MM-DD"                                                                                                     |
| DATETIME               | A time and date in the form "YYYY-MM-DD HH:MM:SS"                                                                                   |
| TIME                   | A time in the format "HH:MM:SS"                                                                                                     |
| YEAR                   | A year in either the format "YY" or "YYYY"                                                                                          |

## Client server databases

A client server database provides simultaneous access to a database for multiple clients. For example, social media websites have many users which are continuously being accessed and multiple users simultaneously.

Users could request access to the same field at the same time, causing *concurrent access*. This can result in database updates being lost if two users edit a record at the same time.

This can be managed via the use of:
- **Record locks**
  When a record is accessed by one user, it is immediately locked to other users until the first user has finished using it. Other users are blocked from accessing or modifying the content of a field until the record has been unlocked.
- **Serialisation**
  Rather than locking a field, requests from other users are placed in a queue. Once the first user has finished using the field, the next command in the queue is executed and so on...
- **Timestamp ordering**
  Each command is assigned a timestamp which marks the point in time at which the field was initiated. The commands are issued in order of the 
- Commitment ordering