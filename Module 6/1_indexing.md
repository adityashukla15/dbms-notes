# Indexing In DBMS
Indexing is a technique used to improve the speed of data retrieval from a database.
Think of it like the index page of a book.
Without index:
Search chapter page-by-page ❌
With index:
Look in index → Directly go to page ✔
Similarly, DBMS uses indexes to reduce disk accesses and find records quickly.

## Basic Components of Indexing

### Search Key
Attribute used for searching.
May be Primary Key, Candidate Key, or another attribute.
Example:
Student(Roll_No, Name)
Search Key = Roll_No

### . Data Reference (Pointer)
Stores the address of the actual record in disk blocks.
Roll_No = 101
     ↓
Disk Block Address

## Important Properties
- Indexing is optional.
- Used as a secondary access path.
- Improves SELECT and WHERE queries.
- Index file is always sorted.

## Types of Indexing

### Primary Key
When the data file is already sorted according to the search key, the index built on that ordering is called a Primary (Clustering) Index.
Example
| Roll_No | Name   |
| ------- | ------ |
| 101     | Aditya |
| 102     | Rahul  |
| 103     | Priya  |
Primary Index can be created on roll no

### Dense Index
Every search-key value has an index entry.
| Roll_No |
| ------- |
| 101     |
| 102     |
| 103     |

| Key | Pointer |
| --- | ------- |
| 101 | →       |
| 102 | →       |
| 103 | →       |

### Characteristics
✔ Faster searching
❌ More storage required

### Sparse Index
Index entries exist only for some search-key values.
Usually one index entry per block.
Example
Data Blocks:
Block1: 101,102,103
Block2: 104,105,106
Block3: 107,108,109
| Key | Block |
| --- | ----- |
| 101 | B1    |
| 104 | B2    |
| 107 | B3    |


### Characteristics
✔ Less storage
❌ Slightly slower than Dense Index


### Primary Index on Key Attribute

**Characteristics**
- Data sorted on Primary Key.
- Search key = Primary Key.
- Usually Sparse Index.

No. of Index Entries
=
No. of Data Blocks

### Primary Index of Non Key Attribute (Clustring Index)
**Characteristics**
No. of Index Entries
=
No. of Data Blocks
Example
Employee Table sorted by Department:
| Emp_ID | Department |
| ------ | ---------- |
| 1      | IT         |
| 2      | IT         |
| 3      | HR         |
| 4      | HR         |
index
| Department | Pointer |
| ---------- | ------- |
| IT         | →       |
| HR         | →       |

### Multi Level Index
If the index itself becomes very large:
Data File
     ↓
Huge Index File 
Searching the index becomes slow.
Solution
create indexes on indexes
Level 2 Index
      ↓
Level 1 Index
      ↓
Data File
This is called Multi-Level Indexing

### Secondary Level Index
Used when the data file is NOT sorted according to the search key
**Characteristics**
- Data file unsorted.
- Can be built on key or non-key attributes.
- Always Dense Index.
- One index entry per record.
No. of Index Entries
=
No. of Records
Example
Data file unsorted:
| Roll_No | Name   |
| ------- | ------ |
| 103     | Priya  |
| 101     | Aditya |
| 102     | Rahul  |
Secondary Index can be built on Roll_No.

## Advantages of Indexing
1.Fast Data Retreival
2.Reduced Disk i/o
3. Better Query Performance
## Limitations
1.Extra Storage Required -Need separate index files.
2.Slower INSERT -New index entries must be added.
3.Slower DELETE-Slower DELETE
4.Slower UPDATE-Index may need modification.