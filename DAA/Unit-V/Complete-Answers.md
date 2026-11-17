# Unit V — Complete Exam Answers
## Amortized Analysis | DAA (410241) | SPPU 2019 Course

> Answers are written in exam-ready language. Formulas use plain keyboard characters for MS Word compatibility. PYQ marks and wording are identified where directly verified; other questions are syllabus-based practice.

---

## 1. Explain the methods of amortized analysis with a suitable example. [6–8 Marks]

**Q. Explain the methods of amortized analysis with a suitable example.**

### Definition
Amortized analysis is a technique used to determine the average cost per operation over a sequence of operations in the worst case.

Some operations may be expensive, but they occur rarely. Amortized analysis distributes their cost over the complete sequence and provides a guaranteed average cost per operation.

It does not use probability and is different from average-case analysis.

### Methods of amortized analysis
There are three main methods:

1. Aggregate method.
2. Accounting method.
3. Potential function method.

### 1. Aggregate method
- Calculate the total actual cost of a sequence of n operations.
- Divide the total cost by n.
- The result gives the amortized cost per operation.

Formula:

Amortized cost = Total cost of n operations / n

### 2. Accounting method
- Assign an artificial charge to each operation.
- Some operations are charged more than their actual cost.
- The extra amount is stored as credit.
- Stored credit is used later to pay for expensive operations.
- Credit must never become negative.

### 3. Potential function method
- Define a potential function Φ(D) that represents stored energy or prepaid work in the data structure.
- The potential increases when cheap operations store future credit and decreases when expensive operations use it.

Amortized cost of operation i:

Amortized cost = Actual cost + Φ(Di) - Φ(Di-1)

For a sequence of n operations:

Total amortized cost = Total actual cost + Φ(Dn) - Φ(D0)

If Φ(D0) = 0 and Φ(Dn) >= 0, total amortized cost is at least the total actual cost.

### Example: Stack operations
Consider a stack supporting PUSH, POP and MULTIPOP(k).

- PUSH inserts one element. Actual cost = 1.
- POP removes one element if the stack is non-empty. Actual cost = 1.
- MULTIPOP(k) removes at most k elements. Its actual cost is the number of elements removed.

Although MULTIPOP may take O(k) time, each element can be pushed only once and popped only once. Therefore, over n stack operations, the total number of successful pushes and pops is bounded by O(n).

Thus, the amortized cost of each stack operation is O(1).

### Conclusion
Amortized analysis gives a guaranteed bound over a sequence of operations. Aggregate, accounting and potential methods are three different ways to prove this bound.

---

## 2. Give an amortized analysis of a k-bit binary counter using the aggregate method. [6 Marks]

**Q. Give an amortized analysis of a k-bit binary counter using the aggregate method.**

### Introduction
A k-bit binary counter stores a binary number using k bits. Initially, all bits are zero. To increment the counter, we add 1 to its current value.

During increment, consecutive trailing 1s become 0 and the first 0 becomes 1.

### Actual cost
The cost of one increment is the number of bits that change.

For example:

Counter before increment: 0111  
Counter after increment: 1000

Here, four bits change. Therefore, actual cost = 4.

### Aggregate analysis
Consider n increment operations on a k-bit counter.

- Bit 0 changes on every increment, so it changes at most n times.
- Bit 1 changes once in every two increments, so it changes at most n/2 times.
- Bit 2 changes once in every four increments, so it changes at most n/4 times.
- In general, bit i changes at most n/2^i times.

Therefore, total number of bit changes is:

T(n) <= n + n/2 + n/4 + n/8 + ...  

This is a geometric series.

T(n) < n(1 + 1/2 + 1/4 + ...)

T(n) < 2n

Hence, total cost of n increment operations is O(n).

Amortized cost per increment:

T(n) / n < 2n / n < 2

Therefore:

**Amortized cost per increment = O(1).**

### Conclusion
Although a single increment may change all k bits and take O(k) time, the total cost of n increments is less than 2n. Hence, the amortized cost of each increment is O(1).

