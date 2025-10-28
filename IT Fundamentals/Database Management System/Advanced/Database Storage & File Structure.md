## **Types of Storage**

### # **Primary Storage**

- **Main Memory / RAM**
- Volatile memory used during **active processing**.
- Holds **buffer pools**, **caches**, **temporary computation results**, and **intermediate query data**.

- **Analogy:**
- *Think of it as a chef’s workstation. Ingredients (data) are brought here temporarily while preparing a dish (query). Once cooking is done, the kitchen (RAM) is cleaned up.*

### # **Secondary Storage**

- **Disk Storage**
- Non-volatile, long-term storage like **HDDs, SSDs**.
- Stores database **files, indexes, logs, backups**.
- Most DBMS activity interacts with this layer.

- **Analogy:**
- *This is the pantry or cold storage in a restaurant—holds ingredients (data) persistently until needed.*

### # **Tertiary Storage**

- **Offline / Archival**
- Used for **rarely accessed data** (e.g., backups, historical logs).
- Examples: **Magnetic tapes, cloud cold storage**.

- **Analogy:**
- *Think of it as a warehouse offsite where rarely used supplies are stored and accessed only during audits or emergencies.*
## **File Structures**

### # **Data Files**

- Store the **actual user data (tables, rows)**.
- Usually organized in **pages (blocks)**—the basic unit of storage (typically 4KB to 16KB).
- Uses **heap** (unordered), **clustered**, or **sequential** structures.

- **Analogy:**
- *A file cabinet with folders (tables) and papers (rows). Each drawer (block) can hold a certain number of papers.*

### # **Index Files**

- Contain **search structures** (like B-Trees or Hash tables).
- Used to **speed up data retrieval**.
- Not actual data but pointers to data locations.

- **Analogy:**
- *The index of a book—it doesn’t hold the content, but tells you where to find a topic quickly.*

### # **Log Files**

- Store every transaction change **before it is committed** to data files.
- Critical for **crash recovery**.
- Used by recovery mechanisms to replay or rollback transactions.

- **Analogy:**
- *A flight data recorder (black box) in an airplane—captures everything that happens so you can replay it in case of failure.*

### # **Temporary Files**

- Store intermediate results during **query execution, sorting, joining**.
- Typically **deleted** once the session ends or the query is complete.

- **Analogy:**
- *A whiteboard in a planning session—used to jot down temporary ideas and calculations, wiped clean after the meeting.*

### # **Configuration Files**

- Contain **metadata**, schema definitions, user privileges, etc.
- Defines how the DBMS should behave at runtime.

- **Analogy:**
- *Like the instruction manual and user permissions chart for a building—defines who can do what and how systems should work.*

## **Organization**

### # **Pages / Blocks**

- Fundamental unit of data read/write on disk.
- Grouped into **extents**, which are further grouped into **segments**.

- **Analogy:**
- *Like loading a whole page of a book into memory instead of a single word—it’s faster and more efficient.*

### # **Tuple Slot Directory**

- In each page, data is stored in **slots**.
- A slot directory maintains pointers to each record (row) inside a page.
- Supports **variable-length rows** and fast lookups.

- **Analogy:**
- *Imagine a theater where tickets (pointers) point to actual seats (data). Even if people move, the ticket system keeps track of where they are.*

## **Access Methods**

### # **Sequential Access**

- Reads data in the order it appears on disk.
- Efficient for **full table scans**.

- **Analogy:**
- *Reading a novel page by page.*

### # **Random Access**

- Jumps to specific locations using indexes or pointers.
- Efficient for **lookups and range queries**.

- **Analogy:**
- *Using Ctrl+F in a document to find a specific word instead of reading line by line.*

### **Buffer Management**

## # **Buffer Manager**

- Manages pages fetched from disk into RAM.
- Uses strategies like **LRU (Least Recently Used)** for cache eviction.

- **Analogy:**
- *A kitchen prep table (buffer pool) that only holds a limited number of ingredients at a time. Least used ones are sent back to the pantry to make room*

## **Storage Formats**

### # **Row-Oriented Storage**

- Stores all fields of a record together.
- Optimized for **OLTP (Online Transaction Processing)**.

- **Analogy:**
- *A grocery bag with all items for one meal in one bag.*

### # **Column-Oriented Storage**

- Stores all values of a column together.
- Optimized for **OLAP (Analytical Processing)** and compression.

- **Analogy:**
- *A warehouse where all the rice is in one section, all the sugar in another—perfect for bulk analysis.*

## **File Organization Types**

### # **Heap File Organization**

- Unordered records.
- Fast inserts, slow search.

- **Analogy:**
- *A pile of papers on a desk—easy to throw in, hard to find.*

### # **Sequential File Organization**

- Sorted based on one field.
- Efficient for range queries.

- **Analogy:**
- *A sorted filing cabinet. Searching is faster but insertion requires shuffling.*

### # **Hashed File Organization**

- Uses hash function to determine record placement.
- Excellent for equality searches.

- **Analogy:**
- *Mail sorted into pigeonholes based on the recipient’s name hash.*

## **RAID**

- RAID is a **data storage virtualization technology** that combines **multiple physical drives** into one **logical unit** to:

- Improve **data redundancy** (fault tolerance).
- Enhance **I/O performance**.
- Support **high-availability** database environments.

### # **RAID 0**

- **Striping (No Redundancy)**
- Data is **split across disks**.
- **No fault tolerance**. One disk fails, all data is lost.
- **High performance** for reads/writes.
- **Use Case in DBMS:**
    - Rarely used in production.
    - May be used in **read-only temp tables or non-critical test systems**.

- **Analogy:**
- *Like splitting a book into chapters and giving each chapter to a friend to read in parallel. Fast, but if one friend loses their part, the story is incomplete.*

### # **RAID 1**

- **Mirroring**
- Data is **duplicated** on two disks.
- **High fault tolerance**, minimal performance loss.
- Slower writes (due to duplication), faster reads.
- **Use Case in DBMS:**
    - Critical metadata, control files, and log files.
    - **Ideal for write-heavy systems with high availability needs.**

- **Analogy:**
- *Like writing every page of a book in two notebooks. If one is lost, you still have a copy.*

### # **RAID 5**

- **Block-Level Striping + Parity**
- Requires at least **3 disks**.
- Data + parity (error correction info) distributed.
- **Good read performance**, moderate write performance.
- Can survive **1 disk failure**.
- **Use Case in DBMS:**
    - Suitable for **data files** with heavy read, moderate write loads.
    - Used in **OLAP and data warehousing** environments.

- **Analogy:**
- *Like spreading a document across 3 friends, but adding a code that lets you recover one lost part if one friend disappears.*

### # **RAID 6**

- **Striping + Double Parity**
- Like RAID 5, but can survive **2 simultaneous disk failures**.
- **More robust**, slightly slower writes than RAID 5.
- **Use Case in DBMS:**
    - Critical for **large-scale data warehousing** or **archival systems**.
    - Good for environments where **data loss is unacceptable**.

- **Analogy:**
- *Like RAID 5 but with two backup friends instead of one—safer, slower.*

### # **RAID 10 (RAID 1+0)**

- **Mirroring + Striping**
- Requires at least 4 disks.
- **High performance and high redundancy**.
- Stripe data across mirrored pairs.
- Survives multiple failures if not on same mirror pair.
- **Use Case in DBMS:**
    - **OLTP databases**, transaction logs, high-performance production systems.
    - Ideal for **write-intensive** workloads.

- **Analogy:**
- *A mirrored fleet of racecars. If one crashes, its mirror takes over without slowing the race.*
