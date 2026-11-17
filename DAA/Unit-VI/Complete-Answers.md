# Unit VI — Complete Exam Answers
## Multithreaded and Distributed Algorithms | DAA (410241) | SPPU 2019 Course

> Answers use plain-text formulas for MS Word compatibility. PYQ marks and wording are included where verified. Other questions are syllabus-based practice.

---

## 1. Explain multithreaded algorithms and their performance measures. [Syllabus-based]

**Q. Explain multithreaded algorithms and the performance measures used to analyze them.**

### Introduction
A multithreaded algorithm divides a computation into multiple tasks called threads. These threads can execute concurrently and may run on multiple processor cores.

The objective is to reduce execution time by performing independent tasks in parallel.

### Important performance measures

1. Work (T1):
   - Total time required to execute all operations using one processor.
   - It represents the total amount of computation.

2. Span (T-infinity):
   - Length of the longest dependency path in the computation.
   - It is also called critical-path length.
   - It represents the minimum possible execution time with unlimited processors.

3. Parallelism:
   - Ratio of work to span.
   - Parallelism = T1 / T-infinity.
   - It indicates the maximum available average concurrency.

4. Speedup:
   - Ratio of sequential execution time to parallel execution time.
   - Speedup = T1 / Tp, where Tp is execution time on p processors.

5. Efficiency:
   - Measures processor utilization.
   - Efficiency = Speedup / p.

### Example
Suppose:
- Work T1 = 100 units.
- Span T-infinity = 20 units.
- Processors p = 4.
- Actual parallel time Tp = 30 units.

Parallelism = 100 / 20 = 5.

Speedup = 100 / 30 = 3.33.

Efficiency = 3.33 / 4 = 0.8325 or 83.25%.

### Work-span lower bound
For p processors, execution time cannot be smaller than:

Tp >= max(T1 / p, T-infinity)

### Conclusion
Work, span, parallelism, speedup and efficiency are important measures for understanding the performance and scalability of multithreaded algorithms.

---

## 2. Explain the analysis of multithreaded algorithms, parallel loops and race conditions. [7 Marks]

**Q. With respect to Multithreaded Algorithms explain analyzing multithreaded algorithms, Parallel loops and Race conditions.**

### 1. Analyzing multithreaded algorithms
A multithreaded algorithm is analyzed using:

- Work (T1): Total operations performed.
- Span (T-infinity): Longest chain of dependent operations.
- Parallelism: T1 / T-infinity.
- Parallel running time: Tp on p processors.
- Speedup: T1 / Tp.

The analysis identifies which operations can run simultaneously and which operations require synchronization.

### 2. Parallel loops
A parallel loop executes independent iterations concurrently instead of executing them one after another.

Example: Sequential loop

```
for i = 0 to n-1
    A[i] = B[i] + C[i]
```

Parallel form:

```
parallel for i = 0 to n-1
    A[i] = B[i] + C[i]
```

Each iteration writes to a different array location, so the iterations are independent.

For n constant-time iterations:
- Work = O(n).
- Span = O(1), assuming enough processors and ideal scheduling.
- With p processors, ideal time is O(n/p), plus scheduling overhead.

### 3. Race condition
A race condition occurs when two or more threads access shared data concurrently and at least one access is a write, so the final result depends on the execution order.

Example:

```
shared counter = 0

Thread 1: counter = counter + 1
Thread 2: counter = counter + 1
```

Both threads may read 0, calculate 1 and write 1. The expected result is 2, but the actual result may be 1.

### Prevention
- Use mutex locks.
- Use semaphores.
- Use atomic operations.
- Avoid unnecessary shared variables.
- Use thread-safe data structures.

### Conclusion
Multithreaded analysis measures work and dependencies, parallel loops execute independent iterations concurrently, and synchronization is required to prevent race conditions.

---

## 3. Explain spawn and sync keywords used in multithreaded programming. [May–June 2025, 6 Marks]

**Q. What do you understand by spawn and sync keywords used in multithreaded programming?**

### Spawn
- The spawn keyword indicates that a procedure or task may execute in parallel with the calling procedure.
- It creates a parallel task.
- The parent computation can continue without waiting immediately for the spawned task.

### Sync
- The sync keyword acts as a synchronization point.
- It makes the current procedure wait until its previously spawned child tasks have completed.
- It ensures that required parallel computations finish before dependent work continues.

### Example