---

## 3. Prove that the amortized cost per operation in a k-bit binary counter is O(1). [5 Marks]

**Q. Prove that the amortized cost per operation in a k-bit binary counter is O(1).**

### Proof using the accounting method
For each increment operation, charge 2 units.

- One unit pays for changing a bit from 0 to 1.
- The second unit is stored as credit on the bit that has become 1.
- When a bit changes from 1 to 0, its stored credit pays for that change.

Every bit that changes from 0 to 1 receives one credit. That credit remains with the bit until it changes from 1 to 0.

Thus, every bit flip is paid for:
- 0 to 1 flip: paid by the current operation.
- 1 to 0 flip: paid by the credit stored earlier.

The stored credit is never negative.

Each increment is charged only 2 units. Therefore, for n increments:

Total amortized charge = 2n

Amortized cost per increment:

2n / n = 2 = O(1)

### Conclusion
The accounting method shows that each increment operation has a constant amortized cost of 2 units. Therefore, amortized cost per operation is O(1), even though an individual increment can take O(k) time.

---

## 4. Explain amortized analysis of a stack using PUSH, POP and MULTIPOP. Find their amortized costs. [9 Marks]

**Q. Explain in brief amortized analysis. Consider stack as an example and single PUSH, single POP and multiple POP operations. Give the amortized costs for these stack operations.**

### Stack operations
A stack follows the LIFO (Last In, First Out) principle.

1. PUSH(x): Inserts element x at the top of the stack.
2. POP(): Removes the top element if the stack is not empty.
3. MULTIPOP(k): Removes at most k elements from the stack or until the stack becomes empty.

### Actual costs
- PUSH: 1.
- POP: 1, if the stack is non-empty.
- MULTIPOP(k): min(k, s), where s is the current number of elements in the stack.

A single MULTIPOP may have a cost of O(k).

### Aggregate analysis
Suppose a sequence contains n stack operations.

An element:
- Can be pushed only once.
- Can be popped only once after it is pushed.

Therefore:
- Total successful PUSH operations <= n.
- Total successful POP operations, including removals by MULTIPOP, <= total successful PUSH operations.

Hence, total number of element insertions and removals is at most 2n.

Total cost <= 2n.

Amortized cost per operation:

2n / n = 2 = O(1)

### Amortized costs using the accounting method
Charge the operations as follows:

| Operation | Actual cost | Amortized charge |
|---|---:|---:|
| PUSH | 1 | 2 |
| POP | 1 | 0 |
| MULTIPOP(k) | Number of elements removed | 0 |

For every PUSH:
- One unit pays for insertion.
- One unit is stored as credit on the inserted element.

When an element is removed by POP or MULTIPOP, its stored credit pays for removal.

Therefore, no operation requires more credit than is available.

### Conclusion
Although MULTIPOP can take O(k) actual time, each element is removed at most once. Hence, the total cost of n stack operations is O(n), and the amortized cost of PUSH, POP and MULTIPOP is O(1) per operation.

---

## 5. Differentiate between amortized analysis and average-case analysis. [Syllabus-based]

**Q. Differentiate between amortized analysis and average-case analysis.**

| Amortized Analysis | Average-Case Analysis |
|---|---|
| Studies a sequence of operations. | Studies expected cost for an input distribution. |
| Gives a worst-case guarantee over the sequence. | Depends on the probability distribution of inputs. |
| Does not require probability. | Uses probability or assumptions about input frequencies. |
| Expensive operations are balanced by cheaper operations in the sequence. | Cost is averaged over possible inputs. |
| Example: Stack PUSH, POP and MULTIPOP. | Example: Average running time of Quick Sort. |

**Conclusion:** Amortized analysis guarantees a bound over every valid operation sequence, whereas average-case analysis depends on the assumed distribution of inputs.

---

## 6. Explain time-space trade-off with suitable examples. [Syllabus-based]

**Q. Explain the time-space trade-off with suitable examples.**

