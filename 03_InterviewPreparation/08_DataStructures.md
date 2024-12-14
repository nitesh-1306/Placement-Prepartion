# Data Structures and Algorithms Interview Comprehensive Guide

## 1. Fundamental Concepts

### 1.1 What are Data Structures?
Data structures are specialized formats for organizing, storing, and managing data efficiently. They provide a way to store and access data more effectively.

### 1.2 What are Algorithms?
Algorithms are step-by-step procedures or formulas for solving problems and performing computations.

## 2. Basic Data Structures

### 2.1 Arrays
- **Definition**: Contiguous memory locations storing similar-type elements
- **Operations**: 
  - Insertion
  - Deletion
  - Searching
  - Traversing

**Time Complexities:**
- Access: O(1)
- Search: O(n)
- Insertion: O(n)
- Deletion: O(n)

**Code Example (Python):**
```python
# Static Array
arr = [1, 2, 3, 4, 5]

# Dynamic Array
dynamic_arr = []
dynamic_arr.append(6)
```

### 2.2 Linked Lists

#### Types of Linked Lists
1. **Singly Linked List**
2. **Doubly Linked List**
3. **Circular Linked List**

**Advantages:**
- Dynamic size
- Easy insertion and deletion

**Time Complexities:**
- Access: O(n)
- Search: O(n)
- Insertion: O(1)
- Deletion: O(1)

**Code Example (Python):**
```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None
```

### 2.3 Stacks
- **LIFO (Last In, First Out)** principle
- **Operations:**
  - Push
  - Pop
  - Peek

**Time Complexities:**
- Push: O(1)
- Pop: O(1)
- Peek: O(1)

**Code Example (Python):**
```python
stack = []
stack.append(1)  # Push
top = stack.pop()  # Pop
```

### 2.4 Queues
- **FIFO (First In, First Out)** principle
- **Types:**
  - Simple Queue
  - Circular Queue
  - Priority Queue
  - Deque

**Time Complexities:**
- Enqueue: O(1)
- Dequeue: O(1)

**Code Example (Python):**
```python
from collections import deque
queue = deque()
queue.append(1)  # Enqueue
first = queue.popleft()  # Dequeue
```

## 3. Advanced Data Structures

### 3.1 Trees

#### Binary Tree
- Each node has maximum two children
- **Types:**
  - Binary Search Tree (BST)
  - AVL Tree
  - Red-Black Tree

**Time Complexities (BST):**
- Search: O(log n)
- Insertion: O(log n)
- Deletion: O(log n)

**Code Example (Python):**
```python
class TreeNode:
    def __init__(self, value):
        self.value = value
        self.left = None
        self.right = None
```

### 3.2 Heaps
- **Types:**
  - Min Heap
  - Max Heap

**Time Complexities:**
- Insertion: O(log n)
- Deletion: O(log n)
- Get Min/Max: O(1)

### 3.3 Hash Tables
- Key-value pair storage
- Fast data retrieval

**Time Complexities:**
- Insert: O(1)
- Delete: O(1)
- Search: O(1)

**Code Example (Python):**
```python
# Dictionary as Hash Table
hash_table = {}
hash_table['key'] = 'value'
```

### 3.4 Graphs
- Collection of vertices and edges
- **Types:**
  - Directed Graph
  - Undirected Graph
  - Weighted Graph

**Representation:**
- Adjacency Matrix
- Adjacency List

## 4. Sorting Algorithms

### 4.1 Comparison Sorting Algorithms

1. **Bubble Sort**
   - Time Complexity: O(n²)
   - Space Complexity: O(1)

2. **Selection Sort**
   - Time Complexity: O(n²)
   - Space Complexity: O(1)

3. **Insertion Sort**
   - Time Complexity: O(n²)
   - Space Complexity: O(1)

4. **Merge Sort**
   - Time Complexity: O(n log n)
   - Space Complexity: O(n)

5. **Quick Sort**
   - Time Complexity: O(n log n)
   - Space Complexity: O(log n)

6. **Heap Sort**
   - Time Complexity: O(n log n)
   - Space Complexity: O(1)

### 4.2 Non-Comparison Sorting
1. Counting Sort
2. Radix Sort
3. Bucket Sort

## 5. Searching Algorithms

### 5.1 Basic Search
1. **Linear Search**
   - Time Complexity: O(n)

2. **Binary Search**
   - Time Complexity: O(log n)
   - Requires sorted array

**Code Example (Python):**
```python
def binary_search(arr, target):
    left, right = 0, len(arr) - 1
    while left <= right:
        mid = (left + right) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            left = mid + 1
        else:
            right = mid - 1
    return -1
```

## 6. Algorithm Design Techniques

### 6.1 Paradigms
1. Divide and Conquer
2. Dynamic Programming
3. Greedy Algorithms
4. Backtracking

## 7. Space and Time Complexity

### 7.1 Big O Notation
- Describes worst-case scenario
- Complexity classes:
  - O(1) - Constant
  - O(log n) - Logarithmic
  - O(n) - Linear
  - O(n log n) - Linearithmic
  - O(n²) - Quadratic
  - O(2ⁿ) - Exponential

## 8. Common Interview Problems

### 8.1 Problem Categories
1. Array Manipulation
2. String Problems
3. Linked List Traversal
4. Tree Traversals
5. Graph Algorithms
6. Dynamic Programming

## 9. Best Practices

### 9.1 Problem-Solving Approach
1. Understand the problem
2. Design algorithm
3. Write clean code
4. Test with multiple scenarios
5. Optimize if possible

## 10. Recommended Practice Resources
- LeetCode
- HackerRank
- CodeForces
- Project Euler
- GeeksforGeeks

## Conclusion
Mastering data structures and algorithms requires consistent practice, understanding core concepts, and solving diverse problems.

## Interview Tips
- Communicate your thought process
- Write clean, modular code
- Handle edge cases
- Discuss time and space complexity
- Practice whiteboard coding