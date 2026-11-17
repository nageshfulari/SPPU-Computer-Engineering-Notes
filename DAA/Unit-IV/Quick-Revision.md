# Unit IV — Quick Revision
## Backtracking and Branch-and-Bound

## 1. Backtracking
- Builds a solution one decision at a time.
- Uses a state-space tree.
- Usually explores depth-first.
- Rejects non-promising or constraint-violating partial solutions.
- Removes the last choice and tries another when a branch fails.

**Control flow:** Choose → Check promising → Recurse → Undo choice.

**Worst-case:** Exponential; depends on branching factor and depth.

## 2. 8-Queen
- Place one queen in each row.
- No two queens may share a column or diagonal.
- Safety condition for rows i and j:
  - column[i] != column[j]
  - |column[i] - column[j]| != |i - j|
- Try a column; recurse if safe; backtrack if no safe column remains.
- Example solution columns by row: [1, 5, 8, 6, 3, 7, 2, 4].
- Common search bound: O(N × N!) for a straightforward safety-check implementation.

## 3. Graph Coloring
- Adjacent vertices must have different colors.
- Assign colors vertex by vertex.
- Reject a color if an adjacent already-colored vertex uses it.
- Worst-case: O(m^n) assignments for n vertices and m colors; straightforward checks can add O(n).
- Space: O(n), excluding graph storage.

## 4. Sum of Subsets
- Each item has include/exclude decisions.
- If current sum = target, output subset.
- If current sum > target (positive values), prune.
- Worst-case: O(2^n) time; O(n) recursion space.
- Example: set {2,3,5,6,8,10}, target 10.
- Solutions: {2,3,5}, {2,8}, {10}.

## 5. Branch-and-Bound
- Used for optimization.
- Branch into subproblems.
- Calculate a bound on the best possible completion.
- Keep the best feasible solution found (incumbent).
- Prune a node if its bound cannot improve the incumbent.
- Worst-case can be exponential.

**Terms:** Live node, E-node, dead node, bound, pruning.

## 6. FIFO, LIFO and LC

| Strategy | Data structure | Selection |
|---|---|---|
| FIFO | Queue | Oldest live node |
| LIFO | Stack | Newest live node |
| LC | Priority queue | Best bound / least estimated cost |

- FIFO = breadth-first.
- LIFO = depth-first.
- LC = best-first according to bound.

For minimization, choose the smallest lower bound. For maximization, choose the largest upper bound.

## 7. TSP using B&B
- Visit every city exactly once and return to start.
- Each node is a partial tour.
- Bound estimates minimum possible completion cost.
- Prune if bound >= best complete tour cost (minimization).
- Worst-case: O(n!) time.

Example cost matrix:
A-B 10, A-C 15, A-D 20; B-C 35, B-D 25; C-D 30.
Best tour: A-B-D-C-A = 80.

## 8. 0/1 Knapsack using B&B
- Include/exclude each item.
- Reject if weight exceeds capacity.
- Calculate upper bound using fractional filling of remaining capacity.
- Prune if upper bound <= current best profit.
- Worst-case: O(2^n); ratio sorting O(n log n).

## 9. Backtracking vs Branch-and-Bound

| Backtracking | Branch-and-Bound |
|---|---|
| Feasibility / constraint search | Optimization |
| Prunes invalid partial solutions | Prunes nodes using objective bounds |
| Usually DFS | FIFO, LIFO or LC |
| N-Queen, coloring, subsets | TSP, knapsack |

## 10. Airline Crew Scheduling
- Flights are tasks; crew teams are resources.
- Constraints: qualification, availability, no overlapping flights, rest and duty limits.
- Objective: find feasible assignment and/or minimize total cost.
- B&B branches on assignments, rejects invalid schedules and prunes using lower cost bounds.

## Complexity at a glance

| Problem | Worst-case time |
|---|---|
| Backtracking general tree | O(b^d) nodes, plus test cost |
| N-Queen | Common upper bound O(N × N!) |
| M-Coloring | O(n × m^n) with straightforward safety checks |
| Sum of Subsets | O(2^n) |
| Branch-and-Bound | Exponential in general |
| TSP | O(n!) |
| 0/1 Knapsack B&B | O(2^n) |

## Exam reminders
1. Backtracking checks feasibility/promising conditions; B&B checks objective bounds.
2. In minimization, prune when lower bound cannot beat the incumbent.
3. In maximization, prune when upper bound cannot beat the incumbent.
4. FIFO uses a queue, LIFO a stack, LC a priority queue.
5. TSP tour must return to the starting city.
6. In crew scheduling, state the assumed operational constraints clearly.