### Definition
Time-space trade-off is a technique in algorithm design in which additional memory is used to reduce execution time, or less memory is used at the cost of increased execution time.

An algorithm designer selects a suitable balance according to system requirements.

### Approaches

1. More space, less time:
   - Store precomputed results or lookup tables.
   - Avoid repeated calculations.
   - Example: A hash table uses extra memory to support average O(1) search.

2. Less space, more time:
   - Recompute values instead of storing them.
   - Use in-place algorithms.
   - Example: Repeatedly calculate a value instead of storing a large table.

### Examples

| Technique | Space usage | Time effect |
|---|---|---|
| Hash table | More memory for buckets and entries | Average search is O(1) |
| Direct-address table | Uses a table proportional to key range | Very fast lookup |
| Memoization | Stores computed results | Avoids repeated recursive work |
| In-place sorting | Uses little auxiliary memory | May involve more data movement or computation |
| Compression | Stores encoded data | Requires encoding/decoding time |

### Factors affecting the choice
- Available memory.
- Required response time.
- Input size.
- Power consumption.
- Hardware limitations.
- Frequency of repeated computations.

### Conclusion
Time-space trade-off helps design efficient algorithms by balancing memory consumption and execution time according to application requirements.

---

## 7. What are tractable and non-tractable problems? Give examples. [7 Marks]

**Q. What are tractable and non-tractable problems? Give examples.**

### Tractable problems
A problem is called tractable if it can be solved by an algorithm whose running time is bounded by a polynomial function of input size.

Examples:
- Sorting using Merge Sort: O(n log n).
- Binary Search: O(log n).
- Minimum Spanning Tree using standard algorithms: polynomial time.
- Searching an unsorted list: O(n).

### Non-tractable / Intractable problems
A problem is commonly called intractable when no polynomial-time algorithm is known for solving all instances optimally, and the known exact approaches may require exponential or factorial time.

Examples:
- Travelling Salesperson Problem (optimization version).
- General 0/1 Knapsack optimization problem.
- Certain scheduling and combinatorial optimization problems.

### Difference

| Tractable | Intractable |
|---|---|
| Solvable in polynomial time. | No polynomial-time exact algorithm is known for general instances of many such problems. |
| Usually practical for large inputs, subject to polynomial degree and constants. | Exact solution may become impractical as input size increases. |
| Examples: sorting, shortest path, MST. | Examples: TSP optimization, general 0/1 Knapsack optimization. |

### Note about complexity classes
- P contains decision problems solvable in polynomial time.
- NP contains decision problems whose proposed solutions can be verified in polynomial time.
- NP-hard problems are at least as hard as every problem in NP under polynomial-time reductions.
- NP-complete problems are both in NP and NP-hard.

It is not proved that P and NP are different. Therefore, avoid claiming that every NP problem is definitely intractable.

### Conclusion
Tractable problems have polynomial-time solutions, while intractable problems are computationally difficult for general input sizes using currently known exact algorithms.

---

## 8. What are randomized algorithms? Explain the reasons for using them. [4–8 Marks]

**Q. What are randomized algorithms? Enlist and explain the primary reasons for using randomized algorithms.**

### Definition
A randomized algorithm uses random numbers or random choices during its execution to make decisions.

Its behaviour or running time may vary even for the same input.

### Types

1. Las Vegas algorithm:
   - Always produces a correct result.
   - Running time may vary.
   - Example: Randomized Quick Sort.

2. Monte Carlo algorithm:
   - Runs within a specified time bound.
   - May produce an incorrect result with a small probability.
   - Example: Certain randomized primality tests.

### Reasons for using randomized algorithms
1. Simplicity: Random choices can simplify algorithm design.
2. Avoid worst-case input patterns: Randomization reduces dependence on a particular input order.
3. Expected efficiency: It can provide good expected running time.
4. Symmetry breaking: Random choices help distributed processes or parallel tasks make independent decisions.
5. Robustness: Performance is less dependent on specially constructed inputs.
6. Practical performance: Randomized algorithms are often efficient for large inputs.