```
procedure parallel_sum(A, low, high)
    if low == high
        return A[low]

    mid = (low + high) / 2

    x = spawn parallel_sum(A, low, mid)
    y = spawn parallel_sum(A, mid+1, high)

    sync

    return x + y
```

### Explanation
1. The array is divided into two parts.
2. Two recursive tasks are spawned.
3. Both tasks may execute concurrently.
4. The sync statement waits for both results.
5. The two partial sums are added.

### Advantages
- Supports parallel execution.
- Improves processor utilization.
- Makes divide-and-conquer algorithms parallel.
- Provides a clear synchronization point.

### Conclusion
Spawn creates parallel tasks, while sync ensures that spawned tasks complete before the program proceeds with dependent operations.

---

## 4. Write a simple multithreaded matrix multiplication algorithm by parallelizing the relevant loops. [May–June 2025, 8 Marks]

**Q. Write a simple multithreaded matrix multiplication algorithm based on parallelizing relevant loops of the conventional procedure.**

### Introduction
Matrix multiplication is the process of multiplying two matrices A and B to obtain matrix C.

If A is of size m × n and B is of size n × p, then C is of size m × p.

Each element is calculated as:

C[i][j] = sum of A[i][k] × B[k][j], for k = 0 to n-1.

### Multithreaded algorithm

```
MULTITHREADED-MATRIX-MULTIPLY(A, B, m, n, p)
    create matrix C[m][p]

    parallel for i = 0 to m-1
        for j = 0 to p-1
            sum = 0
            for k = 0 to n-1
                sum = sum + A[i][k] * B[k][j]
            C[i][j] = sum

    return C
```

### Working
1. Create the result matrix C.
2. Divide the rows of C among multiple threads.
3. Each thread calculates assigned elements.
4. Every output element is independent because it uses fixed rows of A and columns of B.
5. Store each calculated value in C.
6. Return the completed matrix after all threads finish.

### Complexity
For square matrices of size n × n:
- Total work = O(n^3).
- If each output element is assigned independently and enough processors are available, the computation span is O(n), because each element requires a sequential sum of n products.
- With p processors, an ideal work-based lower bound is O(n^3/p), but the span lower bound is O(n).
- Practical execution also includes scheduling and memory overhead.

### Advantages
- Independent output elements can be calculated concurrently.
- Row-wise partitioning is simple.
- Synchronization is minimal when each thread writes to separate output cells.

### Conclusion
Multithreaded matrix multiplication parallelizes independent rows or output elements, reducing execution time when sufficient processor cores and memory bandwidth are available.

---

## 5. Compare row-wise and block-wise approaches in multithreaded matrix multiplication. [November–December 2025, 8 Marks]

**Q. Compare and contrast row-wise and block-wise approaches in multithreaded matrix multiplication with respect to division of work, communication overhead and cache efficiency.**

| Row-wise approach | Block-wise approach |
|---|---|
| Matrix rows are divided among threads. | Matrix is divided into smaller submatrices or tiles. |
| Each thread computes one or more complete rows of the result. | Each thread computes one or more blocks of the result. |
| Simple to implement and schedule. | Requires more complex block assignment. |
| Communication is usually low for independent output rows. | Communication and synchronization depend on block distribution and data sharing. |
| May repeatedly access columns of the second matrix with poor locality. | Reuses data blocks and can improve cache locality. |
| Suitable for simple parallelization. | Suitable for large matrices and cache-aware optimization. |
| Load balance is usually straightforward for equal row sizes. | Load balance depends on block size and task distribution. |

### Conclusion
Row-wise decomposition is simple, while block-wise decomposition can improve cache efficiency and data reuse for large matrices. The better choice depends on matrix size, memory hierarchy and processor architecture.

---

## 6. Write and explain pseudocode for Multithreaded Merge Sort. Explain the advantage of parallel merging. [9 Marks]

**Q. Write and explain pseudo code for multi-threaded merge sort algorithm. How does parallel merging give a significant parallelism advantage over Merge Sort?**

### Introduction
Multithreaded Merge Sort is a parallel version of Merge Sort. It divides the input array into two halves and sorts both halves concurrently.

### Pseudocode

```
PARALLEL-MERGE-SORT(A, low, high)
    if low >= high
        return

    mid = (low + high) / 2

    spawn PARALLEL-MERGE-SORT(A, low, mid)
    spawn PARALLEL-MERGE-SORT(A, mid+1, high)

    sync

    PARALLEL-MERGE(A, low, mid, high)
```

