---
Title: DBS101 Flipped Class 6
categories: [DBS101, Flipped_Class6]
tags: [DBS101]
---

### Topic : Types of Non-Relational Databases
----

In our sixth flipped class, we explored non-relational databases, focusing on their advantages, disadvantages, and applications. Our class was divided into six expert groups, each focusing on a different kind of non-relational database. I turned into a part of Group 5, which centered on time-series databases. 



We began the class with a five-minute consultation, followed through 20 mins of discussions. Then, we spent 25 mins presenting to our home groups, and subsequently, we engaged in a fifteen-minute question and answer consultation. 



Our main aim was to deepen our knowledge of kinds of non-relational databases and their importance in contemporary facts management systems. We aimed to apprehend the advantages and drawbacks of various types of non-relational databases. 



Our tutor supplied us with lots of resources, Like websites: 

https://kx.com/products/kdb/

https://www.geeksforgeeks.org/types-of-nosql-databases/

https://redis.com/nosql/timeseries-databases/

https://www.pinecone.io/learn/vector-database/ 

Additionally, we were advised to consult the textbook “NoSQL for Mere Mortals” for a radical know-how of non-relational databases. 

---
#### Document based databases:

* Nonrelational database storing data in documents (JSON, BSON, or XML) instead of traditional tables.
* Documents mimic application data objects for seamless integration.
* Retrieval via index values for faster querying.

Collections:

* Groups of documents with similar content.
* Flexible schema allows for varied document structures.
* Not all documents need to conform to a specific schema within a collection.

Key Features:

* Flexible Schema: Documents do not require uniform structure.
* Fast Creation & Maintenance: Easy document creation with minimal upkeep.
* No Foreign Keys: Documents are independent, eliminating dynamic relationships.
* Open Formats: Utilizes XML, JSON, and others for document creation.

---
#### Key-Value based databases:

* Nonrelational database where data is stored in key-value pairs.
* Each element has a unique key for retrieval.
* Values can range from simple data types to complex objects.

Key Features:

* Simplicity: Basic structure with only two columns (key and value).
* Scalability: Can scale easily with growing data needs.
* Speed: Offers fast retrieval and storage capabilities.

---
#### Graph Databases

* Focus on relationships between elements, stored as nodes with connections called links or relationships.
* Simplifies identifying data relationships using links within the database.

Key Features:

* Easy Relationship Identification: Links between nodes make relationships clear.
* Real-time Query Results: Queries provide immediate, up-to-date information.
* Speed Based on Relationships: Performance depends on the number of connections among elements.
* Easy Data Updates: Adding nodes or edges is straightforward and doesn't require complex schema changes.

---
#### Vector Databases:

Vector databases index and store vector embeddings for rapid retrieval and similarity search. They support CRUD operations, metadata filtering, horizontal scaling, and serverless architectures.

Core Components:

* Efficiently processes large language models, generative AI, and semantic search applications.
* Relies on vector embeddings for semantic information crucial to AI understanding and memory.
* Offers optimized storage and querying for embeddings, addressing limitations of traditional databases with scalar-based indexing.

Key Features:

* Simplified Data Management: Handles storage, retrieval, and updating of vector data efficiently.
* Real-time Querying: Delivers immediate results for queries, supporting dynamic AI tasks.
* Scalability and Flexibility: Scales seamlessly with data volume and user demands, often employing serverless architectures.
* Enhanced Security and Access Control: Provides built-in security features and access controls for sensitive information.
* Ecosystem Integration: Easily integrates with other data processing tools and AI-related platforms for streamlined workflows.

---
#### Time-series Databases:

Time-series databases specialize in handling data points indexed or ordered in time sequence, making them suitable for storing and analyzing time-stamped data.

Core Components:

* Simplified Data Management: Efficiently manages storage, retrieval, and updating of time-series data points.
* Real-time Querying: Supports immediate retrieval of time-series data for dynamic analysis and monitoring.
* Scalability and Flexibility: Scales seamlessly with increasing data volume and user demands, often leveraging serverless architectures for elastic resource allocation.
* Enhanced Security and Access Control: Offers built-in security features and access controls to safeguard sensitive time-series data.
* Ecosystem Integration: Easily integrates with other data processing tools and platforms, enabling seamless workflows for time-series data analysis.

---
#### Column-Oriented Databases

* Non-relational databases storing data in columns rather than rows.
*Allows direct access to specific columns for analytics, minimizing memory usage.

Key Features:

* Scalability: Can handle large amounts of data efficiently.
* Compression: Data is compressed for storage optimization.
* Very Responsive: Designed for fast data retrieval and analysis.

---