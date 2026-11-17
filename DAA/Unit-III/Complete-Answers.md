# Unit III — Complete Answers
## Greedy and Dynamic Programming Algorithmic Strategies

**Subject:** Design and Analysis of Algorithms (410241)  
**SPPU — Fourth Year Computer Engineering, 2019 Course**

---

## 1. Greedy Strategy: Principle, Control Abstraction and Time Analysis

- **Q. Explain the principle of Greedy method. Write its control abstraction and comment on the time complexity.**

### Definition
A greedy algorithm constructs a solution step by step by selecting the best available choice at each stage. It makes a locally optimal choice with the expectation that these choices will lead to a globally optimal solution.

### Principle
1. Divide the problem into a number of decision steps.
2. At each step, select the best feasible choice according to a selection rule.
3. Do not reconsider earlier choices.
4. Continue until a complete solution is obtained.

A greedy method gives an optimal solution when the problem satisfies the **greedy-choice property** and **optimal substructure**.

### Control abstraction

```text
Greedy(C)
{
    solution = empty

    while solution is not complete
    {
        x = select_best_candidate(C)

        C = C - {x}

        if feasible(solution, x)
            solution = solution union {x}
    }

    return solution
}
```

### Explanation
- **Candidate set:** Contains all available choices.
- **Selection function:** Selects the locally best candidate.
- **Feasibility function:** Checks whether adding the candidate violates constraints.
- **Objective function:** Measures the value or cost of the current solution.
- **Solution function:** Checks whether a complete solution has been formed.

### Time analysis
The time complexity depends on the candidate-selection and feasibility operations.

- If candidates are sorted first, sorting generally takes O(n log n).
- If each candidate is checked once and feasibility testing takes O(1), the scan takes O(n).
- If feasibility checking takes O(n), the total may become O(n²).

Therefore, the time complexity is problem-dependent. A common case with sorting and a linear scan takes O(n log n).

### Applications
- Fractional knapsack.
- Job sequencing with deadlines.
- Activity selection.
- Minimum spanning tree algorithms.

### Conclusion
Greedy algorithms are usually simple and efficient, but a locally optimal choice is not guaranteed to produce a global optimum for every problem.

---

## 2. Fractional Knapsack Using Greedy Method

- **Q. Explain the Greedy approach for solving the Fractional Knapsack problem with a suitable example.**

### Definition
In the Fractional Knapsack problem, items can be divided into fractions. The objective is to maximize the total profit without exceeding the knapsack capacity.

### Greedy principle
Calculate the profit-to-weight ratio of every item:

Profit/Weight ratio = Profit / Weight

Select items in decreasing order of this ratio. If the next item cannot fit completely, take only the required fraction.

### Algorithm

```text
FractionalKnapsack(items, capacity)
{
    for each item i
        ratio[i] = profit[i] / weight[i]

    sort items in decreasing order of ratio

    totalProfit = 0

    for each item i
    {
        if weight[i] <= capacity
        {
            take the complete item
            capacity = capacity - weight[i]
            totalProfit = totalProfit + profit[i]
        }
        else
        {
            fraction = capacity / weight[i]
            totalProfit = totalProfit + fraction * profit[i]
            break
        }
    }

    return totalProfit
}
```

### Example
Knapsack capacity = 50 units.

| Item | Weight | Profit | Profit/Weight |
|---|---:|---:|---:|
| I1 | 10 | 60 | 6 |
| I2 | 20 | 100 | 5 |
| I3 | 30 | 120 | 4 |

The decreasing ratio order is I1, I2, I3.

1. Select I1 completely: weight = 10, profit = 60. Remaining capacity = 40.
2. Select I2 completely: weight = 20, profit = 100. Remaining capacity = 20.
3. Only 20 units of I3 can be selected. Fraction = 20/30 = 2/3. Profit = 120 × 2/3 = 80.

Total profit = 60 + 100 + 80 = **240**.

