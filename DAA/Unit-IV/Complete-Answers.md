# Unit IV — Complete Answers
## Backtracking and Branch-and-Bound

**Subject:** Design and Analysis of Algorithms (410241)  
**SPPU — Fourth Year Computer Engineering, 2019 Course**

---

## 1. Backtracking: Principle, Control Abstraction and Time Analysis

- **Q. Explain with a suitable example Backtracking: Principle, control abstraction and time analysis of control abstraction.**

### Definition
Backtracking is an algorithmic technique that constructs a solution step by step. Whenever a partial solution violates a constraint or cannot lead to a valid complete solution, the algorithm abandons that partial solution and returns to an earlier decision.

### Principle
1. Represent possible solutions as a state-space tree.
2. Start from the root and explore choices in depth-first order.
3. Check whether the current partial solution is promising.
4. If it is promising, continue to the next level.
5. If it is not promising, reject that branch and backtrack.
6. Stop when a required solution or all solutions are found.

### Important terms
- **State-space tree:** Represents all possible choices and partial solutions.
- **Promising node:** A node that may lead to a valid solution.
- **Non-promising node:** A node that violates constraints or cannot lead to a solution.
- **Backtracking:** Returning to the previous decision point to try another choice.

### Control abstraction

~~~text
Backtrack(k)
{
    if k represents a complete solution
        output solution
    else
    {
        for each candidate x at level k
        {
            include x in the current solution

            if promising(current solution)
                Backtrack(k + 1)

            remove x from the current solution
        }
    }
}
~~~

### Example: N-Queen problem
Place N queens on an N × N chessboard so that no two queens attack each other.

A queen attacks along the same row, column and diagonal. Place one queen in each row. For every row, try each column and accept a position only if:
- No previously placed queen is in the same column.
- No previously placed queen is on the same diagonal.

If no column is safe, remove the queen from the previous row and try its next available column. This is backtracking.

### Time analysis
The time complexity depends on the number of nodes explored in the state-space tree and the work required to test whether a node is promising.

For a general tree with branching factor b and depth d, the worst-case number of nodes is O(b^d), excluding the cost of the promising test.

Examples:
- N-Queen: a simple row-by-row search has at most O(N!) candidate arrangements when columns are chosen without repetition; checking safety adds work depending on implementation.
- M-Coloring: at most O(m^n) assignments for n vertices and m colors.
- Sum of Subsets: at most O(2^n) include/exclude combinations.

Backtracking can still have exponential worst-case time, but pruning avoids exploring many invalid branches in practice.

### Conclusion
Backtracking explores a state-space tree using depth-first search and rejects non-promising partial solutions. Its efficiency depends on how effectively invalid branches are pruned.

---

## 2. 8-Queen Problem Using Backtracking

- **Q. Explain the 8-Queen problem and solve it using Backtracking.**

### Definition
The 8-Queen problem is to place eight queens on an 8 × 8 chessboard such that no two queens attack each other.

### Constraints
For any two queens placed at (row[i], column[i]) and (row[j], column[j]):
1. They must not be in the same column: column[i] != column[j].
2. They must not be on the same diagonal: |column[i] - column[j]| != |i - j|.
3. One queen is placed in each row, so row conflict is avoided automatically.

### Backtracking approach
- Place one queen in each row.
- Try columns from 1 to 8.
- Check whether the selected position is safe.
- If safe, place the queen and move to the next row.
- If no column is safe, remove the previous queen and try another column.
- When all eight rows are filled, a solution is found.

### Algorithm

~~~text
NQueen(row)
{
    if row > 8
    {
        print solution
        return
    }

    for col = 1 to 8
    {
        if Safe(row, col)
        {
            position[row] = col
            NQueen(row + 1)
        }
    }
}

Safe(row, col)
{
    for i = 1 to row - 1
    {
        if position[i] == col
            return false

        if abs(position[i] - col) == abs(i - row)
            return false
    }

    return true
}
~~~

### One valid solution
A valid arrangement, where the value at each index gives the column of the queen in that row, is:

