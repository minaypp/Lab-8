# Lab-8
**Objectives:**
Implement a hash table with separate chaining to manage book records (ISBN and titles).
Understand key concepts of hashing, collisions, and separate chaining.
Work collaboratively in pairs to design, implement, test, and analyze the hash table.
Analyze the performance of the system by adding, retrieving, and deleting book records.
 

**Requirements:**
Hash Table Implementation:

The hash table will store book records where:
Key: ISBN (unique book identifier).
Value: Book title.
The hash table should handle collisions using separate chaining with linked lists.
Core Features:

Insert a new book record (ISBN and title).
Lookup a book by ISBN.
Delete a book record by ISBN.
Implement a function to display all book records currently stored in the hash table.
Test Cases:

Test the hash table with 10, 100, and 1000 records.
Measure and comment on the time performance for lookup, insertion, and deletion operations.
 

**Suggested Role Division of Labor**
In pairs, you will divide the work as follows to ensure equal contribution:

Role 1: Hash Table Structure & Basic Operations
Design & implement the HashTable class and its data structure (with linked lists for separate chaining).
Write the insert() function to add new book records.
Implement the delete() function to remove a record by ISBN.
Test the initial implementation with sample data and validate the basic operations.
Role 2: Collision Handling & Performance Analysis
Design & implement the linked list structure for chaining.
Write the lookup() function to retrieve book titles by ISBN.
Implement the display() function to list all books in the system.
Conduct performance tests with different data sizes and measure the time efficiency of the hash table.
 

**Rubric:**
Hash Table Implementation: (40 %)

Hash table structure with separate chaining implemented correctly
Proper use of linked lists for collision handling
Accurate handling of insertions, lookups, and deletions
Test Cases & Performance: (20 %)

Test cases implemented with appropriate data sizes
Performance analysis with increasing data and time measurements
Written reflection on hash table efficiency and collision impact
Code Quality & Team Collaboration: (20 %)

Clear and concise code structure with proper comments
Equal contribution from both members, ensuring balanced workload
Demo: (20 %)
