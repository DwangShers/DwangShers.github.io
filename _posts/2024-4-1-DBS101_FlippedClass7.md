---
Title: DBS101 Flipped Class 7
categories: [DBS101, Flipped_Class7]
tags: [DBS101]
---

### Topic : Tasks on Storage and buffer management
----
In our flipped class 7, we are told to make a summary on what we have done for practical 7 and what we have learned from it.

In our practical 7 we had to write a report in which there were three tasks and exercise.

---
#### What is Buffer Management in DBMS:
A database buffer is a section in the main memory that is used for the temporary storage of data blocks while moving form one location to another. 

We can lessen the number of disk accesses by maintaining as many blocks of data as possible (also known as database buffer) in the main memory. Therefore, when the user wishes to access the data, the user can do so immediately from the main memory. 

Also a buffer manager in DBMS is in charge of allocating buffer space in the main memory so that the temporary data can be stored there.

Referance: 
https://www.scaler.com/topics/buffer-management-in-dbms/

---
#### Raid Configuration
RAID (Redundant Array of Inexpensive Disks) is a data storage structure that allows a system administrator/designer/builder/user to combine two or more physical storage devices (HDDs, SSDs, or both) into a logical unit (an array) that is seen by the attached system as a single drive.

There are three basic RAID elements:

1. Striping (RAID 0) writes some data to one drive and some data to another, minimizing read and write access times and improving I/O performance.
2. Mirroring (RAID 1) replicates data on two drives, preventing loss of data in the event of a drive failure.
3. Parity (RAID 5 & 6) provides fault tolerance by examining the data on two drives and storing the results on a third. When a failed drive is replaced, the lost data is rebuilt from the remaining drives.
It is possible to configure these RAID levels into combination levels — called RAID 10, 50 and 60.

The RAID controller handles the combining of drives into these different configurations to maximize performance, capacity, redundancy (safety) and cost to suit the user needs.

Reference:
https://www.microsemi.com/product-directory/raid-controllers/4047-raid-levels

---
#### Buffer pools
A buffer pool is an area of main memory that has been allocated by the database manager for the purpose of caching table and index data as it is read from disk.

---
#### Exercise:
How to build a relational database from scratch?

Through my research, I found that making a relational database from scratch involves several steps:

1. Define the purpose and scope of the database.
2. Design the database schema.
3. Choose a database management system.
4. Create the database and tables.
5. Define the relationship between tables.
6. Populate the tables with data.
7. Create indexes.
8. Test the database.

Each of these procedures play a vital role in the development of a robust, efficient, and secure database system. They collectively ensure that the database is well-designed, optimized for performance, and capable of supporting the intended operations and data management needs of the application or organization

List of data structures used:

1. Linkedlist/Array/Queue, these are naturally a list of data and will be used to deal with mre than one data.
2. Stack. This is the basis of the function calls. When A function calls B function, the return address of A and local variables of B will be pushed into the system stack.
3. HashTable. Is a data structure in which the address/index value of the data element is generated from a hash function.
4. Tree. Tree is very important data structure to represent things with a hierarchical structure. Trees are also used for indexed data collections since it made search easier.
5. Set. The list of data, but without duplication. Internally, it's pretty much a HashTable or Search Tree.
6. Graph. A graph data structure is a collection of nodes that have data and are connected to other nodes.

---