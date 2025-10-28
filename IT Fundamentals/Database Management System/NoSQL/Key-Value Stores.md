## **Key-Value Stores**

- A **NoSQL key-value store** is a type of non-relational database that stores data as collections of **key-value pairs**.
- Each **key** is unique and serves as an identifier, while the **value** can be a simple data type (like a string or number) or more complex structures, such as JSON objects, lists, or blobs.

## **Key Characteristics**

- **Simplicity:**
    - Key-value stores are among the simplest NoSQL models, functioning like a persistent, large-scale hash table or dictionary.
    - You retrieve the value directly by its key, with no schema or relational structure.
- **Schema-less:**
    - There is no enforced schema for the values, so the structure and type of data can vary across entries.
    - This design gives you flexibility to store any kind of content - structured, semi-structured, or unstructured
- **Scalability and Performance:**
    - Their flat structure enables extremely fast reads and writes (often O(1) complexity), making them ideal for high-throughput, low-latency use cases.
- **Basic Operations:**
    - The main operations are:
        - **Put** (add or update a key with a value)
        - **Get** (retrieve the value by key)
        - **Delete** (remove a key and its value)
- **No Query Language:**
    - You can't query by value or perform complex searches/joins;
    - access is strictly through keys

## **Typical Use Cases**

- **Caching:**
    - Due to their speed, key-value stores are widely used as caches.
- **Session Management:**
    - Web session data can be stored and retrieved quickly based on session identifiers.
- **Configuration Storage:**
    - Store application or system configuration settings.
- **User Profiles & Preferences:**
    - Fast retrieval by user ID or object key.

## **Examples of Key-Value Stores**

- **Redis**
- **Amazon DynamoDB (when used in key-value mode)**
- **Riak**
- **Memcached**

## **Example**

```sql
textKey: user_123
Value: {"name": "Alice", "email": "alice@example.com", "role": "admin"}
```