### Working
1. Divide the array into two halves.
2. Spawn two recursive sorting tasks.
3. Both halves are sorted concurrently.
4. Sync waits until both sorting tasks finish.
5. Merge the two sorted halves.
6. Continue recursively until the complete array is sorted.

### Parallel merging
In ordinary Merge Sort, merging two sorted halves is sequential and takes O(n) time at a problem size n.

Parallel merging divides the merge task into smaller independent subproblems:
- Select an element from one sorted half.
- Find its correct position in the other half using binary search.
- Place the element in its final output position.
- Recursively process the remaining portions in parallel.

A suitable parallel merge algorithm can achieve O(log n) span for merging two sorted arrays of total size n, with O(n) work, under the standard comparison model and suitable parallel execution.

### Complexity
For conventional Merge Sort:
- Work / time: O(n log n).
- Auxiliary space: O(n).

For multithreaded Merge Sort with sequential merging:
- Work: O(n log n).
- Span: O(n), because the top-level merge is sequential.
- Parallelism: O(log n).

With a parallel merge whose span is O(log n):
- Work: O(n log n).
- Span: O(log^2 n).
- Parallelism: O(n log n / log^2 n) = O(n / log n).

These are idealized work-span bounds; actual running time depends on scheduling, memory and synchronization overhead.

### Conclusion
Multithreaded Merge Sort runs the two recursive sorting branches concurrently. Parallel merging reduces the critical path and exposes more parallelism than sequential merging.

---

## 7. Explain distributed algorithms and their characteristics. [Syllabus-based]

**Q. Explain distributed algorithms and their important characteristics.**

### Definition
A distributed algorithm solves a problem using multiple computers or processing nodes connected through a communication network.

Each node performs part of the computation and exchanges messages with other nodes to coordinate the solution.

### Characteristics
1. Multiple nodes: Computation is divided among different machines.
2. Message passing: Nodes communicate by sending and receiving messages.
3. No shared memory assumption: Each node generally has its own local memory.
4. Concurrency: Nodes execute simultaneously.
5. Coordination: Nodes coordinate to reach a common result.
6. Scalability: More nodes can be added to handle larger workloads.
7. Fault tolerance: Some distributed systems are designed to continue despite node or link failures.

### Challenges
- Communication delay.
- Network failure.
- Synchronization.
- Message ordering.
- Duplicate or lost messages.
- Load balancing.

### Applications
- Distributed databases.
- Cloud computing.
- Sensor networks.
- Distributed graph processing.
- Large-scale search and analytics.

### Conclusion
Distributed algorithms divide computation among networked nodes and use communication and coordination to solve problems that may be too large or costly for one machine.

---

## 8. Write and explain a Distributed Breadth-First Search algorithm. State its advantages over conventional BFS. [May–June 2025, 8 Marks]

**Q. Write distributed breadth first search algorithm. What is its advantage over the conventional approach?**

### Introduction
Breadth-First Search (BFS) traverses a graph level by level from a source vertex.

In distributed BFS, graph vertices or edges are stored across multiple processing nodes. Nodes exchange messages to discover vertices at the next level.

### Level-synchronous distributed BFS pseudocode

Assumptions:
- The graph is partitioned among processing nodes.
- Each node stores its local vertices and relevant adjacency information.
- Nodes can exchange messages with neighbouring partitions.
- A global frontier synchronization is available.

```
DISTRIBUTED-BFS(source)
    for each local vertex v
        visited[v] = false
        distance[v] = infinity

    owner(source):
        visited[source] = true
        distance[source] = 0

    frontier = {source}

    while global frontier is not empty
        next_frontier = empty

        for each vertex u in local frontier
            for each neighbour v of u
                send DISCOVER(v, distance[u] + 1)
                to owner(v)

        receive discovery messages

        for each received vertex v
            if visited[v] == false
                visited[v] = true
                distance[v] = received distance
                add v to next_frontier

        synchronize all nodes
        frontier = next_frontier
```

### Working
1. Initialize all vertices as unvisited.
2. Mark the source with distance zero.
3. Process all vertices in the current frontier.
4. Send discovery messages to the nodes that own neighbouring vertices.
5. Each owner marks a vertex only on its first valid discovery.
6. Synchronize nodes after processing the current level.
7. Continue until no node has a new frontier vertex.