| Row | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Column | 1 | 5 | 8 | 6 | 3 | 7 | 2 | 4 |

Thus, the queen positions are:
(1,1), (2,5), (3,8), (4,6), (5,3), (6,7), (7,2), (8,4).

No two queens share a column or diagonal.

### Complexity
- Worst-case search is exponential.
- A common upper bound for row-by-row placement with distinct columns is O(N!); the safety check can take O(N), giving a straightforward upper bound of O(N × N!).
- Space complexity: O(N) for the position array and recursion stack, excluding output storage.

### Conclusion
The 8-Queen problem is solved by placing queens row by row and backtracking whenever a column or diagonal conflict occurs.

---

## 3. Graph Coloring Using Backtracking

- **Q. Explain Graph Coloring using Backtracking and find a solution for a given graph.**

### Definition
Graph coloring assigns colors to the vertices of a graph so that no two adjacent vertices have the same color. The M-Coloring problem asks whether a graph can be colored using at most m colors.

### Conditions
For every edge (u, v):
color[u] != color[v]

### Backtracking approach
1. Consider vertices one by one.
2. Assign a color from 1 to m.
3. Check whether any already-colored adjacent vertex has the same color.
4. If the color is safe, move to the next vertex.
5. If no color is safe, remove the previous assignment and try another color.
6. If all vertices are colored, a valid coloring is obtained.

### Algorithm

~~~text
GraphColor(k)
{
    if k > n
    {
        print color[1 ... n]
        return
    }

    for c = 1 to m
    {
        if IsSafe(k, c)
        {
            color[k] = c
            GraphColor(k + 1)
            color[k] = 0
        }
    }
}

IsSafe(v, c)
{
    for each vertex u adjacent to v
        if color[u] == c
            return false

    return true
}
~~~

### Example
Consider a graph with vertices A, B, C and D and edges:
(A,B), (A,C), (B,C), (B,D), (C,D).

Use three colors: Red, Green and Blue.

One valid assignment is:

| Vertex | Color |
|---|---|
| A | Red |
| B | Green |
| C | Blue |
| D | Red |

Verification:
- A and B have different colors.
- A and C have different colors.
- B and C have different colors.
- B and D have different colors.
- C and D have different colors.

Therefore, the graph is successfully colored using three colors.

### Complexity
For n vertices and m available colors:
- At most m choices are considered for each vertex.
- Worst-case time complexity: O(m^n), excluding or absorbing the adjacency-check cost; a straightforward safety check over up to n vertices gives O(n × m^n).
- Space complexity: O(n) for the color array and recursion stack, excluding graph storage.

### Conclusion
Backtracking solves graph coloring by assigning colors one vertex at a time and rejecting any assignment that gives equal colors to adjacent vertices.

---

## 4. Sum of Subsets Using Backtracking

- **Q. What is the Sum of Subsets problem? Solve the given instance using Backtracking: set = {2, 3, 5, 6, 8, 10}, required sum = 10.**

### Definition
The Sum of Subsets problem finds all subsets of a given set whose elements add up to a specified target value.

### Given data
Set = {2, 3, 5, 6, 8, 10}  
Required sum = 10

Each element has two choices:
- Include the element.
- Exclude the element.

### Backtracking principle
- If the current sum equals 10, a solution is found.
- If the current sum exceeds 10, reject that branch because all remaining values are positive.
- If no elements remain and the sum is not 10, reject the branch.
- Otherwise, explore include and exclude choices.

### Algorithm

~~~text
SumOfSubsets(i, currentSum)
{
    if currentSum == target
    {
        print selected subset
        return
    }

    if i > n or currentSum > target
        return

    include item[i]
    SumOfSubsets(i + 1, currentSum + item[i])

    exclude item[i]
    SumOfSubsets(i + 1, currentSum)
}
~~~

### Step-by-step solution
Given sorted set: {2, 3, 5, 6, 8, 10}.

The subsets that produce the target are:

| Selected elements | Sum |
|---|---:|
| {2, 3, 5} | 2 + 3 + 5 = 10 |
| {2, 8} | 2 + 8 = 10 |
| {10} | 10 |