### Example: Randomized Quick Sort
Randomized Quick Sort selects a pivot randomly instead of always selecting the first or last element.

- Expected time complexity: O(n log n).
- Worst-case time complexity: O(n^2).
- Recursion space: Expected O(log n), worst O(n).

Randomization improves expected performance but does not eliminate the theoretical worst case.

### Conclusion
Randomized algorithms use random choices to improve expected efficiency, reduce input sensitivity and simplify algorithm design.

---

## 9. Does randomized Quick Sort improve average-case time complexity? Discuss. [4 Marks]

**Q. Does randomized algorithm for Quick Sort improve the average-case time complexity? Discuss.**

### Explanation
In ordinary Quick Sort, the pivot may be selected as the first or last element. If the input is already sorted or has an unfavourable order, partitions may become highly unbalanced.

Randomized Quick Sort selects the pivot randomly.

### Working
1. Select a pivot randomly from the current subarray.
2. Partition the array around the pivot.
3. Recursively sort the left and right subarrays.

### Complexity

| Case | Time complexity |
|---|---|
| Expected / average | O(n log n) |
| Worst case | O(n^2) |

### Conclusion
Randomized Quick Sort reduces the chance of consistently unbalanced partitions and provides expected O(n log n) running time. It does not improve the asymptotic expected bound beyond O(n log n), but makes performance less dependent on the original input arrangement.

---

## 10. What are approximation algorithms? Explain performance ratio and its use. [7–9 Marks]

**Q. What is an approximation algorithm? How is the performance ratio useful in approximation algorithms?**

### Definition
An approximation algorithm is an algorithm that finds a near-optimal solution to an optimization problem in polynomial time, especially when finding an exact optimal solution is computationally expensive.

It is commonly used for NP-hard optimization problems.

### Need for approximation algorithms
- Exact algorithms may require exponential time.
- Large real-world inputs need practical solutions.
- A solution close to optimal may be sufficient.
- The algorithm should provide a measurable quality guarantee.

### Performance ratio
The performance ratio measures how close the approximate solution is to the optimal solution.

For a minimization problem:

Performance ratio = Approximate solution cost / Optimal solution cost

For a maximization problem:

Performance ratio = Optimal solution value / Approximate solution value

A ratio of 1 means the solution is optimal. A ratio close to 1 indicates a better approximation.

### Classification based on approximation ratio
1. Constant-factor approximation: The ratio is bounded by a fixed constant, such as 2.
2. Logarithmic approximation: The ratio grows proportionally to O(log n).
3. Polynomial-time approximation scheme (PTAS): For any fixed ε > 0, produces a solution within a factor of (1 + ε) for minimization, in polynomial time for fixed ε.
4. Fully polynomial-time approximation scheme (FPTAS): Runs in polynomial time in both input size and 1/ε.

### Example
For a minimization problem:
- Optimal cost = 100.
- Approximate algorithm cost = 110.

Performance ratio = 110 / 100 = 1.1

Therefore, the approximate solution is within a factor of 1.1 of the optimum.

### Uses
- Compares solution quality.
- Provides a mathematical guarantee.
- Helps select among approximation algorithms.
- Makes difficult optimization problems practically solvable.

### Conclusion
Approximation algorithms trade exact optimality for efficient computation. The performance ratio gives a formal measure of the quality of the obtained solution.

---

## 11. What are embedded algorithms? Explain their characteristics. [Syllabus-based]

**Q. Explain embedded algorithms and their important characteristics.**

### Definition
An embedded algorithm is an algorithm designed to run inside an embedded system, which is a dedicated computing device built to perform a specific function.

Examples include medical monitors, vehicle controllers, smart appliances and industrial controllers.

### Characteristics
1. Real-time response: Must complete operations within required deadlines.
2. Limited memory: RAM and storage are often restricted.
3. Low power consumption: Must operate efficiently on limited battery or power.
4. Reliability: Failure may affect safety or system operation.
5. Predictable execution: Execution time should be bounded and consistent.
6. Hardware awareness: Algorithm should consider processor, sensors and available peripherals.
7. Small code size: Limited program memory requires compact implementation.