### Complexity
- Calculating ratios: O(n).
- Sorting: O(n log n).
- Selecting items: O(n).
- Overall time complexity: O(n log n).
- Space complexity: O(n) when a separate sorted list is stored; sorting in place may use less auxiliary space depending on the sorting method.

### Conclusion
The greedy ratio method gives an optimal solution for fractional knapsack because taking a fraction of an item is allowed. It is not generally optimal for 0/1 knapsack.

---

## 3. Job Sequencing with Deadlines and Profits

- **Q. Explain Job Sequencing with Deadlines using the Greedy method. Find an optimal schedule for a suitable example.**

### Definition
Job sequencing with deadlines is a scheduling problem in which each job takes one unit of time and has a deadline and a profit. Profit is earned only when the job is completed on or before its deadline. The objective is to maximize total profit.

### Greedy principle
Sort jobs in decreasing order of profit. Schedule each job in the latest available time slot on or before its deadline. This keeps earlier slots free for jobs having smaller deadlines.

### Algorithm

```text
JobSequencing(jobs)
{
    sort jobs in decreasing order of profit
    maxDeadline = maximum deadline
    create slots[1 ... maxDeadline], initially empty

    for each job j in sorted order
    {
        for t = min(j.deadline, maxDeadline) down to 1
        {
            if slots[t] is empty
            {
                slots[t] = j
                break
            }
        }
    }

    return slots
}
```

### Example
Consider the following jobs:

| Job | Deadline | Profit |
|---|---:|---:|
| J1 | 2 | 100 |
| J2 | 1 | 19 |
| J3 | 2 | 27 |
| J4 | 1 | 25 |
| J5 | 3 | 15 |

Sort in decreasing order of profit: J1, J3, J4, J2, J5.

There are three available time slots.

| Job considered | Latest available slot | Decision |
|---|---:|---|
| J1 | 2 | Schedule J1 in slot 2 |
| J3 | 1 | Schedule J3 in slot 1 |
| J4 | No free slot on/before deadline 1 | Reject |
| J2 | No free slot on/before deadline 1 | Reject |
| J5 | 3 | Schedule J5 in slot 3 |

Final schedule:

| Time slot | 1 | 2 | 3 |
|---|---|---|---|
| Job | J3 | J1 | J5 |
| Profit | 27 | 100 | 15 |

Maximum profit = 27 + 100 + 15 = **142**.

### Complexity
Let n be the number of jobs and d be the maximum deadline.

- Sorting jobs: O(n log n).
- Slot search: O(nd) in the simple implementation.
- Overall time complexity: O(n log n + nd).
- Space complexity: O(d) for the slot array, excluding the input list.

### Conclusion
Job sequencing uses a greedy profit-based selection rule and schedules each accepted job as late as possible before its deadline.

---

## 4. Activity Selection Using Greedy Method

- **Q. Explain the Activity Selection problem and solve it using the Greedy approach with a suitable example.**

### Definition
The Activity Selection problem consists of activities with start and finish times. Only one activity can be performed at a time. The objective is to select the maximum number of mutually non-overlapping activities.

### Greedy principle
Select the activity that finishes earliest. This leaves the maximum possible time for the remaining activities.

### Algorithm

```text
ActivitySelection(activities)
{
    sort activities by increasing finish time

    select the first activity
    lastFinish = finish time of first activity

    for each remaining activity i
    {
        if start[i] >= lastFinish
        {
            select activity i
            lastFinish = finish[i]
        }
    }

    return selected activities
}
```

### Example
Consider the activities:

| Activity | Start | Finish |
|---|---:|---:|
| A1 | 1 | 3 |
| A2 | 2 | 5 |
| A3 | 4 | 6 |
| A4 | 6 | 7 |
| A5 | 5 | 8 |
| A6 | 8 | 9 |

The activities are already arranged in increasing order of finish time.

1. Select A1 (1, 3).
2. A2 starts at 2, which is less than 3; reject it.
3. A3 starts at 4, which is at least 3; select it.
4. A4 starts at 6, which is at least 6; select it.
5. A5 starts at 5, which is less than 7; reject it.
6. A6 starts at 8, which is at least 7; select it.

