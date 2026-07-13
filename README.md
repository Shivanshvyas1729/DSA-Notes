# DSA-Notes
something is cooking
https://docs.google.com/spreadsheets/d/1nToH69nQEp5npk9WSPqj4CVzabannLvkW4ILNMu6k3c/edit?gid=234757707#gid=234757707



Here is the comprehensive extraction of the Data Structures and Algorithms (DSA) and Python Basics document you provided. The content, definitions, and examples have been retained and organized according to the source text.

## 1. Introduction to DSA and Python Basics

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


<img width="455" height="327" alt="image" src="https://github.com/user-attachments/assets/cd17fd4a-febc-4f0e-9dbf-478e60d1abba" />




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
<img width="413" height="350" alt="image" src="https://github.com/user-attachments/assets/e50eee5f-d13e-43a1-8840-b65464decab5" />


<img width="445" height="264" alt="image" src="https://github.com/user-attachments/assets/fb688f17-d905-4a1f-b7b5-0ed203b9b86b" />

<img width="461" height="207" alt="image" src="https://github.com/user-attachments/assets/67816867-713e-487a-9e9c-5a119a80ac96" />



---

## 2. Arrays & Lists

### Arrays

* **What is an Array?** An array is a data structure that stores a collection of elements of the same data type in contiguous memory locations.


* *Image Reference:* The contiguous memory representation of an array is located on **Part 1 Page 22**.


* **Properties:** Homogeneous elements, Contiguous Memory Allocation, Fixed Index Access, Efficient Iteration.


* **Fixed-Size Arrays:** Size is decided at creation, stored contiguously, more memory-efficient but less flexible. Best for predictable, stable data like offline learning.


* **Dynamic-Size Arrays:** Can grow or shrink during runtime, allocates extra "spare" memory to allow future growth. Best for unpredictable, growing datasets like online learning.



### Lists

* **What is a List?** A list is a built-in and versatile data structure that can hold elements of different data types. It is a dynamic, ordered and mutable sequence in Python.


* **Properties:** Ordered (maintains insertion sequence), Mutable, Allows Duplicates, Supports Indexing, Heterogeneous (mixed data types), Dynamic Size.
<img width="540" height="469" alt="image" src="https://github.com/user-attachments/assets/1dd4dc97-0f1c-4ad9-8777-f3d2b2992d65" />



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


<img width="557" height="93" alt="image" src="https://github.com/user-attachments/assets/04af2113-9c4b-4720-b275-303337aafbd5" />

---

## 3. Strings

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
<img width="545" height="269" alt="image" src="https://github.com/user-attachments/assets/3150ef01-9fb9-4445-b306-8fda6ba7ec6e" />


<img width="529" height="136" alt="image" src="https://github.com/user-attachments/assets/1f84d650-eb78-4f8e-8a70-956ae9b8babb" />

<img width="414" height="610" alt="image" src="https://github.com/user-attachments/assets/47568865-bb5c-4480-83b0-ae634a66d89e" />
<img width="453" height="300" alt="image" src="https://github.com/user-attachments/assets/0e75e6a6-c412-4673-92f6-f5ee7d4fc3ec" />

<img width="497" height="344" alt="image" src="https://github.com/user-attachments/assets/dd0ae1f0-925c-44b4-81a4-d28a17db56ac" />

---

## 4. Linked Lists

### Introduction

* **What is a Linked List?** A linear data structure composed of nodes connected by pointers (or references). Each node contains a data element and a pointer to the next node.

<img width="497" height="648" alt="image" src="https://github.com/user-attachments/assets/9e1676a8-2e0c-45b7-be35-ec497c2efde4" />

<img width="493" height="369" alt="image" src="https://github.com/user-attachments/assets/40cd77dd-b768-452f-a9d4-6b05bb9a23b9" />


* They do not require contiguous memory and can dynamically change size.


* **Key Features:** Dynamic Size, Non-Contiguous Memory Allocation, Efficient Insertions and Deletions, Sequential Access Only.


* **ML Analogy:** ML Pipelines, Neural Network Architectures (stacked layers), Gradient Descent Steps, Graph Representation.

<img width="549" height="340" alt="image" src="https://github.com/user-attachments/assets/0c044918-5666-40c1-99ca-5b08193252d5" />

<img width="518" height="568" alt="image" src="https://github.com/user-attachments/assets/16c724fe-55bc-4dcb-bc19-f6203b7391f4" />

<img width="529" height="122" alt="image" src="https://github.com/user-attachments/assets/5e26936f-7481-4b37-ba14-4ee9ec41ddf9" />

### Types of Linked Lists

* **Singly Linked List:** Node has Data and Next pointer. Traversal is only forward. Last node points to None.




* **Circular Singly Linked List:** Last node points back to the head instead of None, forming a circular chain.


* **Doubly Linked List:** Node has Prev, Data, and Next. Allows bidirectional traversal (forward & backward).


<img width="427" height="562" alt="image" src="https://github.com/user-attachments/assets/b1e03228-c38d-48bf-9ea2-ee5156c90ce5" />

<img width="418" height="598" alt="image" src="https://github.com/user-attachments/assets/92fc2307-0754-499f-9d51-a0e0bbf83092" />



* **Circular Doubly Linked List:** Combines circular and doubly linked lists. Last node points back to head, head's Prev points to last node.



---

## 5. Stacks

### Introduction