Therefore, all solution subsets are:
**{2, 3, 5}, {2, 8}, {10}.**

### Complexity
- Each element has two choices: include or exclude.
- Worst-case time complexity: O(2^n), excluding the cost of printing solutions.
- Space complexity: O(n) for recursion and the current subset.

### Conclusion
Backtracking finds subsets by exploring include/exclude decisions and prunes a branch when its partial sum exceeds the target.

---

## 5. Branch-and-Bound: Principle, Control Abstraction and Time Analysis

- **Q. What is Branch-and-Bound? Explain its principle, control abstraction and time analysis.**

### Definition
Branch-and-Bound is an algorithm design technique used for optimization problems. It divides a problem into smaller subproblems and calculates a bound on the best solution possible from each subproblem.

A subproblem is discarded if its bound proves that it cannot improve the best solution already found.

### Principle
1. Start with the root node representing the original problem.
2. Branch by generating child nodes representing decisions.
3. Calculate a bound for each child node.
4. Maintain the best feasible solution found so far.
5. Prune nodes whose bounds cannot improve the current best solution.
6. Continue until no promising live node remains.

### Important terms
- **Live node:** Generated but not yet expanded.
- **E-node:** The live node currently selected for expansion.
- **Dead node:** A node that has been expanded or pruned.
- **Bounding function:** Estimates the best possible objective value reachable from a node.
- **Pruning:** Removing a node that cannot lead to a better solution.

### Control abstraction

~~~text
BranchAndBound(root)
{
    insert root into live-node structure
    bestSolution = initial feasible solution

    while live-node structure is not empty
    {
        node = select a live node
        expand node

        for each child of node
        {
            calculate bound(child)

            if child is feasible and can improve bestSolution
            {
                if child is a complete solution
                    update bestSolution
                else
                    insert child into live-node structure
            }
        }
    }

    return bestSolution
}
~~~

The live-node selection structure determines whether the method uses FIFO, LIFO or Least-Cost (LC) search.

### Time analysis
The worst-case number of nodes can be exponential because many combinations may need to be explored.

If the state-space tree contains N nodes and each node requires B time for bounding and processing, a general upper bound is O(N × B). The actual time depends on:
- Number of generated nodes.
- Cost of calculating bounds.
- Efficiency of pruning.
- Method used to select the next live node.

### Applications
- Travelling Salesperson Problem.
- 0/1 Knapsack problem.
- Scheduling and assignment optimization.

### Conclusion
Branch-and-Bound finds optimal solutions by exploring a state-space tree and pruning subproblems that cannot improve the current best solution.

---

## 6. FIFO, LIFO and Least-Cost Branch-and-Bound

- **Q. Explain FIFO, LIFO and Least-Cost search strategies used in Branch-and-Bound.**

### 1. FIFO Branch-and-Bound
- Uses a queue.
- The first generated live node is expanded first.
- Follows breadth-first search order.
- Nodes are explored level by level.

### 2. LIFO Branch-and-Bound
- Uses a stack.
- The most recently generated live node is expanded first.
- Follows depth-first search order.
- Explores one branch deeply before returning to another branch.

### 3. Least-Cost (LC) Branch-and-Bound
- Uses a priority queue.
- The live node with the least cost or best bound is selected first.
- For a minimization problem, the node with the smallest lower-bound estimate is expanded.
- For a maximization problem, the node with the most promising upper bound is selected.

### Comparison

| Basis | FIFO | LIFO | Least-Cost (LC) |
|---|---|---|---|
| Data structure | Queue | Stack | Priority queue |
| Node selection | Oldest live node | Newest live node | Best bound / least estimated cost |
| Search order | Breadth-first | Depth-first | Best-first |
| Memory | Can be high | Often lower | Can be high |
| Main advantage | Level-wise exploration | Simple and memory-efficient in many searches | Expands the most promising node first |
| Limitation | May store many nodes | May explore a poor branch deeply | Bound calculation and priority management add overhead |

### Conclusion
FIFO selects nodes by arrival order, LIFO selects the newest node, and LC selects the node with the most promising cost bound.