### Advantages over conventional BFS
- Distributes graph processing among multiple machines.
- Can handle graphs larger than one machine's memory.
- Can reduce elapsed time for large graphs when communication costs are manageable.
- Supports scalable graph analytics.

### Limitations
- Network communication adds overhead.
- Synchronization between levels may be expensive.
- Performance depends on graph partitioning and load balance.

### Complexity
For a single-machine adjacency-list BFS, time complexity is O(V + E).

For distributed BFS, total graph work remains O(V + E) in a well-designed implementation, but elapsed time depends on partitioning, message volume, network latency and synchronization. A single universal distributed time bound cannot be stated without a machine and communication model.

### Conclusion
Distributed BFS explores a graph level by level across multiple nodes. It is useful for very large graphs, but communication and synchronization must be considered.

---

## 9. Explain an algorithm for Distributed Minimum Spanning Tree. [May–June 2023 / November–December 2023]

**Q. Explain an algorithm for Distributed Minimum Spanning Tree.**

### Definition
A Minimum Spanning Tree (MST) of a connected, undirected, weighted graph is a set of edges that connects all vertices without forming a cycle and has minimum total weight.

In a distributed setting, graph vertices and edges are stored across multiple nodes. Nodes communicate to select edges and build the MST.

### Distributed Borůvka-style approach

Assumptions:
- The graph is connected, undirected and weighted.
- Each vertex or component can communicate with the node storing an incident edge.
- Edge weights have a consistent ordering, with ties broken consistently.
- Components exchange their selected minimum outgoing edges.

### Algorithm
1. Initially, each vertex is a separate component.
2. Each component examines its outgoing edges.
3. Select the minimum-weight edge connecting the component to a different component.
4. Communicate the selected edge to the relevant component.
5. Add selected safe edges and merge connected components.
6. Repeat until only one component remains.
7. The selected edges form the MST.

### Pseudocode

```
DISTRIBUTED-MST(G)
    each vertex starts as a separate component
    MST = empty

    while more than one component exists
        each component finds its minimum outgoing edge
        communicate selected edges to component members
        remove duplicate selections
        add safe selected edges to MST
        merge components connected by selected edges

    return MST
```

### Explanation
- Every component chooses its cheapest outgoing edge.
- By the cut property of MSTs, a minimum-weight edge crossing a cut is safe for inclusion (with appropriate tie handling).
- Multiple components can select edges concurrently.
- The number of components decreases after successful merges.

### Complexity
- Borůvka's algorithm performs O(log V) phases because the number of components reduces by at least a constant factor in each phase.
- In a centralized implementation, the total work is O(E log V).
- In a distributed implementation, communication rounds and message complexity depend on the network model, graph partition and component coordination method.

### Advantages
- Supports distributed graph storage.
- Components can process their outgoing edges concurrently.
- Suitable for large distributed graphs.

### Conclusion
A distributed Borůvka-style algorithm builds an MST by repeatedly selecting minimum outgoing edges from components and merging them. Its correctness relies on the MST cut property.

---

## 10. Explain the Naive String Matching algorithm with pseudocode and complexity. [November–December 2022, 8 Marks]

**Q. Write a pseudo code for naïve string matching algorithm and analyze the same.**

### Introduction
String matching is the process of finding occurrences of a pattern P in a text T.

Let:
- n = length of text T.
- m = length of pattern P.
- Assume m <= n.

### Naive algorithm

```
NAIVE-STRING-MATCHER(T, P)
    n = length(T)
    m = length(P)

    for s = 0 to n-m
        j = 0

        while j < m and T[s+j] == P[j]
            j = j + 1

        if j == m
            print "Pattern occurs at shift", s
```

### Working
1. Align the pattern with the first m characters of the text.
2. Compare characters from left to right.
3. If all m characters match, report the shift.
4. Otherwise, shift the pattern one position to the right.
5. Repeat until all possible alignments are checked.

### Example
Text T = KITCHEN  
Pattern P = HEN

| Shift | Text window | Result |
|---:|---|---|
| 0 | KIT | Mismatch |
| 1 | ITC | Mismatch |
| 2 | TCH | Mismatch |
| 3 | CHE | Mismatch |
| 4 | HEN | Match |

Pattern found at index 4 (zero-based).

### Complexity
- Number of alignments = n - m + 1.
- At most m character comparisons per alignment.
- Worst-case time = O((n - m + 1)m) = O(nm).
- Best case can be O(n - m + 1) when the first character mismatches at every alignment.
- Auxiliary space = O(1), excluding output.