Selected activities: **A1, A3, A4, A6**.

Maximum number of non-conflicting activities = **4**.

### Complexity
- Sorting: O(n log n).
- Selection scan: O(n).
- Overall time complexity: O(n log n), or O(n) if the activities are already sorted by finish time.
- Auxiliary space: O(1) for the scan when sorting is in place and no separate result list is counted; O(n) if a separate selected list is stored.

### Conclusion
The earliest-finish-time greedy rule produces an optimal maximum-size set of compatible activities.

---

## 5. Dynamic Programming: Principle, Control Abstraction and Time Analysis

- **Q. Explain the Dynamic Programming approach. Write its control abstraction and comment on its time complexity.**

### Definition
Dynamic Programming (DP) is an algorithmic technique used to solve problems by dividing them into smaller overlapping subproblems, solving each subproblem once, and storing its result for future use.

### Principle
Dynamic programming is applicable when a problem has:

1. **Optimal substructure:** An optimal solution can be constructed from optimal solutions of smaller subproblems.
2. **Overlapping subproblems:** The same subproblems occur repeatedly.

DP stores intermediate results to avoid repeated calculations.

### Approaches
- **Memoization:** Top-down approach. Solve recursively and store computed results.
- **Tabulation:** Bottom-up approach. Solve smaller subproblems first and fill a table.

### Control abstraction

```text
DynamicProgramming(problem)
{
    identify the subproblems
    define the recurrence relation
    initialize base cases

    for each subproblem in dependency order
        compute its result using previously stored results

    return the result for the original problem
}
```

### Example: Fibonacci numbers
The recurrence is:

F(0) = 0  
F(1) = 1  
F(n) = F(n-1) + F(n-2), for n >= 2

Using tabulation, calculate F(0), F(1), and then each next value once.

| n | F(n) |
|---:|---:|
| 0 | 0 |
| 1 | 1 |
| 2 | 1 |
| 3 | 2 |
| 4 | 3 |
| 5 | 5 |
| 6 | 8 |

Thus, F(6) = 8.

### Time analysis
The time complexity depends on:
- Number of distinct subproblems.
- Time required to compute each subproblem after smaller results are available.

General idea:

Time complexity = Number of subproblems × Work per subproblem

For tabulated Fibonacci, there are O(n) subproblems and O(1) work per subproblem. Therefore, time complexity is O(n), and space complexity is O(n).

### Conclusion
Dynamic programming improves efficiency by storing and reusing solutions to overlapping subproblems.

---

## 6. Principle of Optimality / Optimal Substructure

- **Q. What is the Principle of Optimality in Dynamic Programming? Give its mathematical representation.**

### Definition
The Principle of Optimality states that an optimal solution to a problem contains optimal solutions to its subproblems, considering the state reached after each decision.

This property is also referred to as **optimal substructure**.

### Explanation
1. Divide the original problem into smaller subproblems.
2. Find optimal solutions to those subproblems.
3. Combine these solutions to obtain an optimal solution to the original problem.
4. Store the results to avoid solving the same subproblem repeatedly.

### Mathematical representation
For a problem with state i and decision k, the optimal value can be represented in the general form:

F(i) = min or max over valid decisions k of { cost(i, k) + F(next state after k) }

The exact recurrence depends on the problem.

For matrix-chain multiplication:

m[i, j] = min over i <= k < j of {m[i, k] + m[k+1, j] + p[i-1] × p[k] × p[j]}

Base case:

m[i, i] = 0

### Example
Suppose three matrices A1, A2 and A3 are to be multiplied. The complete chain can be divided into smaller chains. The optimal parenthesization is obtained by combining the best cost of the left subchain and the best cost of the right subchain, plus the cost of the final multiplication.

### Importance
- Helps identify whether DP can be applied.
- Allows a problem to be solved using smaller optimal subproblems.
- Forms the basis of matrix-chain multiplication, 0/1 knapsack and OBST.

