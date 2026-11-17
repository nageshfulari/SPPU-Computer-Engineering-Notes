# Unit V — Quick Revision
## Amortized Analysis | DAA (410241)

## 1. Amortized Analysis
- Analyzes the cost of a sequence of operations.
- Gives a guaranteed bound over every valid sequence.
- Does not use probability.
- Different from average-case analysis.

### Three methods

| Method | Main idea | Formula / rule |
|---|---|---|
| Aggregate | Total sequence cost divided by number of operations | Amortized cost = T(n) / n |
| Accounting | Charge extra and store credit for future expensive operations | Credit must never become negative |
| Potential | Measure stored work using a potential function | ĉi = ci + Φ(Di) - Φ(Di-1) |

## 2. k-bit Binary Counter
- Bit 0 flips at most n times.
- Bit 1 flips at most n/2 times.
- Bit i flips at most n/2^i times.

Total flips:
T(n) <= n + n/2 + n/4 + ... < 2n

Amortized cost per increment < 2 = O(1).

Accounting method: charge 2 units per increment; one unit pays for 0-to-1 and one is stored to pay for the later 1-to-0 flip.

## 3. Stack Amortized Analysis
- PUSH actual cost = 1.
- POP actual cost = 1 if non-empty.
- MULTIPOP(k) actual cost = min(k, current stack size).
- Every element is pushed once and popped at most once.
- Total cost of n operations <= 2n.
- Amortized cost per operation = O(1).

Accounting charges:
- PUSH = 2.
- POP = 0.
- MULTIPOP = 0.
One credit is stored on every pushed element and pays for its removal.

## 4. Time-Space Trade-off
- More memory may reduce execution time.
- Less memory may require recomputation or extra processing.
- Examples: hash tables, lookup tables, memoization, in-place sorting, compression.

## 5. Tractable and Intractable Problems

| Tractable | Intractable |
|---|---|
| Polynomial-time solution | No polynomial-time exact solution known for general instances of many such problems |
| Examples: sorting, binary search, MST | Examples: TSP optimization, general 0/1 Knapsack optimization |

Remember:
- P: polynomial-time solvable decision problems.
- NP: proposed solutions verifiable in polynomial time.
- NP-hard: at least as hard as all problems in NP.
- NP-complete: both NP and NP-hard.
- It is not proved that P ≠ NP.

## 6. Randomized Algorithms
- Use random choices during execution.
- Las Vegas: always correct; running time varies.
- Monte Carlo: bounded running time; small error probability may exist.
- Randomized Quick Sort: expected O(n log n), worst O(n^2).

## 7. Approximation Algorithms
For minimization:
Performance ratio = Approximate cost / Optimal cost

For maximization:
Performance ratio = Optimal value / Approximate value

- Ratio 1 means optimal.
- Constant-factor approximation: bounded by a constant.
- PTAS: (1 + ε) approximation for fixed ε in polynomial time.
- FPTAS: polynomial in input size and 1/ε.

## 8. Embedded Algorithms
Design for:
- Real-time deadlines.
- Limited RAM/ROM.
- Low energy use.
- Predictable execution time.
- Reliability and hardware constraints.

## 9. Power-Optimized Scheduling
- EDF: task with earliest deadline first.
- RMS: shorter-period task gets higher fixed priority.
- DVFS: lower voltage/frequency to reduce energy if deadlines remain feasible.
- Sleep/idle state: reduce power when no task is ready.

## 10. Sorting for Embedded Systems

| Algorithm | Time | Extra space | Key point |
|---|---|---|---|
| Insertion | Best O(n), worst O(n²) | O(1) | Small/nearly sorted input |
| Selection | O(n²) | O(1) | Few swaps |
| Heap | O(n log n) | O(1) | Worst-case bound; not stable |
| Merge | O(n log n) | O(n) | Stable |
| Quick | Average O(n log n), worst O(n²) | Recursion stack | Fast in practice; weaker worst-case |

## 11. Cutting Stock Problem
- Cut large stock material into smaller demanded pieces.
- Objective: minimize number of stock units or total waste.
- Constraints: each pattern must fit stock length; all demands must be satisfied.
- Applications: paper, steel, textile, glass, timber.
- Approaches: Greedy heuristics, DP for selected variants, Integer Programming, Branch-and-Bound.

## Must-remember formulas
- Amortized cost (potential): amortized_cost_i = actual_cost_i + Φ(Di) - Φ(Di-1)
- Aggregate counter cost: T(n) < 2n
- Counter amortized increment: O(1)
- Stack total cost: O(n) for n operations
- Randomized Quick Sort expected: O(n log n)
- Randomized Quick Sort worst: O(n²)
- Heap Sort: O(n log n) worst case
- Merge Sort: O(n log n) time, O(n) extra space