### Conclusion
Naive string matching checks the pattern at every possible text position. It is simple but may require O(nm) time in the worst case.

---

## 11. Write and explain the Rabin–Karp string matching algorithm. Give expected and worst-case runtime. [May–June 2024, 10 Marks]

**Q. Write a Rabin-Karp string matching algorithm. Input to the algorithm be: Original text t of length n and pattern text p of length m. What is the expected runtime and worst-case runtime of this algorithm?**

### Introduction
Rabin–Karp is a string matching algorithm that uses hashing to find a pattern in a text.

Instead of comparing all characters at every shift, it first compares the hash value of the pattern with the hash value of each text window.

### Working principle
1. Calculate the hash value of the pattern.
2. Calculate the hash value of the first text window of length m.
3. Compare both hash values.
4. If hashes are equal, verify the characters to avoid a false match.
5. Calculate the next window hash using the rolling hash formula.
6. Continue until all windows are checked.

### Rolling hash
For a text window of length m, let:
- d = number of possible characters in the alphabet.
- q = prime modulus.
- h = d^(m-1) mod q.
- pHash = pattern hash.
- tHash = current text-window hash.

The next hash is:

tHashNext = (d × (tHash - leadingCharacter × h) + nextCharacter) mod q

If the hash becomes negative, add q to make it non-negative.

### Pseudocode

```
RABIN-KARP(T, P, d, q)
    n = length(T)
    m = length(P)
    h = d^(m-1) mod q

    pHash = 0
    tHash = 0

    for i = 0 to m-1
        pHash = (d*pHash + code(P[i])) mod q
        tHash = (d*tHash + code(T[i])) mod q

    for s = 0 to n-m
        if pHash == tHash
            if T[s ... s+m-1] == P
                print "Pattern occurs at shift", s

        if s < n-m
            tHash = (d*(tHash - code(T[s])*h)
                     + code(T[s+m])) mod q

            if tHash < 0
                tHash = tHash + q
```

### Spurious hit
A spurious hit occurs when the pattern hash and text-window hash are equal but the actual strings are different.

Therefore, character-by-character verification is required whenever the hashes match.

### Complexity
- Preprocessing: O(m).
- Expected time: O(n + m), assuming a suitable hash and that spurious hits are limited.
- Worst-case time: O((n - m + 1)m) = O(nm), when many hash collisions require full verification.
- Auxiliary space: O(1), excluding output.

### Conclusion
Rabin–Karp uses hashing and rolling hash to perform efficient string matching. It has expected O(n + m) time under suitable assumptions and O(nm) worst-case time.

---

## 12. Solve a Rabin–Karp spurious-hit problem using modulo arithmetic. [November–December 2023, 8 Marks]

**Q. For string matching, working modulo q = 11, how many spurious hits does the Rabin-Karp matcher encounter in T = 31415926535, P = 26?**

### Given
- Text T = 31415926535
- Pattern P = 26
- Pattern length m = 2
- Modulus q = 11
- Use decimal digits, so d = 10.

Pattern hash:

26 mod 11 = 4

### Calculate each two-digit text window

| Shift | Text window | Window mod 11 | Comparison |
|---:|---:|---:|---|
| 0 | 31 | 9 | No match |
| 1 | 14 | 3 | No match |
| 2 | 41 | 8 | No match |
| 3 | 15 | 4 | Hash hit — spurious |
| 4 | 59 | 4 | Hash hit — spurious |
| 5 | 92 | 4 | Hash hit — spurious |
| 6 | 26 | 4 | Exact match |
| 7 | 65 | 10 | No match |
| 8 | 53 | 9 | No match |
| 9 | 35 | 2 | No match |

### Result
- Hash hits = 4.
- Exact matches = 1.
- Spurious hits = 4 - 1 = 3.

Therefore, **the Rabin–Karp matcher encounters 3 spurious hits**.

### Conclusion
A hash match does not always indicate an actual pattern match. Exact character verification identifies and rejects spurious hits.

---

## 13. Compare Naive String Matching and Rabin–Karp algorithms. [Syllabus-based]

**Q. Differentiate between Naive String Matching and Rabin–Karp algorithms.**