---

## 7. Travelling Salesperson Problem Using Branch-and-Bound

- **Q. Explain the Travelling Salesperson Problem and solve it using Branch-and-Bound.**

### Definition
The Travelling Salesperson Problem (TSP) asks for a minimum-cost tour in which a salesperson:
1. Starts from a city.
2. Visits every other city exactly once.
3. Returns to the starting city.
4. Minimizes the total travel cost.

### Branch-and-Bound approach
- Represent cities as vertices and travel costs as weighted edges.
- Each node represents a partial tour.
- Branch by selecting the next unvisited city.
- Calculate a lower bound on the possible cost of completing that partial tour.
- Prune a node if its lower bound is not better than the best complete tour already found.
- Expand the live node with the least lower-bound cost when using LC search.

### Illustrative example
Consider four cities A, B, C and D with the following symmetric travel-cost matrix:

| From / To | A | B | C | D |
|---|---:|---:|---:|---:|
| A | 0 | 10 | 15 | 20 |
| B | 10 | 0 | 35 | 25 |
| C | 15 | 35 | 0 | 30 |
| D | 20 | 25 | 30 | 0 |

Start from A. The possible tours, ignoring reverse duplicates in this symmetric example, are:

| Tour | Cost |
|---|---:|
| A-B-C-D-A | 10 + 35 + 30 + 20 = 95 |
| A-B-D-C-A | 10 + 25 + 30 + 15 = 80 |
| A-C-B-D-A | 15 + 35 + 25 + 20 = 95 |

The best tour among these is:
**A → B → D → C → A**

Minimum tour cost = **80**.

A Branch-and-Bound implementation explores partial tours and uses valid lower bounds to avoid exploring branches that cannot beat the current best tour. The table above verifies the final tour cost; it is not itself a complete lower-bound expansion trace.

### Complexity
- TSP has factorial search space.
- Worst-case time complexity is O(n!), because pruning may fail to eliminate enough tours.
- Space complexity depends on the live-node structure and can be exponential in the worst case.

### Conclusion
Branch-and-Bound reduces unnecessary TSP search by calculating lower bounds for partial tours and discarding branches that cannot produce a better complete tour.

---

## 8. 0/1 Knapsack Using Branch-and-Bound

- **Q. Explain how the 0/1 Knapsack problem is solved using Branch-and-Bound.**

### Definition
In 0/1 Knapsack, each item has a weight and profit. An item is either selected completely or rejected. The objective is to maximize total profit without exceeding capacity.

### Branch-and-Bound approach
1. Sort items by decreasing profit/weight ratio to calculate a useful upper bound.
2. At each level, create two branches: include the next item or exclude it.
3. Calculate the total weight and profit of the partial solution.
4. Calculate an upper bound by filling the remaining capacity fractionally using the remaining items in ratio order.
5. Prune a node if its weight exceeds capacity or its upper bound is not greater than the best feasible profit.
6. Continue until no live node can improve the best solution.

### Upper-bound calculation
For a maximization problem, the fractional filling estimate is an upper bound because allowing fractions can only make the estimated profit at least as large as the best 0/1 completion.

### Example
Capacity W = 16.

| Item | Weight | Profit | Profit/Weight |
|---|---:|---:|---:|
| I1 | 2 | 40 | 20 |
| I2 | 5 | 30 | 6 |
| I3 | 10 | 50 | 5 |
| I4 | 5 | 10 | 2 |

Consider selecting I1, I2 and I3:
- Total weight = 2 + 5 + 10 = 17, which exceeds capacity; reject this selection.

Consider I1, I2 and I4:
- Total weight = 2 + 5 + 5 = 12.
- Total profit = 40 + 30 + 10 = 80.

Consider I1 and I3:
- Total weight = 12.
- Total profit = 90.

The best feasible selection is I1 and I3:
- Total weight = 2 + 10 = 12.
- Total profit = **90**.

### Complexity
- Worst-case time complexity: O(2^n), because every include/exclude combination may be explored.
- Sorting by ratio takes O(n log n).
- Space complexity can be O(2^n) for storing live nodes in the worst case; depth-first variants may use less live-node memory.

