'''
CIST 005B Fall 2024
Lab Week 8
Description: A stress test for a hash table using ISBNs and book titles
Input: None
Output: The timing of the hash table using insertion, lookup, and deletion
Student: Chris Amey and Mina Yeap
Known bugs: None
Date: 11/4/2024
'''

###############################################
# This code was made with the help of ChatGPT #
###############################################

import time
import random
import string

# Node class for linked list
class Node:
    def __init__(self, isbn, title):
        self.isbn = isbn  # Key
        self.title = title  # Value
        self.next = None  # Pointer to the next Node

# HashTable class
class HashTable:
    def __init__(self, size=997):  # Using a prime number for the hash table size
        self.size = size
        self.table = [None] * self.size  # Initialize the hash table with empty buckets

    # Hash function to compute index for a given ISBN
    def hash_function(self, isbn):
        # Simple hash function: sum of ASCII values modulo the table size
        return hash(isbn) % self.size

    def insert(self, isbn, title):
        index = self.hash_function(isbn)
        new_node = Node(isbn, title)
        current = self.table[index]
        if current is None:
            self.table[index] = new_node
        else:
            if current.isbn == isbn:
                current.title = title
            while current.next:
                current = current.next
                if current.isbn == isbn:
                    current.title = title
                    break
            if current.isbn != isbn:
                current.next = new_node



    # Lookup a book by ISBN
    def lookup(self, isbn):
        index = self.hash_function(isbn)
        current = self.table[index]
        while current:
            if current.isbn == isbn:
                #print(f"Found ISBN {isbn} at index {index} with title '{current.title}'")
                return current.title
            current = current.next
        #print(f"ISBN {isbn} not found in the hash table.")
        return None

    # Delete a book record by ISBN
    def delete(self, isbn):
        index = self.hash_function(isbn)
        current = self.table[index]
        prev = None
        while current:
            if current.isbn == isbn:
                if prev:
                    prev.next = current.next
                else:
                    self.table[index] = current.next
                #print(f"Deleted ISBN {isbn} from index {index}")
                return True  # Deletion successful
            prev = current
            current = current.next
        #print(f"ISBN {isbn} not found for deletion.")
        return False  # ISBN not found

    # Display all book records in the hash table
    def display(self):
        #print("\nDisplaying all book records in the hash table:")
        for i in range(self.size):
            current = self.table[i]
            if current:
                print(f"Bucket {i}:")
                while current:
                    print(f"  ISBN: {current.isbn}, Title: {current.title}")
                    current = current.next

# Function to generate a random ISBN number (13-digit string)
def generate_isbn():
    return ''.join(random.choices(string.digits, k=13))

# Function to generate a random book title
def generate_title():
    words = random.randint(2, 5)
    return ' '.join(''.join(random.choices(string.ascii_letters, k=random.randint(3, 8))) for _ in range(words))

# Function to perform test cases
def test_hash_table(record_count):
    print(f"\n--- Testing with {record_count} records ---")
    hash_table = HashTable()
    records = []

    # Generating test data
    for _ in range(record_count):
        isbn = generate_isbn()
        title = generate_title()
        records.append((isbn, title))

    # Insert items
    for isbn, title in records[:-1]:
        hash_table.insert(isbn, title)

    '''
    for bucket in hash_table.table:
        if bucket:
            current = bucket
            counter = 1
            while current.next:
                current = current.next
                counter += 1
            print(f"Bucket {hash_table.table.index(bucket)} contains {counter} items.")
        else:
            print("empty")
    '''

    hash_table.display()

    # Insert last item
    isbn, title = records[-1]
    start_time = time.time()
    hash_table.insert(isbn, title)
    insertion_time = time.time() - start_time
    print(f"Insertion time for {record_count}th record: {insertion_time:.6f} seconds")

    # Measuring lookup time
    start_time = time.time()
    hash_table.lookup(isbn)
    lookup_time = time.time() - start_time
    print(f"Lookup time for {record_count}th record: {lookup_time:.6f} seconds")

    # Measuring deletion time
    start_time = time.time()
    hash_table.delete(isbn)
    deletion_time = time.time() - start_time
    print(f"Deletion time for {record_count}th record: {deletion_time:.6f} seconds")

    # Optional: Display the hash table (should be empty after deletion)
    # hash_table.display()

# Main function to run the test cases
if __name__ == "__main__":
    # Running test cases for 10, 100, and 1000 records
    test_hash_table(10000)
    #test_hash_table(100*100)
    #test_hash_table(1000**2)

#Expected Output
'''
--- Testing with 1000 records ---
Insertion time for 1000 records: 0.001001 seconds
Lookup time for 1000 records: 0.001001 seconds
Deletion time for 1000 records: 0.000000 seconds

--- Testing with 10000 records ---
Insertion time for 10000 records: 0.007509 seconds
Lookup time for 10000 records: 0.043160 seconds
Deletion time for 10000 records: 0.044704 seconds

--- Testing with 100000 records ---
Insertion time for 100000 records: 0.100310 seconds
Lookup time for 100000 records: 10.957053 seconds
Deletion time for 100000 records: 12.513210 seconds

'''