| Naive String Matching | Rabin–Karp |
|---|---|
| Compares pattern characters directly at every shift. | Compares hash values of pattern and text windows first. |
| Does not require hashing. | Uses a rolling hash function. |
| Simple to implement. | Requires hash calculation and rolling update. |
| Worst-case time O(nm). | Expected O(n + m) under suitable assumptions; worst-case O(nm). |
| No spurious hash hits. | Hash collisions can cause spurious hits. |
| Suitable for small texts and patterns. | Useful when hashing can reduce repeated character comparisons. |

### Conclusion
Naive matching directly compares characters, while Rabin–Karp uses rolling hashes to reduce expected work. Both have O(nm) worst-case time.

---

## 14. Explain the Plagiarism Detection case study using string matching algorithms. [Syllabus case study]

**Q. Explain how string matching algorithms can be used for plagiarism detection.**

### Introduction
Plagiarism detection is the process of identifying text copied or closely reused from another document without proper acknowledgement.

String matching algorithms can help locate common sequences between documents.

### Working procedure
1. Collect the documents to be compared.
2. Preprocess the text:
   - Normalize case.
   - Remove or standardize unnecessary spaces.
   - Handle punctuation consistently.
   - Tokenize text into words or other suitable units.
3. Select a document or passage as the pattern.
4. Use Naive or Rabin–Karp string matching to locate matching sequences in another document.
5. Record matching positions and lengths.
6. Calculate similarity measures and generate a report.
7. A human reviewer examines the matches and context.

### Role of algorithms
- Naive matching: Checks a selected phrase at every possible position.
- Rabin–Karp: Uses rolling hashes to search for repeated phrases efficiently.
- Multiple patterns or document fingerprints can be used in larger systems, but these are extensions beyond the basic syllabus algorithms.

### Advantages
- Helps locate copied text.
- Reduces manual comparison effort.
- Can process many documents.
- Identifies matching passages for review.

### Limitations
- Common phrases may match by coincidence.
- Paraphrased text may not be detected by exact string matching.
- Formatting and language variations affect results.
- A matching passage does not automatically prove plagiarism.

### Conclusion
String matching algorithms support plagiarism detection by finding repeated text sequences. Final judgement requires context, citation checking and human review.

---

## 15. Explain parallel merging and why it improves the parallelism of Merge Sort. [Syllabus-based]

**Q. Explain parallel merging and its advantage over conventional sequential merging.**

### Conventional merge
In ordinary Merge Sort, after sorting two halves, the merge procedure compares their elements sequentially and creates one sorted array.

For n total elements:
- Work = O(n).
- Span = O(n).

This sequential merge can become the critical path.

### Parallel merge
Parallel merging divides the merge operation into smaller independent tasks:
1. Choose a pivot element from one sorted array.
2. Use binary search to find its correct position in the other sorted array.
3. Place the pivot in the final output position.
4. Recursively merge the left portions in parallel.
5. Recursively merge the right portions in parallel.

Under a suitable parallel merge algorithm:
- Work = O(n).
- Span = O(log n).

### Comparison

| Sequential merge | Parallel merge |
|---|---|
| Processes elements sequentially. | Divides merging into independent subproblems. |
| Work O(n). | Work O(n). |
| Span O(n). | Can achieve O(log n) span. |
| Limits available parallelism. | Exposes more parallel tasks. |
| Simple implementation. | More complex partitioning and synchronization. |

### Conclusion
Parallel merging reduces the critical path of the merge phase and improves the available parallelism of multithreaded Merge Sort.

---

## 16. Explain the role of string matching in text processing. [Syllabus-based]

**Q. Explain string matching and its applications.**

### Definition
String matching is the process of finding whether a pattern P occurs in a larger text T and identifying all positions where it occurs.

### Important terms
- Text (T): Main string in which the search is performed.
- Pattern (P): String to be searched.
- Shift: Position at which the pattern is aligned with the text.
- Match: All pattern characters match the corresponding text characters.
- Spurious hit: Equal hash values without an actual string match, in hash-based matching.

### Algorithms in the syllabus
1. Naive String Matching:
   - Checks every possible shift.
   - Worst-case O(nm).

2. Rabin–Karp:
   - Uses hash values and rolling hash.
   - Expected O(n + m) under suitable assumptions.
   - Worst-case O(nm).

### Applications
- Text search.
- Document comparison.
- Plagiarism detection support.
- Search engines.
- Pattern detection in logs and data.

### Conclusion
String matching is a fundamental text-processing operation. Naive and Rabin–Karp are two methods for locating patterns in a text.
