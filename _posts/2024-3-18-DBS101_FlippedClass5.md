---
Title: DBS101 Flipped Class 5
categories: [DBS101, Flipped_Class5]
tags: [DBS101]
---

### Topic : Normalization in DBMS
----

In our fifth flipped class, we learned about Normal Forms, which help make databases better. We made groups of 6-7 people each. We had four groups: Group 1 studied about First and Second Normal Forms, Group 2 studied about BCNF, Group 3 studied about Third Normal Form, and Group 4 studied about Fourth Normal Form. I got in group 1 which I will cover as follows.

We started with a 10-minute talk, then had 30-minutes of group discussion. Finally, we spent 20 minutes showing what we learned to the whole class.

Our goals from this flipped classroom were to use Normal Forms to make databases better and to understand why we need to reduce databases to these forms. 

Our tutor provided us with resources like websites link and youtube link:

https://www.studytonight.com/dbms/database-normalization.php

https://www.youtube.com/watch?v=IY5kYfCCRY0

In our fifth flipped class, we learned about Normal Forms, which help make databases better. We made groups of 6-7 people each. We had four groups: Group 1 studied about First and Second Normal Forms, Group 2 studied about BCNF, Group 3 studied about Third Normal Form, and Group 4 studied about Fourth Normal Form. I got in group 1 which I will cover as follows.

We started with a 10-minute talk, then had 30-minutes of group discussion. Finally, we spent 20 minutes showing what we learned to the whole class.

Our goals from this flipped classroom were to use Normal Forms to make databases better and to understand why we need to reduce databases to these forms. 

Our tutor provided us with resources like websites link 
Plus, we were told to refer to Textbooks/eBook called “Database Systems Fundamentals,” especially Chapter 7, pages 303-351. These helped us understand Normal Forms better.

---
Firstly, before going with Normal Forms, it is better to know that Normalization in DBMS is a technique which can organize the data in the database tables so that:

There is less repetition of data,

A large set of data is structured into a bunch of smaller tables,


and the tables have a proper relationship between them.


DBMS Normalization is a systematic approach to decompose (break down) tables to eliminate data redundancy(repetition) and undesirable characteristics like Insertion anomaly in DBMS, Update anomaly in DBMS, and Delete anomaly in DBMS.

#### Types of DBMS Normal forms

Normalization rules are divided into the following normal forms:

1. First Normal Form
2. Second Normal Form
3. Third Normal Form
4. BCNF
5. Fourth Normal Form
6. Fifth Normal Form

---
####   First Normal Form (1NF)

For a table to be in the First Normal Form, it should follow the following 4 rules:

1. It should only have single(atomic) valued attributes/columns.
2. Values stored in a column should be of the same domain.
3. All the columns in a table should have unique names.
4. And the order in which data is stored should not matter.

Let’s look at an example. Imagine having a table with employee information and their skills. 

![alt text](<../image/Screenshot from 2024-03-25 20-31-31.png>)

This table has a problem because the “emp_skills” column has multiple skills listed in one cell. According to 1NF, each cell should have only one piece of data.

To fix this, we can: 

1. Make a new table for employee skills. This way, each skill is in its own row, linked to the employee by their ID.
2. Add more rows for each skill an employee has. This means if an employee has two skills, they will have two rows, one for each skill.

Here’s how the table would look like after fixing:

Employee Table:

![alt text](<../image/Screenshot from 2024-03-25 20-38-05.png>)

Employee Skills Table:

![alt text](<../image/Screenshot from 2024-03-25 20-39-40.png>)

By doing this, we make sure our database follows 1NF, making it easier to work with and update.

---
#### Second Normal Form (2NF)

For a table to be in the Second Normal Form,

1. It should be in the First Normal form.
2. And, it should not have Partial Dependency.

Partial dependency happens when a non-primary-key attribute depends on only part of the primary key.

Let’s take an example to understand this. If we have two tables Students and Subjects, to store student information and information related to subjects.

![alt text](<../image/Screenshot from 2024-03-25 20-56-33.png>)

![alt text](<../image/Screenshot from 2024-03-25 20-56-51.png>)

The primary key is a combination of student_id and subject_id. However, the teacher_name, which is not part of the primary key, depends only on the subject_id, not the primary key. This is a partial dependency.

To fix this and bring the Score table into 2NF, we need to remove this partial dependency. One way to do this is by moving the teacher_name to the Subjects table, where it can be fully dependent on the subject_id, which is the primary key of the Subjects table. This way, the Score table no longer has partial dependencies, and it meets the requirements of 2NF

Before removing partial dependency.

Score Table:

![alt text](<../image/Screenshot from 2024-03-25 21-09-45.png>)

After removing partial dependency:

Updated Subject Table:

![alt text](<../image/Screenshot from 2024-03-25 21-11-08.png>)

Updated Score Table:

![alt text](<../image/Screenshot from 2024-03-25 21-11-50.png>)

---
#### Third Normal Form (3NF)

A table is said to be in the Third Normal Form when,

1. It satisfies the First Normal Form and the Second Normal form.
2. And, it doesn't have Transitive Dependency.

Transitive dependency occurs when a non-primary-key attribute depends on another non-primary-key attribute, which in turn depends on the primary key. This can lead to issues with data integrity and updates.

Let's take an example. We had the Score table in the Second Normal Form above. If we have to store some extra information in it, like,

1. exam_type
2. total_marks

The primary key is a combination of student_id and subject_id. The exam_type column depends on both student_id and subject_id, and the total_marks column depends on the exam_type column, which is not part of the primary key. This creates a transitive dependency.

Score Table:

![alt text](<../image/Screenshot from 2024-03-25 21-20-05.png>)

To resolve this and bring the Score table into 3NF, we can create a separate table for ExamType, which includes the exam_type, total_marks, and any other related information. Then, we can use the exam_type_id from the ExamType table in the Score table, eliminating the transitive dependency.

New ExamType Table:

![alt text](<../image/Screenshot from 2024-03-25 21-22-26.png>)

---
#### Boyce-Codd Normal Form (BCNF)

* The Boyce and Codd Normal Form is a higher version of the Third Normal Form.
* This form deals with a certain type of anomaly that is not handled by 3NF.
* A 3NF table that does not have multiple overlapping candidate keys is said to be in BCNF.
* For a table to be in BCNF, the following conditions must be satisfied:
  * R must be in the 3rd Normal Form
  * and, for each functional dependency ( X → Y ), X should be a Super Key.

---
####  Fourth Normal Form (4NF)

A table is said to be in the Fourth Normal Form when,

1. It is in the Boyce-Codd Normal Form.
2. And, it doesn't have Multi-Valued Dependency.

---