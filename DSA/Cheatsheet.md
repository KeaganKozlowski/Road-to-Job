# Data Structures and Algorithms (DSA) Cheat Sheet

A quick reference guide for common data structures, algorithms, Big-O complexities, and problem-solving patterns.

---

## 📊 Big-O Time & Space Complexity

### Data Structures

| Data Structure | Access | Search | Insertion | Deletion | Space Complexity |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Array** | `O(1)` | `O(n)` | `O(n)` | `O(n)` | `O(n)` |
| **Stack** | `O(n)` | `O(n)` | `O(1)` | `O(1)` | `O(n)` |
| **Queue** | `O(n)` | `O(n)` | `O(1)` | `O(1)` | `O(n)` |
| **Singly Linked List** | `O(n)` | `O(n)` | `O(1)` | `O(1)` | `O(n)` |
| **Doubly Linked List** | `O(n)` | `O(n)` | `O(1)` | `O(1)` | `O(n)` |
| **Hash Table** | `N/A` | `O(1)` | `O(1)` | `O(1)` | `O(n)` |
| **Binary Search Tree** | `O(log n)` | `O(log n)` | `O(log n)` | `O(log n)` | `O(n)` |
| **B-Tree** | `O(log n)` | `O(log n)` | `O(log n)` | `O(log n)` | `O(n)` |
| **AVL Tree** | `O(log n)` | `O(log n)` | `O(log n)` | `O(log n)` | `O(n)` |

> *Note: Hash Table operations are `O(1)` on average, but `O(n)` in the worst case (many collisions). BST operations are `O(log n)` on average, but `O(n)` in the worst case (unbalanced tree).*

### Sorting Algorithms

| Algorithm | Best Time | Average Time | Worst Time | Space Complexity |
| :--- | :---: | :---: | :---: | :---: |
| **Quicksort** | `O(n log n)` | `O(n log n)` | `O(n^2)` | `O(log n)` |
| **Mergesort** | `O(n log n)` | `O(n log n)` | `O(n log n)` | `O(n)` |
| **Heapsort** | `O(n log n)` | `O(n log n)` | `O(n log n)` | `O(1)` |
| **Bubble Sort** | `O(n)` | `O(n^2)` | `O(n^2)` | `O(1)` |
| **Insertion Sort**| `O(n)` | `O(n^2)` | `O(n^2)` | `O(1)` |
| **Selection Sort**| `O(n^2)` | `O(n^2)` | `O(n^2)` | `O(1)` |

---

## 🏗️ Core Data Structures Quick Reference

### Arrays & Strings
* **Pros:** Fast lookups (`O(1)` access), cache-friendly.
* **Cons:** Fixed size (in some languages), expensive inserts/deletes at the beginning/middle (`O(n)`).
* **Use when:** You need fast indexed access and the data size is relatively static.

### Hash Tables / Maps / Dictionaries
* **Pros:** Lightning-fast lookups, inserts, and deletes (`O(1)` average).
* **Cons:** Unordered data, higher memory overhead, collision resolution can degrade performance.
* **Use when:** Counting frequencies, caching/memoization, or requiring `O(1)` lookups by a key.

### Linked Lists
* **Pros:** Fast insertions and deletions at the head/tail (`O(1)`). Dynamic size.
* **Cons:** Slow search (`O(n)` access), extra memory for pointers.
* **Use when:** You need constant time insertions/deletions and don't need random access.

### Stacks (LIFO - Last In, First Out)
* **Pros:** `O(1)` push and pop operations.
* **Use when:** Parsing expressions (e.g., valid parentheses), undo/redo features, iterative depth-first search (DFS).

### Queues (FIFO - First In, First Out)
* **Pros:** `O(1)` enqueue and dequeue operations.
* **Use when:** Task scheduling, breadth-first search (BFS), handling asynchronous requests.

### Trees & Graphs
* **Trees:** Hierarchical data. Binary Search Trees (BST) keep data sorted. Tries are excellent for prefix searching (autocomplete).
* **Graphs:** Networks of nodes (vertices) and connections (edges). Represent social networks, maps, dependencies.

---

## 🧩 Common Algorithmic Patterns

Knowing *how* to approach a problem is often more important than memorizing code. Look for these patterns:

1.  **Sliding Window:**
    * **Use for:** Arrays or strings. Finding subarrays or substrings based on a condition (e.g., "longest substring without repeating characters").
    * **Concept:** Maintain a "window" that expands or contracts as you iterate through the data.
2.  **Two Pointers:**
    * **Use for:** Sorted arrays or linked lists. (e.g., "Find pairs that sum to a target").
    * **Concept:** Iterate with two pointers moving towards each other, or in the same direction at different speeds.
3.  **Fast & Slow Pointers (Tortoise & Hare):**
    * **Use for:** Linked lists or cyclic arrays.
    * **Concept:** One pointer moves by 1 step, the other by 2 steps. Useful for finding the middle of a linked list or detecting cycles.
4.  **Merge Intervals:**
    * **Use for:** Overlapping intervals or scheduling problems.
    * **Concept:** Sort intervals by start time, then iterate and merge if the current interval overlaps with the previous one.
5.  **Breadth-First Search (BFS):**
    * **Use for:** Trees or Graphs. Finding the *shortest path* in an unweighted graph, exploring level-by-level.
    * **Data Structure:** Queue.
6.  **Depth-First Search (DFS):**
    * **Use for:** Trees or Graphs. Exploring all possibilities, pathfinding, topological sorting.
    * **Data Structure:** Stack (or Recursion).
7.  **Dynamic Programming (DP):**
    * **Use for:** Optimization problems, counting paths, overlapping subproblems (e.g., Fibonacci, Knapsack).
    * **Concept:** Break down into smaller subproblems. Store results (memoization) to avoid redundant calculations.

---

## 🌳 Tree Traversals

Given a Binary Tree, the order in which nodes are visited:

* **In-Order (Left, Root, Right):** Visits nodes in ascending order (for BSTs).
* **Pre-Order (Root, Left, Right):** Useful for duplicating trees.
* **Post-Order (Left, Right, Root):** Useful for deleting trees.
* **Level-Order (BFS):** Visits nodes level by level from top to bottom.