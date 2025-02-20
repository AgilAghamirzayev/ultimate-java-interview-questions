# Advanced databased interview questions

**1. What are the difference row and column based databases?**


**2. What are the difference clustered and non-clustered indexes?**

### **Difference Between Clustered and Non-Clustered Indexes**

Clustered and non-clustered indexes are two types of indexing mechanisms used in databases to improve query performance. Here are the key differences:

---

#### **1. **Storage and Data Organization****
- **Clustered Index**:
    - A clustered index determines the physical order of data in a table. The rows of the table are stored on disk in the same order as the clustered index.
    - There can be only **one clustered index per table** because the data rows themselves can only be sorted in one order.
    - Example: If a table has a clustered index on the `ID` column, the rows will be physically stored on disk in ascending or descending order of `ID`.

- **Non-Clustered Index**:
    - A non-clustered index does not alter the physical order of the data. Instead, it creates a separate structure that contains the indexed columns and a pointer to the actual data rows.
    - You can have **multiple non-clustered indexes** on a table.
    - Example: A non-clustered index on the `Email` column will create a separate structure that stores the `Email` values and pointers to the corresponding rows in the table.

---

### **Summary Table**

| **Aspect**               | **Clustered Index**                          | **Non-Clustered Index**                     |
|--------------------------|----------------------------------------------|---------------------------------------------|
| **Number per table**      | Only one                                     | Multiple                                    |
| **Physical order of data**| Determines the physical order of rows        | Does not affect the physical order of rows  |
| **Storage**               | No additional storage (data is the index)    | Requires additional storage                 |
| **Performance**           | Faster for range queries                    | Faster for filtering and sorting            |
| **Best for**              | Primary keys, range queries                 | Columns used in `WHERE` or `JOIN` clauses  |
| **Leaf nodes**            | Contain actual data rows                   | Contain pointers to data rows               |

---

Understanding the differences between clustered and non-clustered indexes is crucial for database design and optimization, especially when working with large datasets and performance-critical applications.