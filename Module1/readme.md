# Introduction to DBMS

Computer systems usually store their data in the form of bytes that contains bits 0 or 1

## Data
Raw collection of bits nd bytes that doesnt have any meaning without being processed is called data.Data is measured in bytes which are basic units of info

### Types:
- **Qualitative**: Descriptive data doesn't contains any numerical value eg name ,gender, weight
- **Quantitative**:Numerical form of data.Eg weight,volume

## Information
When we process the data the data becomes meaningful nd provide context on which we can make decesions this is called information

**Data does not depends on information but information depends on data**

## Database
A place where data can be saved we can organise data Here data can be accessed managed and updated smoothly.It is stored in the disk

## DataBaseManagementSystem(DBMS)
A software that is a collection of programs that contains all the features to create a database store data in it perform operations on the data It acts like an interface between the data nd the database 

## DBMS VS FILE SYSTEMS
Earlier when dbms was not there data was stored in the form of file format.This caused programmers to code for every feature every programmer has its own code that was opposed by new coder there was alot of incosistent data when dbms doesn't existed
 
### Disadvantages of file systems data storage:
**Data redundancy and inconsistency**-Means if one user saved his info in a bank in saving account nd the same user creates his account in current account there will be repeatative code this is data redundancy Now if user updates in his old account created by a developer 1 but there is no change in program of developer 2 than that is data is incosistency

**Difficulty in acessing data**: If the data is not organised properly then data acessing will be slow .Suppose we need people of picode 700061 then with file system it will take alot of time to acess the data compared to dbms

**Data isolation problem** :In a file system, data is stored in multiple separate files with different formats and locations. This makes accessing, updating, and combining data difficult. DBMS reduces data isolation by storing data in a structured and integrated database, allowing easy retrieval and sharing of information.

**Integrity Problem**: In a file system, maintaining the correctness and consistency of data is difficult because the same data may be stored in multiple files. If updates are not reflected everywhere, inconsistent data results, causing integrity problems. DBMS reduces this problem through integrity constraints and centralized data management.

**Atomicity Problem**:Atomicity means either a transaction is completed fully or not executed at all.In a file system, if a failure occurs during an operation, only some parts of the operation may be executed, leaving the data inconsistent. This is known as the atomicity problem. DBMS solves this by using transactions that ensure all-or-nothing execution.

**Concurrent Acess anamolies**:Concurrent access occurs when multiple users or transactions access the same data at the same time.
In a file system (and even in a DBMS without proper control), simultaneous access can lead to inconsistencies and unexpected results, known as concurrent access anomalies.

**Security Problems**:In a file system, protecting data from unauthorized access, modification, or deletion is difficult due to limited security controls. This can lead to data misuse and privacy violations. DBMS overcomes this problem through authentication, authorization, and access control mechanisms.