### Conclusion
A problem that lacks the required optimal-substructure property cannot be solved by the standard DP recurrence based on that decomposition. The recurrence must correctly represent the problem's states and decisions.

---

## 7. Binomial Coefficients Using Dynamic Programming

- **Q. Explain how binomial coefficients are calculated using Dynamic Programming with a suitable example.**

### Definition
A binomial coefficient C(n, r) represents the number of ways to select r objects from n distinct objects, without considering order.

### Recurrence relation
The recurrence is based on Pascal's identity:

C(n, r) = C(n-1, r-1) + C(n-1, r)

Base conditions:

C(n, 0) = 1  
C(n, n) = 1

### Algorithm

```text
BinomialCoefficient(n, r)
{
    create table C[0 ... n][0 ... r]

    for i = 0 to n
    {
        for j = 0 to min(i, r)
        {
            if j == 0 or j == i
                C[i][j] = 1
            else
                C[i][j] = C[i-1][j-1] + C[i-1][j]
        }
    }

    return C[n][r]
}
```

### Example: Find C(5, 2)

Using Pascal's identity:

C(5, 2) = C(4, 1) + C(4, 2)  
= 4 + 6  
= **10**

Relevant DP table:

| n | C(n,0) | C(n,1) | C(n,2) |
|---:|---:|---:|---:|
| 0 | 1 | - | - |
| 1 | 1 | 1 | - |
| 2 | 1 | 2 | 1 |
| 3 | 1 | 3 | 3 |
| 4 | 1 | 4 | 6 |
| 5 | 1 | 5 | 10 |

### Complexity
For a table up to n and r:
- Time complexity: O(nr).
- Space complexity: O(nr).
A one-dimensional optimized implementation can reduce space to O(r).

### Conclusion
Dynamic programming calculates binomial coefficients efficiently by reusing previously computed values instead of repeatedly evaluating the recursive formula.

---

## 8. Optimal Binary Search Tree (OBST) Using Dynamic Programming

- **Q. Explain the Optimal Binary Search Tree problem and solve it using Dynamic Programming with a suitable example.**

### Definition
An Optimal Binary Search Tree (OBST) is a binary search tree arranged so that the expected or weighted search cost is minimum, based on the search frequencies or probabilities of keys.

A key searched more frequently should generally be placed closer to the root.

### Recurrence for successful-search frequencies
Let f[i] be the frequency of key i.

W[i, j] = sum of frequencies from i to j.

C[i, j] = minimum cost of an optimal BST containing keys i through j.

C[i, j] = min over i <= r <= j of {C[i, r-1] + C[r+1, j] + W[i, j]}

Base case:

C[i, i-1] = 0

This recurrence assumes only successful-search frequencies. If unsuccessful-search probabilities are included, dummy keys and the corresponding OBST recurrence are required.

### Algorithm

```text
OBST(frequency[1 ... n])
{
    for i = 1 to n+1
        cost[i][i-1] = 0

    for length = 1 to n
    {
        for i = 1 to n-length+1
        {
            j = i + length - 1
            weight[i][j] = sum of frequency[i ... j]
            cost[i][j] = infinity

            for r = i to j
            {
                value = cost[i][r-1]
                      + cost[r+1][j]
                      + weight[i][j]

                if value < cost[i][j]
                    cost[i][j] = value
                    root[i][j] = r
            }
        }
    }

    return cost[1][n] and root[1][n]
}
```

### Example
Keys = 10, 20, 30  
Frequencies = 3, 3, 1

Try key 20 as root:
- Key 10 is the left child.
- Key 30 is the right child.

Weighted search cost:

Key 20: 3 × 1 = 3  
Key 10: 3 × 2 = 6  
Key 30: 1 × 2 = 2  

Total cost = 3 + 6 + 2 = **11**.

If key 10 is the root, the cost is 3 × 1 + 3 × 2 + 1 × 3 = 12. If key 30 is the root, the cost is 1 × 1 + 3 × 2 + 3 × 3 = 16.

Therefore, the optimal root is key 20 and the minimum weighted search cost is **11**.