* **What is a Stack?** A linear data structure that stores elements in a sequential order where insertion and deletion happen only from one end (the top).

<img width="552" height="393" alt="image" src="https://github.com/user-attachments/assets/70c1f30f-a8c1-43a7-989a-1271b0d7f1aa" />



* It follows the LIFO (Last In, First Out) principle.


* **Common Operations:** Push, Pop, Peek, isEmpty.


* **Implementations:** Lists, `collections` (deque), Linked Lists.


* **Applications:** Undo/Redo in Text Editors, Browser navigation, Function calls, Parentheses/Bracket matching.



### DS Context

* **Data Science / ML Correlation:** Neural network forward/backward pass.


* **Libraries & Usage:** PyTorch autograd, TensorFlow graph execution.



---

## 6. Queues

### Introduction

* **What is a Queue?** A linear data structure that follows the FIFO (First In, First Out) principle—the first element added is the first one removed.


<img width="360" height="549" alt="image" src="https://github.com/user-attachments/assets/9f7cdc84-5b84-4a26-9806-c53c930fd3f4" />



* **Real-World Applications:** Call Center Systems, CPU / Process Scheduling, Data Preprocessing (ML training stages), Streaming Data & Online Learning, Model Serving & Inference.


* **Common Operations:** Enqueue (insert at rear), Dequeue (remove from front), FrontPeek, RearPeek, isEmpty.


* **Implementations:** Lists, Linked List, `collections`, `heapq` (Priority Queues), `queue`, `asyncio`.



### DS Context

* **Data Science / ML Correlation:** Mini-batch training, Stochastic Gradient Descent (SGD) batches.


* **Libraries & Usage:** TensorFlow Data API (`tf.data.Dataset`), PyTorch DataLoader.



---

## 7. Searching

* **Linear Search:** Also known as sequential search. Examines each element sequentially until the target is found. No sorting required. Time Complexity: $O(n)$. Space Complexity: $O(1)$.


* **Binary Search:** Efficient "divide and conquer" algorithm for sorted arrays. Calculates the midpoint and adjusts the search bounds. Time Complexity: $O(log n)$. Space Complexity: $O(1)$.


* **Exponential Search:** Also known as Doubling or Galloping Search. Efficient for very large or unbounded sorted arrays. Finds a range by doubling the index, then applies Binary Search within that range.



### DS Context

* **Data Science / ML Correlation:** Hyperparameter tuning, Threshold optimization, Nearest neighbor search.


* **Libraries & Usage:** scikit-learn (`GridSearchCV`), FAISS, scipy.



---

## 8. Sorting

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

## 9. Recursion

### Introduction

* **What is Recursion?** A programming technique where a function calls itself to solve smaller subproblems until a specific base case (stopping condition) is met.


* **Structure:** Consists of a Base Case (stops infinite recursion) and a Recursive Case (divides problem into smaller versions).


* **Internal Working:** Managed using a Call Stack (LIFO data structure). New stack frames (activation records) are pushed for each call. Once the base case is reached, stack unwinding occurs.


* **Recursion vs Iteration:** Recursion uses the call stack, is elegant and mathematical, but uses more memory. Iteration uses loops, is faster and memory efficient.



### DS Context

* **Data Science / ML Correlation:** Tree-based models, Hierarchical modeling.


* **Libraries & Usage:** scikit-learn (DecisionTree, RandomForest), Recursive splitting in trees.



---

## 10. Hashing

### Introduction

* **What is Hashing?** A technique that converts a key into a fixed-size number called a hash value, which is then mapped to a specific index in a Hash Table.


<img width="390" height="204" alt="image" src="https://github.com/user-attachments/assets/bf6209e0-c436-4e7a-a8f1-c08f4ee9b82e" />



* **Hash Function Properties:** Deterministic, Uniform Distribution, Fast Computation, Low Collision.


* **Hash Collisions:** Occurs when two different keys produce the same table index. Resolved via Chaining (linked lists) or Open Addressing (Linear/Quadratic Probing, Double Hashing).


* **Load Factor:** The ratio of the Number of elements inserted to the Total number of buckets. It determines when to resize the hash table.
<img width="243" height="419" alt="image" src="https://github.com/user-attachments/assets/6dc0cb41-25b7-45d2-9d0d-3e641b0b703a" />
<img width="508" height="107" alt="image" src="https://github.com/user-attachments/assets/a128f629-839d-4b76-9bcd-69d87c2f1c68" />




### DS Context

* **Data Science / ML Correlation:** Feature encoding, Caching & memoization, Deduplication.


* **Libraries & Usage:** `sklearn.feature_extraction.FeatureHasher`.



---

## 11. Patterns & Problem Solving

* **Sliding Window:** Maintains a running window (expanding right, shrinking left) to process contiguous subarrays in $O(n)$ time.


* **Two Pointers:** Two indices traverse the array from different directions to solve problems efficiently (usually $O(n)$ or $O(n log n)$).


* **Fast & Slow Pointers:** Uses two pointers moving at different speeds to detect cycles or find the middle of a sequence.


* **Prefix Sum:** An array storing the cumulative sum up to each index for fast subarray sum calculations.


* **Hashing:** Used for frequency counting, duplicate detection, and grouping.


* **Binary Search Pattern:** Used beyond basic search when the search space is monotonic (True/False transitions).


* **Greedy Approach:** Making locally optimal choices at each step hoping it leads to a global optimum.



---

## 12. Trees

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

## 13. Graphs

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
