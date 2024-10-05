# PostgreSQL vs MongoDB: Choosing the Right Database

When building or scaling your application, choosing the right database is crucial. Both **PostgreSQL** and **MongoDB** are popular databases with their own unique strengths. In this guide, we'll compare the two databases, outlining when to choose one over the other based on your project's specific needs.

---

## I. Introduction

I use mongoDB a lot after using postgreSQL a while ago. I'm really confused about having to choose between mongooDB or mySQL, why not mongoDB. I explained MongoDB's advantages, such as being JSON-based and having fast read/write operations. "But can't PostgreSQL do the same?", "If you remove PostgreSQL's relational aspect, how is it different from MongoDB?" That question left me stumped.

After further study and experience, I've realized that **both databases can meet the basic needs** of most projects, but each excels in specific use cases. Choosing the right one can save time, improve performance, and reduce costs. 

---

## II. Key Factors to Consider Before Choosing a Database

1. **Project Requirements**: Understand the specific needs of your project.
2. **Cost**: Consider the implementation, operational, and scaling costs.
3. **Team Expertise**: Evaluate the team's strengths and experience with the databases.
4. **Community Support**: Consider the size of the community and available resources.
5. **Integration**: Assess how well the database integrates with your existing tech stack.

---

## III. Detailed Comparison

### 1. **Read Performance**

- **PostgreSQL**: It performs well with reads thanks to its **Multi-Version Concurrency Control (MVCC)**. MVCC allows simultaneous reading and writing by creating new versions of records rather than directly updating them. PostgreSQL uses a process called **VACUUM** to clean up old, obsolete records. This enables **high concurrency** and consistent reads, making PostgreSQL a strong choice for read-heavy workloads.

- **MongoDB**: MongoDB also performs well for reading, especially with **unstructured data**. Its document-based model allows for flexible querying and schema-less storage, making it ideal for fast reads with complex, nested documents.

### 2. **Write Performance**

- **PostgreSQL**: While MVCC enhances read performance, it can slow down writes due to the overhead of creating new records instead of updating them directly. PostgreSQL’s write performance might be slower compared to MongoDB in high QPS (queries per second) scenarios.

- **MongoDB**: MongoDB’s write operations are highly optimized for **high-throughput scenarios**. If the new data size matches or is smaller than the previous size, MongoDB updates it in-place, reducing the overhead. MongoDB supports **up to 2000-3000 requests/second** with high write efficiency.

### 3. **Storage Engines**

- **MongoDB**: 
  - MongoDB primarily uses **WiredTiger** (default since version 3.2), which supports:
    - Data and index compression.
    - Document-level concurrency control.
    - Both **journal** and **unjournaled** storage for data durability.
  - **In-Memory Storage**: Available in the enterprise edition, designed for ultra-low-latency workloads.

- **PostgreSQL**:
  - Uses the **Heap Storage Engine** by default, with support for **MVCC** and **Write-Ahead Logging (WAL)** for data durability and recovery.
  - PostgreSQL’s WAL logs all database actions before they are committed, providing robust support for **ACID compliance** and crash recovery.
  - Extensions like **TOAST**, **pg_trgm**, and **PostGIS** provide additional storage options, and third-party extensions such as **TimescaleDB** and **Citus** offer more specialized solutions.

### 4. **Indexing**

- **PostgreSQL**: Supports several index types, including **B-tree**, **hash**, **GiST**, **SP-GiST**, **GIN**, **BRIN**, **partial indexes**, and **expression indexes**. This makes PostgreSQL highly flexible for different indexing strategies and query optimization.

- **MongoDB**: Offers various index types, such as **single-field indexes**, **compound indexes**, **multikey indexes**, **geospatial indexes**, **hashed indexes**, and **TTL indexes**. MongoDB’s indexing capabilities are extensive and tailored for its document model.

### 5. **Joins**

