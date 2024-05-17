---
Title: DBS101 Flipped Class 8
categories: [DBS101, Flipped_Class8]
tags: [DBS101]
---

### Topic : Indexing

---

In this flipped_class, firstly the students were divided into size of 4 students in each group, which formed 6 groups. This gorups were expert groups and got each topic form three topics to master the topic within 25 minutes. After the group discussion the 6 groups were then divided into 2 groups which were the quiz group.
After dividing into 2 groups we were given 25 minutes for discussion.

Then for 30 minutes the 2 groups had a quiz and whoever the group wins got to choose the prize which were chocolate and chewing gum.

During the quiz, both groups had a equal points and was difficult to decide the winner, so, in the end one person from each group played rock-papper-scissor game to choose the winner. Like that my group ended with a win and a chocolate(dairy) prize.

From this flipped class, the goals are to understand buffer trees, explain the indexing of spatial and temporal data, and implement bitmap indices.

#### Reference:

a. https://www.geeksforgeeks.org/bitmap-indexing-in-dbms/

b. https://www.javatpoint.com/dbms-b-plus-tree

c. https://www.youtube.com/watch?v=16TPK7nBSss

d. https://www.ibm.com/docs/en/informix-servers/12.10?topic=objects-spatiotemporal-search-indexing#:~:text=Before%20you%20start%20indexing%20spatiotemporal,the%20time%20series%20base%20table.

---

### Indexing of Spatial and Temporal Data

#### Introduction:

Indexing of spatial and temporal data enables efficient organization and retrieval of data based on geographical and time-based attributes.

#### Spatial Indexing:

Configuring spatial data in spatiotemporal search involves setting parameters for trajectory generation, such as frequency, duration, and bounding box size. This ensures accurate tracking of object movements over time, including stationary periods. Efficient storage management is crucial, requiring specification of storage spaces and extent sizes for subtrack objects like the table and geometry column.

#### Temporal Data Indexing:

Temporal data indexing focuses on configuring temporal aspects during indexing. This includes defining parameters for trajectory generation, stationary periods, and periods with no data. Storage space management is essential, requiring specification of storage spaces and extent sizes for subtrack objects like the table and geometry column.

---

### Bitmap Indices

#### Introduciton

Bitmap indexing is a data indexing technique used in DBMS to enhance the performance of read-only queries involving large datasets. It involves creating a data structure called a bitmap index.

Structure: In a bitmap index, each distinct value in a column is assigned a bit vector representing its presence or absence in each row of the table. Set bits indicate presence, and cleared bits indicate absence.

#### Features:

- Space Efficiency: Bitmap indexes are compact, making them efficient for large datasets with many attributes.
- Fast Query Processing: Enables quick set-based operations like AND, OR, and NOT, reducing query execution time.
- Low Maintenance Overhead: Requires minimal updates and maintenance, suitable for frequently updated datasets.
- Flexibility: Supports both numerical and categorical data types, and can index text data using techniques like TF-IDF.
- Reduced I/O Overhead: Avoids costly I/O operations by compressing data representation, improving query performance.

#### Usage Example:

Bitmap indexing is employed when columns have low cardinality but are frequently queried, providing efficient retrieval of data.

---

### Buffer Tree
Buffer Trees are data structures designed to manage and process large volumes of data efficiently.

They are particularly effective in scenarios where data is too large to fit in main memory and needs to be stored and managed on disk.

#### Structure
* Root Node:
Contains a buffer to hold incoming operations.
* Internal Nodes:
Each internal node has a buffer and child pointers.
Buffers in internal nodes accumulate operations which are propagated to child nodes periodically.
* Leaf Nodes:
Leaf nodes store the actual data.
Operations are eventually propagated to the leaf nodes and executed there.


#### Operations
* Insertion:

Data or operations are inserted into the buffer at the root.
When the root buffer is full, operations are flushed down to child nodes.
This process continues recursively, ensuring buffers at each level manage overflow.

* Deletion:

Similar to insertion, deletions are initially stored in buffers.
They are propagated to the appropriate leaf nodes where actual deletions occur.

* Search:

Searches traverse the tree from root to leaf, taking into account operations stored in buffers.
This ensures that searches reflect the most up-to-date state of the tree.

#### Advantages
* Reduced I/O Operations:
By batching operations in buffers, buffer trees minimize the number of disk accesses.
* Efficiency in Large Datasets:
Designed to handle datasets that exceed main memory capacity efficiently.
* Amortized Performance:
Offers better average performance over a series of operations compared to traditional data structures.