### Complexity
- Time complexity: O(n³) for the standard interval DP recurrence.
- Space complexity: O(n²) for cost, weight and root tables.

### Conclusion
OBST uses dynamic programming to select the root of each key interval so that the total weighted search cost is minimum.

---

## 9. 0/1 Knapsack Using Dynamic Programming

- **Q. Explain the 0/1 Knapsack problem and solve it using Dynamic Programming with a suitable example.**

### Definition
In the 0/1 Knapsack problem, each item has a weight and profit. An item must either be selected completely or rejected; fractions are not allowed. The objective is to maximize total profit without exceeding the capacity.

### Recurrence relation
Let DP[i][w] represent the maximum profit using the first i items with capacity w.

If item i is too heavy:

DP[i][w] = DP[i-1][w]

Otherwise:

DP[i][w] = max(DP[i-1][w], profit[i] + DP[i-1][w-weight[i]])

Base conditions:

DP[0][w] = 0  
DP[i][0] = 0

### Algorithm

```text
Knapsack(weights, profits, n, W)
{
    create DP[0 ... n][0 ... W]

    for i = 0 to n
    {
        for w = 0 to W
        {
            if i == 0 or w == 0
                DP[i][w] = 0
            else if weights[i] <= w
                DP[i][w] = max(
                    DP[i-1][w],
                    profits[i] + DP[i-1][w-weights[i]]
                )
            else
                DP[i][w] = DP[i-1][w]
        }
    }

    return DP[n][W]
}
```

### Example
Capacity W = 5.

| Item | Weight | Profit |
|---|---:|---:|
| I1 | 2 | 12 |
| I2 | 1 | 10 |
| I3 | 3 | 20 |
| I4 | 2 | 15 |

The important DP table entries are:

| Items considered | Capacity 0 | 1 | 2 | 3 | 4 | 5 |
|---|---:|---:|---:|---:|---:|---:|
| None | 0 | 0 | 0 | 0 | 0 | 0 |
| I1 | 0 | 0 | 12 | 12 | 12 | 12 |
| I1, I2 | 0 | 10 | 12 | 22 | 22 | 22 |
| I1, I2, I3 | 0 | 10 | 12 | 22 | 30 | 32 |
| I1, I2, I3, I4 | 0 | 10 | 15 | 25 | 30 | 37 |

The maximum profit is DP[4][5] = **37**.

Selected items:
- I1: weight 2, profit 12.
- I2: weight 1, profit 10.
- I4: weight 2, profit 15.

Total weight = 2 + 1 + 2 = 5.  
Total profit = 12 + 10 + 15 = **37**.

### Complexity
- Time complexity: O(nW).
- Space complexity: O(nW).
This is pseudo-polynomial because it depends on the numeric capacity W, not only on the number of input items.

### Conclusion
Dynamic programming checks both the include and exclude choices for each item and finds the optimal 0/1 knapsack profit.

---

## 10. Matrix Chain Multiplication Using Dynamic Programming

- **Q. Explain Matrix Chain Multiplication using Dynamic Programming with a suitable example.**

### Definition
Matrix Chain Multiplication determines the best order of multiplying a sequence of matrices. The order of matrices cannot be changed, but their parenthesization can be changed to minimize the number of scalar multiplications.

### Recurrence relation
Let matrix Ai have dimensions p[i-1] × p[i].

m[i, j] = minimum number of scalar multiplications needed to multiply matrices Ai through Aj.

Base condition:

m[i, i] = 0

Recurrence:

m[i, j] = min over i <= k < j of {
m[i, k] + m[k+1, j] + p[i-1] × p[k] × p[j]
}

### Algorithm

```text
MatrixChain(p, n)
{
    for i = 1 to n
        m[i][i] = 0

    for length = 2 to n
    {
        for i = 1 to n-length+1
        {
            j = i + length - 1
            m[i][j] = infinity

            for k = i to j-1
            {
                q = m[i][k] + m[k+1][j]
                    + p[i-1] * p[k] * p[j]

                if q < m[i][j]
                {
                    m[i][j] = q
                    split[i][j] = k
                }
            }
        }
    }

    return m[1][n]
}
```

