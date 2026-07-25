# DSA-Notes

something is cooking
[https://docs.google.com/spreadsheets/d/1nToH69nQEp5npk9WSPqj4CVzabannLvkW4ILNMu6k3c/edit?gid=234757707#gid=234757707](https://docs.google.com/spreadsheets/d/1nToH69nQEp5npk9WSPqj4CVzabannLvkW4ILNMu6k3c/edit?gid=234757707#gid=234757707)
[https://www.risingbrain.org/sheet](https://www.risingbrain.org/sheet)

Here is the comprehensive extraction of the Data Structures and Algorithms (DSA) and Python Basics document you provided. The content, definitions, and examples have been retained and organized according to the source text.

### Importance of DSA

* **What is DSA?** Data Structures and Algorithms are the twof fundamental pillars of computer science and software development.
* DSA helps manage and preprocess large datasets, optimize pipelines, and write fast algorithms for feature engineering or model evaluation.
* **Data Structures:** A particular way of organizing and storing data so it can be accessed and modified efficiently.
* Linked Lists are used for Streaming Data where you can't load full data into memory.
* Hash Tables are used for One-hot Encoding and Label Encoding.
* Stacks/Queues are used for Data Pipelines and Rolling Windows.
* Trees are used for Decision Trees, Random Forests, and Boosting methods.
* Graphs are used for Social Networks and Recommendation Systems.
* **Algorithms:** A step-by-step procedure to solve a specific problem or perform a task.
* Examples include Searching (Linear, Binary), Sorting (Bubble, Merge, Quick), Recursion, Dynamic Programming, and Graph algorithms (BFS, DFS).
* **Why Learn DSA?** To build strong problem-solving skills, crack coding interviews, develop better system design thinking, and improve debugging and optimization.
* It allows you to write optimized code, reduce time and space complexity, handle large datasets efficiently, and write scalable programs.
* It forms the core for advanced topics like Machine Learning (matrix operations), Web development (caching, queues), Blockchain, Compilers, and Operating Systems.

### Time & Space Complexity

* **Why Analyze Complexity?** When working with large datasets or building scalable ML/DS systems, it is crucial to estimate how fast an algorithm runs (Time Complexity) and know how much memory it uses (Space Complexity).

| Notation | Name | Meaning / Represents | Analogy |
| --- | --- | --- | --- |
| $\Omega(f(n))$ | Big Omega | Best-case performance | - |
| $\Theta(f(n))$ | Big Theta | Average-case / tight bound | - |
| $O(f(n))$ | Big O | Worst-case performance | - |
| $O(1)$ | Constant | - | Flipping a light switch |
| $O(log n)$ | Logarithmic | - | Finding a word in a dictionary |
| $O(n)$ | Linear | - | Scanning every row in a dataset |
| $O(n log n)$ | Linearithmic | - | Efficient sorting (Merge Sort) |
| $O(n^{2})$ | Quadratic | - | Comparing each row with every other row |
| $O(2^{n})$ | Exponential | - | Trying every possible combination |

### Python Refresher

* **Numeric Types:** `int` (Integer values), `float` (Floating-point numbers), `complex` (Complex numbers like 3+5j).
* **Sequence Types:** `str` (Text characters), `list` (Mutable ordered collection), `tuple` (Immutable ordered collection), `range` (Sequence of numbers).
* **Set Types:** `set` (Mutable, unordered), `frozenset` (Immutable version of set).
* **Mapping Types:** `dict` (Unordered key-value store).
* **Boolean Type:** `bool` (True or False).
* **None Type:** Represents None.


---

### Arrays

* **What is an Array?** An array is a data structure that stores a collection of elements of the same data type in contiguous memory locations.
* *Image Reference:* The contiguous memory representation of an array is located on **Part 1 Page 22**.
* **Properties:** Homogeneous elements, Contiguous Memory Allocation, Fixed Index Access, Efficient Iteration.
* **Fixed-Size Arrays:** Size is decided at creation, stored contiguously, more memory-efficient but less flexible. Best for predictable, stable data like offline learning.
* **Dynamic-Size Arrays:** Can grow or shrink during runtime, allocates extra "spare" memory to allow future growth. Best for unpredictable, growing datasets like online learning.

### Lists

* **What is a List?** A list is a built-in and versatile data structure that can hold elements of different data types. It is a dynamic, ordered and mutable sequence in Python.
* **Properties:** Ordered (maintains insertion sequence), Mutable, Allows Duplicates, Supports Indexing, Heterogeneous (mixed data types), Dynamic Size.


### Arrays vs Lists Comparison

| Property | Array | List |
| --- | --- | --- |
| **Data Type** | Collection of homogeneous elements | Heterogeneous collection |
| **Memory** | Stored in contiguous memory, memory efficient | Stores references to objects, less efficient |
| **Performance** | Faster for numerical operations (NumPy) | Slower for element-wise math |
| **Flexibility** | Generally fixed in size | Can grow/shrink dynamically |
| **Functionality** | Supports math operations directly | Needs manual loops for math |
| **Use Cases** | ML datasets, image data, numerical simulations | Data collection, mixed-type storage |

### DS Context

* **Data Science / ML Correlation:** Feature vectors, datasets, tensors. Model inputs and outputs are arrays.
* **Libraries & Usage:** NumPy (ndarray), Pandas (Series & DataFrame columns), TensorFlow / PyTorch (tensors).
Here is the time complexity for every Python list operation, based on CPython's internal implementation.

## 1. Basic Operators & Indexing

| Operation | Syntax Example | Time Complexity | Notes / Description |
| --- | --- | --- | --- |
| Index Access | lst[i] | $O(1)$ | Direct lookup via memory offset. |
| Index Assignment | lst[i] = x | $O(1)$ | Direct overwrite at memory offset. |
| Concatenation | lst1 + lst2 | $O(n + m)$ | Dependent on the sizes of both lists. |
| Repetition | lst * k | $O(k \cdot n)$ | Allocation size depends on factor $k$. |
| Membership | x in lst | $O(n)$ | Linear scan from start to finish. |
| Basic Slicing (Get) | lst[a:b] | $O(k)$ | $k$ is the length of the slice ($b - a$). |
| Slice Assignment | lst[a:b] = src | $O(k + n)$ | Requires shifting remaining elements. |

---

## 2. Built-In Global Functions

| Function | Syntax Example | Time Complexity | Notes / Description |
| --- | --- | --- | --- |
| Length check | len(nums) | $O(1)$ | CPython tracks list size explicitly. |
| Maximum | max(nums) | $O(n)$ | Must check every item once. |
| Minimum | min(nums) | $O(n)$ | Must check every item once. |
| Summation | sum(nums) | $O(n)$ | Math addition across all items. |
| Global Sort | sorted(nums) | $O(n \log n)$ | Uses Timsort algorithm; creates a copy. |
| Construction | list(iterable) | $O(n)$ | Iterates over the source collection. |

---

## 3. Built-In List Methods

| Method | Syntax Example | Time Complexity | Notes / Description |
| --- | --- | --- | --- |
| append() | lst.append(x) | $O(1)$ | Amortized constant time; fast at end. |
| extend() | lst.extend(iterable) | $O(k)$ | $k$ is the size of the added iterable. |
| insert() | lst.insert(i, x) | $O(n)$ | Must shift all elements after index $i$. |
| remove() | lst.remove(x) | $O(n)$ | Linear search followed by shifting items. |
| pop() (last) | lst.pop() | $O(1)$ | Fast because no shifting is required. |
| pop() (index) | lst.pop(i) | $O(n)$ | Must shift all elements after index $i$. |
| clear() | lst.clear() | $O(n)$ | Clears references to all elements. |
| index() | lst.index(x) | $O(n)$ | Linear search for the first match. |
| count() | lst.count(x) | $O(n)$ | Scans the entire list to count items. |
| sort() | lst.sort() | $O(n \log n)$ | In-place Timsort; $O(n)$ if pre-sorted. |
| reverse() | lst.reverse() | $O(n)$ | In-place swap from outer edges inward. |
| copy() | lst.copy() | $O(n)$ | Allocates space for a shallow copy. |

---

## 4. Advanced Operations

| Operation | Syntax Example | Time Complexity | Notes / Description |
| --- | --- | --- | --- |
| Delete Index | del lst[i] | $O(n)$ | Shifts elements to fill the gap. |
| Delete Slice | del lst[a:b] | $O(n)$ | Shifts elements after the deleted chunk. |
| Comprehension | [x for x in lst] | $O(n)$ | Evaluates expression for each item. |

## Key Takeaway for Optimization

* Fast ($O(1)$): Operations hitting the end of the list (append, pop()) or direct index access (lst[i]).
* Slow ($O(n)$): Operations hitting the beginning or middle of the list (insert(0, x), pop(0), remove) because Python must shift all subsequent items in memory to maintain order. [1, 2, 3, 4]

Would you like to explore how to use alternatives like collections.deque if you need fast $O(1)$ insertions at the beginning, or do you want to analyze a specific script's total time complexity?

[1] [https://www.reddit.com](https://www.reddit.com/r/learnpython/comments/1hztaox/if_time_complexity_of_pop_first_item_is_on_and/)
[2] [https://www.cs.swarthmore.edu](https://www.cs.swarthmore.edu/~knerr/teaching/topics/linkedlists.html)
[3] [https://medium.com](https://medium.com/@mohitarvindjoshi/the-truth-about-python-lists-nobody-told-you-7b2a5ae3e4e2)
[4] [https://medium.com](https://medium.com/@ivanmarkeyev/understanding-python-list-operations-a-big-o-complexity-guide-49be9c00afb4)

---

### Introduction and Properties

* **What is a String?** A string is a sequence of characters enclosed within quotes. They are ordered sequences where characters have a defined index starting from 0.
* **Properties:** Ordered sequences, Immutable (cannot be modified after creation), Iterable, Slicing supported (`[start:end:step]`), Unicode-based (UTF-8), supports Concatenation and Repetition.
* **Use cases:** Handling Textual Data (names, emails, file paths), Foundation for Algorithms (Pattern Matching, Hashing, Parsing), Basis for Natural Language Processing (Tokenization, sentiment analysis).

### String Comparison

* Strings are compared lexicographically (like words in a dictionary), checking character by character from left to right based on Unicode code points.
* If all characters match but lengths differ, the shorter string is considered smaller.

### DS Context

* **Data Science / ML Correlation:** Text data processing, NLP pipelines.
* **Libraries & Usage:** `re` for text cleaning, NLTK/spaCy for tokenization, `transformers` for BERT/GPT tokenizers.


---

### Introduction

* **What is a Linked List?** A linear data structure composed of nodes connected by pointers (or references). Each node contains a data element and a pointer to the next node.

* They do not require contiguous memory and can dynamically change size.
* **Key Features:** Dynamic Size, Non-Contiguous Memory Allocation, Efficient Insertions and Deletions, Sequential Access Only.
* **ML Analogy:** ML Pipelines, Neural Network Architectures (stacked layers), Gradient Descent Steps, Graph Representation.

### Types of Linked Lists

* **Singly Linked List:** Node has Data and Next pointer. Traversal is only forward. Last node points to None.
* **Circular Singly Linked List:** Last node points back to the head instead of None, forming a circular chain.
* **Doubly Linked List:** Node has Prev, Data, and Next. Allows bidirectional traversal (forward & backward).

* **Circular Doubly Linked List:** Combines circular and doubly linked lists. Last node points back to head, head's Prev points to last node.

---

### Introduction

* **What is a Stack?** A linear data structure that stores elements in a sequential order where insertion and deletion happen only from one end (the top).

* It follows the LIFO (Last In, First Out) principle.
* **Common Operations:** Push, Pop, Peek, isEmpty.
* **Implementations:** Lists, `collections` (deque), Linked Lists.
* **Applications:** Undo/Redo in Text Editors, Browser navigation, Function calls, Parentheses/Bracket matching.

### DS Context

* **Data Science / ML Correlation:** Neural network forward/backward pass.
* **Libraries & Usage:** PyTorch autograd, TensorFlow graph execution.

---

### Introduction

* **What is a Queue?** A linear data structure that follows the FIFO (First In, First Out) principle—the first element added is the first one removed.

* **Real-World Applications:** Call Center Systems, CPU / Process Scheduling, Data Preprocessing (ML training stages), Streaming Data & Online Learning, Model Serving & Inference.
* **Common Operations:** Enqueue (insert at rear), Dequeue (remove from front), FrontPeek, RearPeek, isEmpty.
* **Implementations:** Lists, Linked List, `collections`, `heapq` (Priority Queues), `queue`, `asyncio`.

### DS Context

* **Data Science / ML Correlation:** Mini-batch training, Stochastic Gradient Descent (SGD) batches.
* **Libraries & Usage:** TensorFlow Data API (`tf.data.Dataset`), PyTorch DataLoader.

---

* **Linear Search:** Also known as sequential search. Examines each element sequentially until the target is found. No sorting required. Time Complexity: $O(n)$. Space Complexity: $O(1)$.
* **Binary Search:** Efficient "divide and conquer" algorithm for sorted arrays. Calculates the midpoint and adjusts the search bounds. Time Complexity: $O(log n)$. Space Complexity: $O(1)$.
* **Exponential Search:** Also known as Doubling or Galloping Search. Efficient for very large or unbounded sorted arrays. Finds a range by doubling the index, then applies Binary Search within that range.

### DS Context

* **Data Science / ML Correlation:** Hyperparameter tuning, Threshold optimization, Nearest neighbor search.
* **Libraries & Usage:** scikit-learn (`GridSearchCV`), FAISS, scipy.

---

### Classifications

* **Based on Implementation:** Internal Sorting (fits in main memory) vs External Sorting (stored in external memory).
* **Based on Stability:** Stable (equal elements maintain relative order) vs Unstable (equal elements may change order).
* **Based on Time Complexity:** Quadratic Time ($O(n^{2})$) vs Log-linear Time ($O(n log n)$).

### Sorting Algorithms

* **Bubble Sort:** Compares neighboring pairs and swaps them if out of order. Time: $O(n^{2})$. Space: $O(1)$. Stable.
* **Selection Sort:** Finds the smallest element in the unsorted part and swaps it with the first element of the unsorted section. Time: $O(n^{2})$. Space: $O(1)$. Unstable.
* **Insertion Sort:** Inserts the current element into its correct position in the sorted part. Works well for small or almost sorted lists. Time: $O(n^{2})$. Space: $O(1)$. Stable.
* **Merge Sort:** Divides the list into halves, then merges them in sorted order. Time: $O(n log n)$. Space: $O(n)$. Stable.
* **Quick Sort:** Chooses a pivot and partitions the list into elements smaller and greater than the pivot. Time: $O(n log n)$ average. Space: $O(log n)$. Unstable.
* **Counting Sort:** Counts frequencies of unique elements and uses them to place elements directly. Best for integers in a small range. Time: $O(n + k)$. Space: $O(k)$. Stable.

### DS Context

* **Data Science / ML Correlation:** Ranking predictions, Feature importance ordering, Evaluation metrics (Top-K).
* **Libraries & Usage:** `numpy.argsort()`, `pandas.sort_values()`, Recommendation systems.

---

### Introduction

* **What is Recursion?** A programming technique where a function calls itself to solve smaller subproblems until a specific base case (stopping condition) is met.
* **Structure:** Consists of a Base Case (stops infinite recursion) and a Recursive Case (divides problem into smaller versions).
* **Internal Working:** Managed using a Call Stack (LIFO data structure). New stack frames (activation records) are pushed for each call. Once the base case is reached, stack unwinding occurs.
* **Recursion vs Iteration:** Recursion uses the call stack, is elegant and mathematical, but uses more memory. Iteration uses loops, is faster and memory efficient.

### DS Context

* **Data Science / ML Correlation:** Tree-based models, Hierarchical modeling.
* **Libraries & Usage:** scikit-learn (DecisionTree, RandomForest), Recursive splitting in trees.

---

### Introduction

* **What is Hashing?** A technique that converts a key into a fixed-size number called a hash value, which is then mapped to a specific index in a Hash Table.

* **Hash Function Properties:** Deterministic, Uniform Distribution, Fast Computation, Low Collision.
* **Hash Collisions:** Occurs when two different keys produce the same table index. Resolved via Chaining (linked lists) or Open Addressing (Linear/Quadratic Probing, Double Hashing).
* **Load Factor:** The ratio of the Number of elements inserted to the Total number of buckets. It determines when to resize the hash table.



### DS Context

* **Data Science / ML Correlation:** Feature encoding, Caching & memoization, Deduplication.
* **Libraries & Usage:** `sklearn.feature_extraction.FeatureHasher`.

---

* **Sliding Window:** Maintains a running window (expanding right, shrinking left) to process contiguous subarrays in $O(n)$ time.
* **Two Pointers:** Two indices traverse the array from different directions to solve problems efficiently (usually $O(n)$ or $O(n log n)$).
* **Fast & Slow Pointers:** Uses two pointers moving at different speeds to detect cycles or find the middle of a sequence.
* **Prefix Sum:** An array storing the cumulative sum up to each index for fast subarray sum calculations.
* **Hashing:** Used for frequency counting, duplicate detection, and grouping.
* **Binary Search Pattern:** Used beyond basic search when the search space is monotonic (True/False transitions).
* **Greedy Approach:** Making locally optimal choices at each step hoping it leads to a global optimum.

---

### Introduction

* **What is a Tree?** A non-linear hierarchical data structure consisting of nodes connected by edges, organizing data in a parent-child relationship with no cycles.
* *Image References:* Tree visuals and Traversal examples are located on **Pages 497-511**.
* **Terminology:** Root, Parent, Child, Leaf, Depth (distance from root), Height (longest path to a leaf), Level, Subtree.

### Traversals & Types

* **DFS Traversals:** Preorder (Root → Left → Right), Inorder (Left → Root → Right), Postorder (Left → Right → Root).
* **BFS Traversal:** Level Order (visits nodes level by level using a Queue).
* **Binary Search Tree (BST):** Left subtree values < Root value < Right subtree values. Average operations run in $O(log n)$ time.
* **N-ary Tree:** A tree where each node can have 0 to N children.
* **Tree DP:** Postorder traversal is the backbone of Tree DP because children's results are needed before computing the parent.

### DS Context

* **Data Science / ML Correlation:** Decision Trees, Random Forests, Gradient Boosted Trees, Hierarchical Clustering (Dendrograms), NLP Parse Trees.

---

### Introduction

* **What is a Graph?** A non-linear data structure defined as G = (V, E) where V is Vertices/Nodes and E is Edges (connections).
* *Image References:* Graph examples and State Space representations are located on **Pages 562-569 and Page 643**.
* **Types:** Undirected vs Directed, Weighted vs Unweighted, Cyclic vs Acyclic, Complete vs Incomplete.
* **Representation:** Adjacency Matrix (Boolean matrix, $O(V^{2})$ space) and Adjacency List (Array of linked lists).

### Traversals & Algorithms

* **Traversal:** DFS (Depth First, uses Stack/Recursion) and BFS (Breadth First, uses Queue).
* **Shortest Path:** Dijkstra’s Algorithm (non-negative weights, min-heap), Bellman-Ford (handles negative weights and detects cycles), Floyd-Warshall (all-pairs).
* **Advanced:** DSU (Disjoint Set Union for connectivity), Prim's MST (Vertex-based, min-heap), Kruskal's MST (Edge-based, sorts edges, uses DSU).
* **DAG (Directed Acyclic Graph):** Solved using Topological Sorting (Kahn’s Algorithm tracking in-degrees).

### DS Context

* **Data Science / ML Correlation:** Recommendation Systems (Node2Vec, GNNs), Fraud Detection, Social Network Analysis (PageRank, Louvain clustering), Search Engines, Bioinformatics.