- **PostgreSQL**:
  - Supports efficient join algorithms, including **nested loop**, **hash join**, and **merge join**.
  - Joins are optimized based on data statistics and indexing strategies.
  - It can handle complex multi-table joins with ease and supports subqueries.

- **MongoDB**:
  - Introduced **$lookup** (since version 3.2), which is MongoDB's equivalent to a **LEFT OUTER JOIN**.
  - While MongoDB can now handle basic joins, it encourages **denormalization** and **embedded documents** to reduce the need for joins.
  - Joins in MongoDB are limited compared to SQL joins and often need to be handled at the application level.

### 6. **Scalability**

- **MongoDB**:
  - Built with scalability in mind, MongoDB provides **sharding** as a built-in feature for horizontal scaling across multiple servers.
  - MongoDB’s replica sets allow easy scaling for high availability and redundancy.

- **PostgreSQL**:
  - While not as sharding-friendly as MongoDB, PostgreSQL supports extensions like **Citus** for distributed scaling.
  - **PgPool-II** and **Patroni** can help manage scaling, but they are not as natively integrated as MongoDB’s sharding.

### 7. **JSON Support**

- **MongoDB**: As a **document-based database**, MongoDB natively supports JSON-like objects, making it highly flexible for schema-less data storage.

- **PostgreSQL**: While traditionally a relational database, PostgreSQL supports **JSON** and **JSONB** data types, allowing for powerful querying and indexing of JSON data. It offers the best of both relational and non-relational worlds.

### 8. **Full-text Search**

- **PostgreSQL**:
  - Supports full-text search with specialized indexes like **GIN** and **GiST**.
  - Extensions like **pg_trgm** enable fast, fuzzy text search.

- **MongoDB**: Full-text search is integrated natively, and MongoDB Atlas offers a powerful **Atlas Search** engine built on **Apache Lucene**.

### 9. **ACID Compliance**

- **PostgreSQL**: Built from the ground up to support **ACID** properties, PostgreSQL excels at handling complex transactions with guaranteed consistency and durability.

- **MongoDB**: Introduced **ACID** support in version 4.0. However, transactions in MongoDB come with some limitations (e.g., duration and size limits), and do not support **savepoints** as PostgreSQL does.

### 10. **Community and Support**

- **PostgreSQL**:
  - Boasts a large, mature community with extensive documentation.
  - Known for its stability and long-standing presence in the database world.

- **MongoDB**:
  - A rapidly growing community, especially among NoSQL developers.
  - Strong support from the MongoDB company and a growing ecosystem around MongoDB Atlas.

---

## IV. Conclusion

### 1. When to Choose **MongoDB**:
- Your data model is **constantly evolving** or is unstructured.
- You need **high write throughput** and can handle QPS of 2000-3000 requests per second.
- You’re working with **real-time analytics**, IoT, or scenarios involving large amounts of daily data.
- You need **easy horizontal scaling** with built-in sharding and replica sets.
- Your application requires **geospatial queries** or complex **nested document structures**.
- You have a **small team** and want fast development cycles.

### 2. When to Choose **PostgreSQL**:
- Data **reliability and consistency** are a priority, especially in mission-critical applications.
- Your data model is **structured** and involves many **complex queries**.
- You need **ACID-compliant transactions** and **complex joins**.
- Your application involves **complex relationships** and multi-table operations (joins).
- Your project demands **regulatory compliance**, such as in finance or healthcare.
- You’re dealing with **large-scale data analytics** and require features like **full-text search** or **geospatial data**.

---

### Final Thoughts:

Both **MongoDB** and **PostgreSQL** are powerful databases, each with their own strengths. **MongoDB** excels in flexibility, speed, and scalability for unstructured or semi-structured data. **PostgreSQL**, on the other hand, shines in consistency, ACID compliance, and handling complex queries and relationships.

Ultimately, the right choice depends on your project’s requirements, your team's expertise, and your performance needs.

---
📝 **Created by ducanhduocdochu**