### Example
Three matrices have dimensions:

- A1 = 10 × 30
- A2 = 30 × 5
- A3 = 5 × 60

Two possible parenthesizations are:

**Option 1: (A1 × A2) × A3**

Cost of A1 × A2 = 10 × 30 × 5 = 1500.  
Resulting matrix has dimensions 10 × 5.

Cost of multiplying the result by A3 = 10 × 5 × 60 = 3000.

Total cost = 1500 + 3000 = **4500**.

**Option 2: A1 × (A2 × A3)**

Cost of A2 × A3 = 30 × 5 × 60 = 9000.  
Resulting matrix has dimensions 30 × 60.

Cost of multiplying A1 by the result = 10 × 30 × 60 = 18000.

Total cost = 9000 + 18000 = **27000**.

Therefore, the optimal order is **(A1 × A2) × A3**, requiring **4500 scalar multiplications**.

### Complexity
- Time complexity: O(n³).
- Space complexity: O(n²).

### Conclusion
Matrix-chain multiplication uses dynamic programming to find the parenthesization with the minimum number of scalar multiplications.

---

## 11. Comparison Between Greedy Method and Dynamic Programming

- **Q. Compare Greedy method and Dynamic Programming with respect to feasibility, optimality, recursion, memorization and time complexity.**

| Basis | Greedy Method | Dynamic Programming |
|---|---|---|
| Feasibility | Selects a locally best feasible choice at each step | Solves defined subproblems while respecting constraints |
| Optimality | Optimal only when greedy-choice property and optimal substructure hold | Finds an optimum when the recurrence correctly captures optimal substructure |
| Decision | Makes a choice and generally does not reconsider it | Compares alternatives through recurrence relations |
| Subproblems | Does not necessarily solve overlapping subproblems | Uses overlapping subproblems |
| Memorization | Usually does not store subproblem results | Stores results using memoization or tabulation |
| Implementation | Often iterative and simple | Often table-based or recursive with memoization |
| Time complexity | Often lower, depending on sorting and selection | Depends on number of states and work per state; may use more time and memory |
| Examples | Fractional knapsack, activity selection, job sequencing | 0/1 knapsack, OBST, matrix-chain multiplication |

### Example
- **Fractional knapsack:** Greedy selection by profit/weight ratio is optimal because fractions of items are allowed.
- **0/1 knapsack:** The same greedy ratio rule is not guaranteed to be optimal because each item must be taken completely or rejected. DP considers both choices.

### Conclusion
Greedy is generally simpler and faster when its selection rule is provably optimal. Dynamic programming is suitable when decisions must be compared across overlapping subproblems.

---

## 12. Time Analysis of Greedy and Dynamic Programming Control Abstractions

- **Q. Explain the time analysis of Greedy and Dynamic Programming control abstractions.**

### Greedy control abstraction
A greedy algorithm commonly performs candidate selection, feasibility testing and solution updating.

If candidates are sorted first:
- Sorting: O(n log n).
- Candidate scan: O(n).
- Feasibility checks: depends on the problem.

For constant-time feasibility checks, the overall time is O(n log n). If each feasibility check takes O(n), the total can be O(n²) after sorting.

### Dynamic programming control abstraction
A DP algorithm:
1. Defines states/subproblems.
2. Initializes base cases.
3. Evaluates each state in dependency order.
4. Stores the result.
5. Returns the state representing the original problem.

General analysis:

Time = Number of states × Work per state

Examples:

| Problem | Number of states / work | Time complexity |
|---|---|---|
| Binomial coefficient table | O(nr) entries, O(1) work each | O(nr) |
| 0/1 Knapsack | O(nW) states, O(1) work each | O(nW) |
| Matrix-chain multiplication | O(n²) intervals, O(n) split points | O(n³) |
| OBST | O(n²) intervals, O(n) root choices | O(n³) |

### Conclusion
Greedy complexity is mainly determined by sorting, selection and feasibility checks. Dynamic programming complexity is determined by the number of states and the work required to compute each state.