### Design considerations
- Select suitable data structures.
- Avoid unnecessary memory allocation.
- Reduce computational complexity.
- Prefer predictable execution time.
- Minimize data movement and energy consumption.
- Handle sensor errors and exceptional conditions.

### Applications
- Medical monitoring devices.
- Automotive control systems.
- Smart meters.
- Industrial automation.
- IoT devices.

### Conclusion
Embedded algorithms must balance speed, memory, power, reliability and real-time constraints rather than optimizing only execution time.

---

## 12. Explain power-optimized scheduling algorithms for embedded systems. [Syllabus-based]

**Q. Explain power-optimized scheduling algorithms for embedded systems.**

### Introduction
Power-optimized scheduling assigns tasks to a processor in a way that meets timing deadlines while reducing energy consumption.

Embedded systems often operate on batteries and have limited power resources.

### Important concepts
- Task: A unit of work to be executed.
- Deadline: Latest time by which a task must finish.
- Execution time: Processor time required by the task.
- Energy: Power consumed while executing the task.
- Idle state: Processor state in which it performs no task.

### Common scheduling approaches

1. Earliest Deadline First (EDF):
   - Select the ready task with the nearest deadline.
   - It is a dynamic-priority scheduling algorithm.
   - For independent preemptible tasks on a single processor, EDF can schedule a feasible task set when total utilization is at most 1 under the standard ideal assumptions.

2. Rate Monotonic Scheduling (RMS):
   - Assign higher priority to tasks with shorter periods.
   - It is a fixed-priority scheduling algorithm.
   - Useful for periodic tasks.

3. Dynamic Voltage and Frequency Scaling (DVFS):
   - Reduce processor frequency and voltage when full speed is not required.
   - This can reduce dynamic power, but execution time increases.
   - Must ensure that all deadlines are still met.

4. Sleep / idle-state scheduling:
   - Put the processor into a low-power state when no task is ready.
   - Wake it before the next required execution.

### General procedure
1. Identify tasks, execution times and deadlines.
2. Check whether all deadlines can be satisfied.
3. Select a scheduling policy such as EDF or RMS.
4. Identify idle intervals.
5. Apply DVFS or sleep states where safe.
6. Verify deadline satisfaction and total energy use.

### Illustrative schedule

| Time interval | Activity |
|---|---|
| 0–2 | Execute high-priority task T1 |
| 2–5 | Execute task T2 at reduced frequency if deadline permits |
| 5–6 | Processor idle / low-power state |
| 6–8 | Execute next ready task |

This is an illustrative schedule; actual scheduling depends on the task set and timing constraints.

### Advantages
- Reduces battery consumption.
- Increases operating life.
- Reduces heat generation.
- Supports real-time operation.
- Improves energy efficiency.

### Conclusion
Power-optimized scheduling combines task priorities, deadline checks, processor speed control and low-power states to reduce energy while preserving real-time correctness.

---

## 13. Suggest a suitable sorting algorithm for a medical embedded system that processes sensor readings in real time. Justify your choice. [9 Marks]

**Q. Suppose you are working on an embedded system for a medical device that monitors patient vital signs. The device continuously collects data from various sensors and needs to process and display this information in real time. The data includes timestamps, temperature readings, heart rate and blood pressure measurements. Suggest a suitable sorting algorithm for this scenario. Clearly justify your answer with respect to key factors.**

### Requirements
The medical device has to sort sensor readings while considering:
- Real-time response.
- Limited memory.
- Continuous data arrival.
- Stability of records.
- Predictable execution time.
- Low power consumption.
- Correct ordering of timestamps and readings.

### Suitable choice: Heap Sort for bounded batches, or Insertion Sort for small batches
For a general bounded batch of sensor records, Heap Sort is a suitable choice when worst-case O(n log n) time and O(1) auxiliary array space are important.

