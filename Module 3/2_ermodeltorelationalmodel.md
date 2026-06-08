# ER Model → Relational Model 
## Introduction
ER Model and Relational Model are logical representations of real-world data.
Converting an ER Diagram into tables is called ER to Relational Mapping.
### Strong Entity
Rule:
Create a separate table for each strong entity.
Entity attributes → Columns.
Entity Primary Key → Table Primary Key.
Example:
Student(Roll_No, Name, Age)

PK: Roll_No

### Weak Entity
Rule:
Create a separate table.
Add Strong Entity's PK as FK.
PK = {FK + Partial Key}
Example:
Employee(Emp_ID, Name)
Dependent(Name, Age)

Becomes:

Employee(Emp_ID, Name)

Dependent(Emp_ID, Dep_Name, Age)

PK: (Emp_ID, Dep_Name)

FK: Emp_ID

### Single-Valued Attribute
Rule:
Directly becomes a column.
Example:
Student(Roll_No, Name, Age)

Name and Age become columns.

### Composite Attribute
Rule:
Break into simple attributes.
Ignore the composite attribute itself.
Example:
Address = {House_No, Street, City}

Becomes:

Customer(
    Cust_ID,
    House_No,
    Street,
    City
)

Do not store Address separately.

### Multivalued Attribute
Rule:
Create a new table.
Add entity PK as FK.
PK = {FK + Multivalued Attribute}
Example:

Employee has multiple dependent names.

Employee(Emp_ID, Name)

Create:

Dependent_Name(
    Emp_ID,
    DName
)

PK: (Emp_ID, DName)

FK: Emp_ID

### Derived Attribute
Rule:
Not stored in the table.
Calculated when needed.
Example:
Age ← derived from Date_of_Birth

Store DOB, not Age.

### Generalization
Method 1 (Most Common)

Create:

One table for Superclass
One table for each Subclass
Example
Account(Account_No, Balance)

Savings_Account(
    Account_No,
    Interest_Rate,
    Daily_Withdrawal_Limit
)

Current_Account(
    Account_No,
    Overdraft_Amount,
    Transaction_Charges
)
Method 2

Conditions:

Generalization must be Disjoint
Generalization must be Complete
Rule:
No table for Superclass.
Create only subclass tables.
Example
Savings_Account(
    Account_No,
    Balance,
    Interest_Rate,
    Daily_Withdrawal_Limit
)

Current_Account(
    Account_No,
    Balance,
    Overdraft_Amount,
    Transaction_Charges
)
Drawbacks
Data redundancy possible.
Cannot represent entities belonging only to superclass.
### Aggregation
Rule:
Create a table for the relationship.
Include:
PKs of participating entities
PKs of aggregated entities
Relationship attributes
Example
Employee ----- Works_On ----- Project
                     |
                  Manager

Table:

Works_On(
    Emp_ID,
    Project_ID,
    Manager_ID,
    Hours
)