# RDBMS Challenge

I've seen a challenge for implementing a RDBMS that supports CRUD operations and is interacted with a language similar to SQL. An app is meant to be made that demos the RDBMs implemented.

A **database is just a collection of related data and this data is known facts that can be recorded and have a meaning** (Rames et al, 2011). Since a database is just a collection of facts, there is no constraint of where these facts can be stored. Looks like any approach would be valid. 

## What is a relational database

A RDMS is a database management system that **uses the relational model**. In the relational model, the *database is represented as a collection of relations* (Rames et al, 2011). The data in a relation can be thought of as "flat" since each of the records in the database has a linear or flat structure (Rames et al, 2011). These *relations are made up of rows (tuples)*, where each row is a linear structure of related data. All the data in a row is related to each other and can be thought of as one entity in the real world. *The relation has column names (attributes) that help to interpret the data in each row*. *The range of possible values that can exist in each column is called the domain* (Rames et al, 2011).

Implementing the concept of a tuple, attribute, relation and domains will be crucial as this is what makes our database relational.

*Domains are a set of the possible values for an attribute* of a tuple. These sets can be described with existing data types e.g. integers or can be formats made up of existing data types e.g. a type for a phone_numbers domain could be defined as (ddd)(ddddddddd) where d is a numeric digit and first 3 digits are an area code. These domains are given names (Rames et al, 2011)

This implementation will not implement formats for domains.

We can know describe a relation schema with this information.
```
R(A1, A2, ... , An)
```
**A relation schema R is made up of attributes A1, A2, ... , An where each attribute is a named role of a domain D in the relation schema. The domain of an attribute can be denoted as dom(Ai). A relation r(R) or a relation schema R is the set of n-tuples where each tuple t is an ordered list of n values t = <v1, v2, ... , vn> where each value vi, 1 <= i <= n, is of the domain dom(Ai) or a special NULL value** (Rames et al, 2011).

The information above gives some important hints:

1. When working with a relation we expect a set of tuples
2. Each tuple is an ordered list of n values
3. Each value vi belongs to the domain Ai or is NULL

**A relation schema can also be thought of as a predicate** where each tuple in the relation can be interpreted as values that satisfy the predicate (Rames et al, 2011). This information will be useful when implementing updating a relation or inserting a new tuple into relation.

A relational database is made up of multiple relations and the tuples in these relations can be related to each other (Rames et all, 2011)

## What happens when someone enters a SQL Query

Below is what I think happens:

1. A compiler checks if there are any token error in the SQL statement i.e. invalid token
2. A compiler checks for any syntax errors by constructing parse tree
3. A compiler checks for any semantic errors in the parse tree (check if columns exist, type issues e.t.c)
4. A query tree is constructed from the parse tree
5. Database operations and order of operations is gotten
6. Operations are ran
7. Results are returned

## References

Rames Elmasri and Shamkant B. Navathe, Fundamentals of Database Systems Sixth Edition, 2011