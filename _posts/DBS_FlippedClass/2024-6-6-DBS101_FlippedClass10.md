---
Title: DBS101 Flipped Class 10
categories: [DBS101, Flipped_Class10]
tags: [DBS101]
---

### Topic : Transaction and Serializability

---
In our flipped class we learned about transactions in database which I will be sharing the knowledge I acquired from the flipped class. So, do go through my journal.

### What is a Transaction?
A transaction is a collection of operations that together form a single logical unit of work. This unit of work can access and potentially update various data items.
It ensures that either all the operations are completed successfully, or not at all.

A transaction is delimited by statements (or function calls)
of the form begin transaction and end transaction.
The transaction consists of all operations executed between
the begin transaction and end transaction.

For example, if you are performing a bank transfer:

1. 'begin tansaction'
2. Deduct amount from Acount A
3. Add amount to Account B
4. 'end transaction'

If any operation fails within this sequence, the entire transaction fails, ensuring data integrity and consistency.

#### Properties of Transaction:

Transaction follows this ACID properties.

![alt text](</image/ACID.png>)

#### A simple Transaction Model

Let's do this transaction in PostgreSQL for better understanding the transaction.

- I'm creating a database named 'test_transaction' and let's use this database.

![alt text](</image/Screenshot from 2024-06-06 07-34-18.png>)

- I have created a table 'account' and I have inserted the values inside the table.

![alt text](</image/Screenshot from 2024-06-06 07-36-07.png>)
