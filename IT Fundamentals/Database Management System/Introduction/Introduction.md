## **Introduction**

- A Database Management System (DBMS) is a Software system designed to handle, store, retrieve, and work with data in databases.
- First Introduced in 1960’s.
- Included **Charles Bachman’s Integrated Data Store (IDS)** and IBM’s Information Management System (IMS).
- Database were organized into Tree-like Structure using Hierarchical and Network Model.
- RDBMS was popularized by Edger F. Codd in the 1970’s.

## **Key Difference Between File System and DBMS**

| **Feature** | **File System** | **DBMS** |
| --- | --- | --- |
| Data Redundancy | High | Low |
| Data Consistency | Difficult to enforce | Ensured using constraints |
| Concurrency Control | Not supported | Supported with locking mechanisms |
| Security | OS-level file permissions | Fine-grained access control |
| Backup and Recovery | Manual processes | Automated and robust tools available |
| Data Relationships | Hard-coded in application logic | Defined using foreign keys |

## **Pro’s & Con’s of DBMS**

### **# Pro’s**

- **Data Abstraction**: Users can interact with data without worrying about internal complexities.
- **Data Independence**: Changes in the database schema do not affect the application programs.
- **Reduced Redundancy**: Centralized control minimizes data duplication.
- **Security**: Role-based access controls can restrict data access.
- **Concurrent Access**: Allows multiple users to access data simultaneously without conflict.
- **Backup and Recovery**: Built-in features help restore data in case of failure.
- **Data Integrity**: Enforces rules such as data types, constraints, and referential integrity.

### **# Con’s**

- **Cost**: Requires investment in hardware, software, and skilled personnel.
- **Complexity**: Installation, configuration, and maintenance require expertise.
- **Performance**: Can be slower for lightweight or single-user applications.
- **Resource Consumption**: Requires more memory and processing power than file systems.
