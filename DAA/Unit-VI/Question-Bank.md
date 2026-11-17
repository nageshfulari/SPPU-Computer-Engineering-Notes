# Unit VI — Question Bank
## Multithreaded and Distributed Algorithms | DAA (410241)

**Subject:** Fourth Year Computer Engineering, SPPU, 2019 Course.

PYQ wording and marks below are retained from the directly inspected paper excerpts. If a subquestion's marks were assigned to a combined question, that is stated rather than inventing a separate mark.

## A. Multithreaded Algorithms

| No. | Question | Marks / Source |
|---:|---|---|
| 1 | With respect to Multithreaded Algorithms explain Analyzing multithreaded algorithms, Parallel loops, Race conditions. | Nov–Dec 2022, Q7(b), 7; Nov–Dec 2023, Q7(b), 7 |
| 2 | Write and explain pseudo code for Multi-threaded merge sort algorithm. How parallel merging gives a significant parallelism advantage over Merge Sort? | Nov–Dec 2022, Q8(a), 9; Nov–Dec 2023, Q8(a), 9; May–June 2023, Q7(a), 9 |
| 3 | Write and explain pseudo code for multi-threaded merge sort algorithm. Briefly discuss how does it differ from conventional merge sort. | May–June 2024, Q7(b), 8 |
| 4 | Write a simple multithreaded matrix multiplication algorithm based on parallelizing relevant loops of the conventional procedure. | May–June 2025, Q7(a), 8 |
| 5 | Explain in brief race condition in multithreaded algorithms. | May–June 2025, Q7(b), 4 |
| 6 | What do you understand by spawn and sync keywords used in multithreaded programming? | May–June 2025, Q7(c), 6 |
| 7 | Compare and contrast row-wise and block-wise approaches in multithreaded matrix multiplication with respect to division of work, communication overhead and cache efficiency. | Nov–Dec 2025, Q7(b), 8 |
| 8 | Write short notes on multithreaded matrix multiplication and multithreaded merge sort. | Nov–Dec 2022, Q7(a), combined 10 |
| 9 | Explain work, span, parallelism, speedup and efficiency. | Syllabus-based practice |

## B. Distributed Algorithms

| No. | Question | Marks / Source |
|---:|---|---|
| 10 | Explain an algorithm for Distributed Minimum Spanning Tree. | May–June 2023, Q7(b)(i), 8; Nov–Dec 2023, Q7(a)(i), part of combined 10 |
| 11 | Show stepwise process how the distributed breadth first search algorithm works on the given adjacency matrix. | May–June 2024, Q8(a), 10 |
| 12 | Write distributed breadth search algorithm. What is its advantage over the conventional approach? | May–June 2025, Q8(a), 8 |
| 13 | Write a distributed algorithm to find the minimum spanning tree. | Nov–Dec 2025, Q8(b), 8 |
| 14 | Explain distributed algorithms and their communication challenges. | Syllabus-based practice |

## C. String Matching

| No. | Question | Marks / Source |
|---:|---|---|
| 15 | Write a pseudo code for naïve string matching algorithm and Rabin-Karp algorithm for string matching and analyze the same. | Nov–Dec 2022, Q8(b), 8 |
| 16 | Write and explain Rabin-Karp algorithm for string matching. | May–June 2023, Q7(b)(ii), part of combined question |
| 17 | Write and explain Rabin-Karp algorithm for string matching. | Nov–Dec 2023, Q7(a)(ii), part of combined 10 |
| 18 | For string matching, working modulo q = 11, how many spurious hits does the Rabin-Karp matcher encounter in T = 31415926535, P = 26? | Nov–Dec 2023, Q8(b), 8 |
| 19 | Write a Rabin-Karp string matching algorithm. What is its expected runtime and worst-case runtime? | May–June 2024, Q7(a), 10; May–June 2025, Q8(b), 10 |
| 20 | Consider text T and pattern P. Write a naïve string-matching algorithm and show its working for T = KITCHEN and P = HEN. | Nov–Dec 2025, Q8(a), 10 |

## D. Exemplar / Case Study

| No. | Question | Marks / Source |
|---:|---|---|
| 21 | Explain how Naive and Rabin–Karp string matching algorithms can support plagiarism detection. | Syllabus case study / practice |

## Syllabus coverage checklist

| Syllabus topic | Covered in Complete Answers |
|---|---|
| Introduction to multithreaded algorithms | Yes |
| Performance measures | Yes |
| Analyzing multithreaded algorithms | Yes |
| Parallel loops | Yes |
| Race conditions | Yes |
| Multithreaded matrix multiplication | Yes |
| Multithreaded merge sort | Yes |
| Introduction to distributed algorithms | Yes |
| Distributed BFS | Yes |
| Distributed MST | Yes |
| Introduction to string matching | Yes |
| Naive string matching | Yes |
| Rabin–Karp algorithm | Yes |
| Plagiarism detection case study | Yes |

## Practice guidance
- For multithreaded analysis, define work and span before calculating speedup or parallelism.
- For matrix multiplication, identify which output elements can be computed independently.
- For merge sort, explain spawn, sync and the merge stage separately.
- For distributed BFS, show frontiers level by level and state how duplicate discoveries are handled.
- For distributed MST, state the graph and communication assumptions and explain why selected edges are safe.
- For Rabin–Karp, calculate the pattern hash, every relevant window hash, verify hash hits and count spurious hits.
- For plagiarism detection, distinguish matching evidence from a final plagiarism judgement.