For very small batches or nearly sorted incoming data, Insertion Sort may be more suitable due to its simplicity and low overhead. The choice depends on the maximum batch size and deadline.

### Heap Sort working
1. Build a max heap from the input records.
2. Swap the root (largest item) with the last item.
3. Reduce the heap size by one.
4. Heapify the root.
5. Repeat until all records are sorted.

For ascending order, a max heap is used.

### Complexity comparison

| Algorithm | Time complexity | Auxiliary space | Suitability |
|---|---|---|---|
| Insertion Sort | Best O(n), worst O(n^2) | O(1) | Small or nearly sorted batches |
| Heap Sort | O(n log n) in all cases | O(1) | Bounded batches needing worst-case time guarantee |
| Merge Sort | O(n log n) | O(n) | Stable sorting when extra memory is available |
| Quick Sort | Average O(n log n), worst O(n^2) | Recursion stack | Less suitable when strict worst-case bounds are required |

### Justification
- Predictable worst-case time: Heap Sort guarantees O(n log n).
- Low memory: It sorts in place and requires O(1) auxiliary array space.
- Bounded execution: A known maximum batch size helps estimate a deadline budget.
- Power: Avoiding extra memory movement can help, though actual energy depends on hardware.
- Stability: Heap Sort is not stable. If equal timestamps must retain arrival order, use a stable method such as Merge Sort, provided memory is available, or include a sequence number as a tie-breaker.

### Conclusion
Heap Sort is a practical default for bounded batches when worst-case time and low auxiliary memory are priorities. For very small batches, Insertion Sort may be faster. The final selection must be validated against the device's real-time deadline, memory and stability requirements.

---

## 14. Explain the Cutting Stock Problem with a suitable example. [Syllabus case study]

**Q. Explain the Cutting Stock Problem with a suitable example.**

### Definition
The Cutting Stock Problem is an optimization problem in which large stock materials are cut into smaller required pieces while minimizing waste and satisfying the demand for each piece size.

It is commonly used in paper, steel, textile, glass and timber industries.

### Objective
Minimize the total raw material used or minimize the leftover waste while meeting all customer demands.

### Example
A factory has stock rolls of length 10 units. It must produce:

| Required piece length | Demand |
|---:|---:|
| 6 | 2 |
| 4 | 2 |
| 3 | 2 |

One feasible cutting plan is:

| Stock roll | Cutting pattern | Used length | Waste |
|---|---|---:|---:|
| 1 | 6 + 4 | 10 | 0 |
| 2 | 6 + 4 | 10 | 0 |
| 3 | 3 + 3 | 6 | 4 |

Total stock rolls used = 3  
Total material used = 26 units  
Total waste = 4 units

All demands are satisfied:
- Length 6: 2 pieces.
- Length 4: 2 pieces.
- Length 3: 2 pieces.

### Mathematical formulation
Let:
- L = length of one stock roll.
- li = required length of piece type i.
- di = demand for piece type i.
- xij = number of pieces of type i produced using cutting pattern j.
- yj = number of stock rolls cut using pattern j.

Each cutting pattern must satisfy:

Sum(li × xij) <= L

Demand constraints:

Sum(xij × yj) >= di, for every piece type i

Objective:

Minimize Sum(yj)

The exact integer programming formulation may use pattern variables and demand constraints; the above expresses the basic pattern-based model.

### Solution approaches
- Greedy heuristic: Select a feasible cutting pattern that uses stock efficiently.
- Dynamic programming: Useful for certain one-dimensional cutting variants.
- Integer Linear Programming: Can model pattern selection and demand constraints.
- Branch-and-Bound: Can search for an optimal integer solution using bounds and pruning.

### Applications
- Paper roll cutting.
- Steel rod cutting.
- Textile manufacturing.
- Glass sheet cutting.
- Timber industry.

### Conclusion
The Cutting Stock Problem aims to satisfy piece demands while minimizing the number of stock materials or total waste. Efficient cutting patterns reduce production cost and material loss.