---

## 13. Case Study: Rail Tracks Connecting All the Cities Using Greedy Method

- **Q. Explain the case study of connecting all the cities using rail tracks. How can a Greedy algorithm be used to find the minimum cost of connecting all cities?**

### Introduction
Consider a railway department that wants to connect a number of cities by laying railway tracks. The cost of laying a track between two cities may differ because of distance, land conditions and construction requirements.

The objective is to connect every city so that:
1. Every city is reachable from every other city.
2. The total construction cost is minimum.
3. Unnecessary track connections and cycles are avoided.

This problem can be represented using a **weighted, undirected graph**:
- Each city is represented by a vertex.
- A possible railway track between two cities is represented by an edge.
- The construction cost of that track is the edge weight.

The required solution is a **Minimum Spanning Tree (MST)**. This is the standard graph interpretation of the stated case study: a minimum-cost set of tracks that connects all cities.

### Greedy approach — Kruskal's algorithm
Kruskal's algorithm selects railway connections in increasing order of construction cost. An edge is selected only if it does not form a cycle with the already selected edges.

### Algorithm

```text
Kruskal(G)
{
    MST = empty set

    sort all edges in increasing order of weight

    for each vertex v
        make a separate set containing v

    for each edge (u, v) in sorted order
    {
        if Find(u) != Find(v)
        {
            add (u, v) to MST
            Union(u, v)
        }

        if MST contains V - 1 edges
            break
    }

    return MST
}
```

Here, Find checks whether two cities are already connected, and Union combines their sets. These operations help avoid cycles.

### Example
Suppose five cities A, B, C, D and E are to be connected. The possible railway tracks and their construction costs are:

| Track | Construction cost |
|---|---:|
| A-B | 4 |
| A-C | 2 |
| B-C | 1 |
| B-D | 5 |
| C-D | 8 |
| C-E | 10 |
| D-E | 2 |
| B-E | 6 |

**Step 1: Sort the tracks in increasing order of cost.**

B-C (1), A-C (2), D-E (2), A-B (4), B-D (5), B-E (6), C-D (8), C-E (10).

**Step 2: Select tracks without forming a cycle.**

| Track considered | Cost | Decision | Reason |
|---|---:|---|---|
| B-C | 1 | Select | Connects two separate components |
| A-C | 2 | Select | Connects city A to the existing component |
| D-E | 2 | Select | Connects two separate cities |
| A-B | 4 | Reject | Forms a cycle among A, B and C |
| B-D | 5 | Select | Connects the two remaining components |
| B-E | 6 | Stop / not needed | All cities are already connected |

**Step 3: Final minimum spanning tree.**

Selected tracks: B-C, A-C, D-E and B-D.

Total minimum construction cost:

= 1 + 2 + 2 + 5

= **10 cost units**

All five cities are connected using four tracks. A spanning tree with V cities always contains V - 1 edges.

### Result
The railway department should construct the tracks B-C, A-C, D-E and B-D. This connects all five cities with minimum total cost of **10 cost units**.

### Time and space complexity
Let V be the number of cities and E be the number of possible railway connections.

- Sorting all edges: O(E log E).
- Disjoint-set Find/Union operations: nearly O(1) amortized per operation with path compression and union by rank.
- Overall time complexity: O(E log E).
- Space complexity: O(V) for the disjoint-set structure, excluding the graph and edge list; storing the graph requires O(V + E).

### Other Greedy method
Prim's algorithm can also find a minimum spanning tree. It starts from any one city and repeatedly adds the minimum-cost edge that connects a city already in the tree to a city outside it.

### Applications
- Connecting cities through railway tracks.
- Designing road and highway networks.
- Connecting computers in a communication network.
- Laying minimum-cost electrical or telephone cables.

### Conclusion
The rail-track case study can be modelled as a Minimum Spanning Tree problem. Kruskal's greedy algorithm selects the lowest-cost connections without creating cycles and connects all cities with minimum total construction cost.