### Conclusion
Branch-and-Bound solves 0/1 Knapsack by exploring include/exclude decisions and using an upper bound to prune branches that cannot beat the current best profit.

---

## 9. Comparison Between Backtracking and Branch-and-Bound

- **Q. Differentiate between Backtracking and Branch-and-Bound.**

| Basis | Backtracking | Branch-and-Bound |
|---|---|---|
| Main purpose | Finds feasible solutions or all solutions satisfying constraints | Finds an optimal solution to an optimization problem |
| Main test | Checks whether a partial solution is promising/feasible | Checks whether a node's bound can improve the current best solution |
| Pruning | Rejects constraint-violating or non-promising partial solutions | Rejects nodes whose bounds cannot improve the incumbent solution |
| Search | Commonly depth-first search | FIFO, LIFO or Least-Cost search |
| Node selection | Usually follows recursive depth-first order | Depends on queue, stack or priority queue |
| Objective | May be feasibility or enumeration | Optimization |
| Examples | N-Queen, graph coloring, sum of subsets | TSP, 0/1 knapsack |

### Conclusion
Backtracking mainly prunes infeasible or non-promising choices, while Branch-and-Bound uses objective-function bounds to eliminate subproblems that cannot improve an optimal solution.

---

## 10. Case Study: Airline Crew Scheduling

- **Q. Explain the application of algorithmic techniques to the Airline Crew Scheduling problem.**

### Introduction
An airline must assign pilots and cabin crew to flights while satisfying operational rules and minimizing scheduling cost. A crew member cannot be assigned to two overlapping flights and must satisfy qualification, rest and duty-time requirements.

The exact constraints depend on airline policy and aviation regulations. The following is a general optimization model for understanding the syllabus case study.

### Problem representation
- Flights are the tasks to be covered.
- Crew members are the resources assigned to those tasks.
- A crew-flight assignment is a decision.
- Assignment cost may represent duty cost, travel cost or another defined objective.

### Constraints
1. Every flight must receive the required number of qualified crew members.
2. Crew members must have the required qualifications and ratings.
3. A crew member cannot be assigned to overlapping flights.
4. Required rest periods must be maintained.
5. Duty-time limits must be respected.
6. A crew member's availability must be considered.

### Objective
Minimize total assignment cost or, in a feasibility version, find a valid crew assignment that covers all flights.

### Branch-and-Bound interpretation
1. Start with no flights assigned.
2. Select an unassigned flight.
3. Branch by assigning an eligible crew group or crew member.
4. Reject a branch immediately if it violates qualification, overlap or rest constraints.
5. Calculate a lower bound on the remaining assignment cost.
6. If the lower bound is no better than the best complete schedule found, prune the branch.
7. Continue until the best valid schedule is established or no feasible schedule exists.

### Simple illustrative example
Suppose three flights F1, F2 and F3 require one crew team each. Three teams T1, T2 and T3 are available. Assume the following assignment costs and that all listed assignments are qualified and schedule-compatible:

| Flight | T1 | T2 | T3 |
|---|---:|---:|---:|
| F1 | 4 | 6 | 8 |
| F2 | 5 | 3 | 7 |
| F3 | 6 | 5 | 2 |

One valid assignment is:
- F1 → T1, cost 4.
- F2 → T2, cost 3.
- F3 → T3, cost 2.

Total assignment cost = 4 + 3 + 2 = **9**.

This example illustrates the assignment objective only. Real crew scheduling must additionally validate duty periods, rest rules, crew composition and operational constraints.

### Why Branch-and-Bound is useful
- It explores alternative crew assignments.
- It rejects assignments that violate constraints.
- It uses cost bounds to avoid examining every possible schedule.
- It can search for a minimum-cost feasible schedule.

### Conclusion
Airline crew scheduling is a constrained resource-allocation problem. Branch-and-Bound can be used to search for a feasible, low-cost assignment while pruning invalid or uncompetitive partial schedules. The exact operational model depends on the constraints supplied in the problem.