---

## 15. Explain the relationship between the Cutting Stock Problem and optimization algorithms. [Syllabus-based]

**Q. Explain how optimization algorithms can be applied to the Cutting Stock Problem.**

### Explanation
The Cutting Stock Problem requires selecting cutting patterns to satisfy demand while minimizing raw material use or waste. It is a combinatorial optimization problem.

### Algorithmic approaches

1. Greedy approach:
   - Select a pattern that fills the stock length efficiently.
   - Easy to implement.
   - Does not always guarantee a global optimum.

2. Dynamic Programming:
   - Solves suitable one-dimensional cutting variants by considering smaller capacities.
   - Stores the best value for each capacity.
   - Useful when piece lengths and stock capacity are manageable.

3. Integer Programming:
   - Represents pattern counts as integer decision variables.
   - Minimizes the number of stock rolls subject to demand constraints.

4. Branch-and-Bound:
   - Explores candidate pattern combinations.
   - Uses lower and upper bounds to prune unpromising branches.
   - Can prove optimality when the search is completed.

### Evaluation criteria
- Number of stock units used.
- Total leftover waste.
- Demand satisfaction.
- Computational time.
- Number of cutting patterns.
- Manufacturing constraints such as kerf and machine limits.

### Conclusion
Greedy methods provide quick feasible plans, while Dynamic Programming and Branch-and-Bound can solve selected variants more systematically. The correct method depends on problem size and whether an optimal solution is required.

---

## 16. Explain the importance of sorting algorithms in embedded systems. [Syllabus-based]

**Q. Explain sorting algorithms for embedded systems and the factors affecting their selection.**

### Introduction
Sorting algorithms arrange data in a specific order. Embedded systems use sorting to organize sensor readings, timestamps, control events and measurement records.

### Factors affecting selection
1. Execution time: Must finish within the system deadline.
2. Memory usage: Embedded devices often have limited RAM.
3. Power consumption: Fewer operations and data transfers can reduce energy.
4. Stability: Equal-key records may need to preserve their original order.
5. Predictability: Worst-case execution time may be more important than average time.
6. Input size: Small batches may favour simple algorithms.
7. Data condition: Nearly sorted input may favour Insertion Sort.

### Common algorithms

| Algorithm | Time complexity | Extra space | Important property |
|---|---|---|---|
| Insertion Sort | Best O(n), worst O(n^2) | O(1) | Simple, good for small/nearly sorted data |
| Selection Sort | O(n^2) | O(1) | Limited number of swaps |
| Heap Sort | O(n log n) | O(1) | Worst-case bound, in-place, not stable |
| Merge Sort | O(n log n) | O(n) | Stable, predictable time |
| Quick Sort | Average O(n log n), worst O(n^2) | Recursion stack | Often fast, but worst-case bound is weaker |

### Conclusion
No single sorting algorithm is best for every embedded system. Selection depends on deadlines, input size, memory, power, stability and worst-case guarantees.

---

## 17. Explain the time-space trade-off and its importance in embedded-system algorithm design. [Syllabus-based]

**Q. Explain how time-space trade-off affects algorithm selection in embedded systems.**

### Explanation
Embedded systems have limited memory, processor speed and battery capacity. Therefore, an algorithm must balance execution time and memory consumption.

### Examples
- Lookup table: Uses extra ROM/RAM to reduce repeated calculations.
- In-place sorting: Saves auxiliary memory but may have different time or stability properties.
- Memoization: Stores intermediate results to avoid recomputation.
- Compression: Saves storage or communication energy but requires encoding and decoding time.

### Design decision
- If response time is critical and memory is available, store precomputed results.
- If memory is limited, prefer compact or in-place methods.
- If energy is critical, consider both processor computation and memory access.
- If a hard deadline exists, validate worst-case execution time.

### Conclusion
The time-space trade-off is important in embedded systems because algorithm selection must satisfy timing, memory, power and reliability constraints together.
