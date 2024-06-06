---
Title: DBS101 Flipped Class 12
categories: [DBS101, Flipped_Class12]
tags: [DBS101]
---

### Topic : Recovery Algorithm

---

### Introduction

In this journal I will take you through recovery algorithm which I learned in my flipped class.

Recovery systems in Database Management Systems are very important because they ensure the integrity and avialability of data despite various potential disruptions which can include system failures, transaction failures, human errors, security breaches, hardware upgrades, natural disasters, compliance regulations, and data curruption.
But don't worry, I will teach you how to recover a database from these disruptions. So, go through my journal to learn this.

### What is a Recovery Algorithm?

A recovery algorithm is a set of procedures and techniques designed to restore a database to a correct state after a failure. Think of it as a safety net for your data. This way, important data is protected and remains accurate, no matter what happens.

![alt text](/image/recovery_algo.png)

There are several types of recovery algorithms used in Database Management Systems, in this journal I will take you through Log-Based Recovery, ARIES(Algorithm for Recovery and Isolation Exploiting Semantics),and Shadow Paging.

### 1. Log-Based Recovery (The most common technique)

In this technique any operation which is performed on the database is recorded on the log. This log helps in undoing or redoing transactions as needed to recover the database.

#### Types of Log Records:

- Update Record: <Ti, Xj, V1, V2> where Ti is the transaction ID, Xj is the data item, V1 is the old value, and V2 is the new value.
- Start Record: <Ti start> indicating the beginning of transaction Ti.
- Commit Record: <Ti commit> indicating the successful completion of transaction Ti.
- Abort Record: <Ti abort> indicating the transaction Ti was aborted.

#### Modification Techniques:

- Deferred Modification: Changes are not written to the database until the transaction commits.
- Immediate Modification: Changes are written to the database as they occur, but logged first.

#### Recovery Process

- Undo (Ti): If a transaction needs to be undone (reversed), the system restores the old values using the log records. This process is necessary if a transaction was not completed before a failure.
- Redo (Ti): If a transaction needs to be redone (re-applied), the system uses the log records to set data items to their new values. This is needed if the changes were committed but not yet fully written to the database.

![alt text](/image/Undo-redo.png)

### 2. ARIES(Algorithm for Recovery and Isolation Exploiting Semantics)

These are the thress passes of ARIES recovery.

![alt text](</image/Pasted image 5.png>)

#### Key point:

- Write-Ahead Logging (WAL): Before any change is made to the database, its details are first recorded in a log. This log is then written to permanent storage. This ensures that even if the system crashes before the change is applied to the database, the log provides a record of what should have happened.
- Repeating History During Redo: After a crash, ARIES replays the actions that occurred before the crash to bring the database back to its pre-crash state. Then, it undoes any transactions that were still ongoing at the time of the crash.
- Logging Changes During Undo: While undoing transactions, any changes made to the database are also logged. This prevents these actions from being repeated if the system crashes again during the recovery process.

#### Checkpoints

To avoid re-scanning the log-file during the analysis phase, they save the state of the Dirty Page Table(DPT) and Transaction Table(TT) which speed up the recovery. There are two types of checkpoints: traditional, which lock the entire database, and fuzzy, which allow transactions to continue while the checkpoint is being prepared.

### 3. Shadow Paging

In this recovery technique, database is considered as made up of fixed size of logical units of storage which are referred as pages. Pages are mapped into physical blocks of storage, with help of the page table which allow one entry for each logical page of database.

![alt text](/image/shadow-paging.png)

To understand concept, consider above figure. In this 2 write operations are performed on page 3 and 5. Before start of write operation on page 3, current page table points to old page 3. When write operation starts following steps are performed :

1. Firstly, search start for available free block in disk blocks.
2. After finding free block, it copies page 3 to free block which is represented by Page 3 (New).
3. Now current page table points to Page 3 (New) on disk but shadow page table points to old page 3 because it is not modified.
4. The changes are now propagated to Page 3 (New) which is pointed by current page table.
