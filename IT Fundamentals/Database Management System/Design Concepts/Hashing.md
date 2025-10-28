## **Hashing**

- **Hashing** involves converting a **search key** (e.g., a roll number or ID) into a **hash value** (also called a hash address) using a **hash function**. This hash value determines the location (bucket or slot) where the actual data record is stored.
- Think of hashing as a "smart address system" where each key knows exactly where its value is kept.
## **Analogy**

### **# Student Lockers**

Imagine each student is given a locker based on a rule:

- Rule: `locker number = student ID % 10`

So, if a student’s ID is 1023, they get:

locker number = 1023 % 10 = 3

Now, instead of checking each locker one by one, you directly go to locker 3 to find or store the student’s details.

## **Types of Hashing in DBMS**

### **# Static Hashing**

- Hash function always maps to **fixed locations**.
- If a collision happens, a resolution method is used.
- Used when the number of records is known and stable.
- **Collision Resolution Techniques in Static Hashing**:
    - **Chaining**: Each slot points to a linked list of entries.
    - **Linear Probing**: If a slot is full, check the next one.
    - **Quadratic Probing**: Jump in quadratic steps (1², 2², 3²...).
    - **Double Hashing**: Use a second hash function for probing.

### **# Dynamic Hashing**

- The size of the hash table can grow or shrink.
- More flexible; ideal for databases with frequent insertions.
- **Types of Dynamic Hashing**:
    - **Extendible Hashing**:
        - Uses a directory that grows in size.
        - Only splits the directory as needed.
    - **Linear Hashing**:
        - Grows incrementally.
        - Uses a split pointer to control gradual expansion.

## **Terminology**

| Term           | Description                                                                  |
|----------------|------------------------------------------------------------------------------|
| **Hash Function** | Converts a key into an index. Example: `h(key) = key % table_size`              |
| **Bucket**        | A slot where data records are stored                                          |
| **Overflow**      | Occurs when multiple keys hash to the same index                              |
| **Collision**     | When different keys hash to the same address                                  |

## **Key Properties**

- **Deterministic**: Always produces the same output for the same input.
- **Uniform Distribution**: Spreads keys evenly across buckets.
- **Minimizes Collisions**: Reduces chances of two keys getting the same hash.
- **Efficient**: Quick to compute.

## **Importance**

- **Fast access** to records using keys.
- Ideal for **indexing** and **search-heavy applications**.
- Used in internal memory structures and **NoSQL databases**.
