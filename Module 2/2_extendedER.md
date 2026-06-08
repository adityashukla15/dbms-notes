# Extended ER FEATURES

The Extended Entity-Relationship (EER) Model is an enhancement of the basic ER model. It adds extra concepts to represent complex real-world situations more accurately.

## Specialisation

Specialization is the process of dividing a higher-level entity (superclass) into lower-level entities (subclasses) based on specific characteristics.
In ER model, we may require to subgroup an entity set into other entity sets that are distinct in some way with other entity sets.
It is a Top-Down approach.
Example:
          Employee
              |
      ----------------
      |              |
   Teacher       Accountant

Employee = Superclass
Teacher, Accountant = Subclasses

All Teachers and Accountants are Employees.
We have “is-a” relationship between superclass and subclass.
 Depicted by triangle component.


## Generalisation

It combines similar lower-level entities into a higher-level entity
Example:
   Car          Bike
      \          /
       \        /
        Vehicle
Car and Bike are generalized into Vehicle.
It is a Bottom-up approach.

### Attribute Inheritance
Both Specialisation and Generalisation, has attribute inheritance.
 The attributes of higher level entity sets are inherited by lower level entity sets.
. E.g., Customer & Employee inherit the attributes of Person.

### Participation Inheritance
 If a parent entity set participates in a relationship then its child entity sets will also participate in that relationship.

## Aggregation
How to show relationships among relationships? - Aggregation is the technique.
Abstraction is applied to treat relationships as higher-level entities. We can call it abstract entity.
Avoid redundancy by aggregating relationship as an entity set itself
Aggregation treats a relationship as a higher-level entity so that it can participate in another relationship.
EG
Employee ---- Works_On ---- Project
                    |
                Monitored_By
                    |
                Manager

        Here, "Works_On" can be treated as a single entity and related to Manager.
