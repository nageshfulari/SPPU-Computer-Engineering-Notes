# Unit III — Quick Revision
## Greedy and Dynamic Programming

## 1. Greedy Strategy

- Select the locally best feasible choice at each step.
- Do not normally reconsider previous choices.
- Correctness generally requires greedy-choice property and optimal substructure.
- Control abstraction: select candidate → check feasibility → add to solution.
- Time depends on sorting, selection and feasibility checks.

**Common examples:** Fractional knapsack, job sequencing, activity selection.

## 2. Fractional Knapsack

- Calculate ratio = Profit / Weight.
- Sort items in decreasing ratio.
- Take complete items while possible.
- Take a fraction of the next item if capacity is insufficient.
- Greedy is optimal because fractions are allowed.

**Example result:** Capacity 50; items (10,60), (20,100), (30,120). Take first two and 2/3 of third. Maximum profit = 240.

**Complexity:** O(n log n) time.

## 3. Job Sequencing with Deadlines

- Each job takes one time unit and has a deadline and profit.
- Sort jobs by decreasing profit.
- Place each job in the latest free slot on or before its deadline.
- Reject a job if no valid slot is available.

**Remember:** Highest profit first; schedule as late as possible.

**Example result:** J1(2,100), J2(1,19), J3(2,27), J4(1,25), J5(3,15). Schedule J3, J1, J5. Profit = 142.

**Complexity:** O(n log n + nd), where d is maximum deadline.

## 4. Activity Selection

- Goal: Select maximum number of non-overlapping activities.
- Sort by increasing finish time.
- Select the first activity.
- Select next activity if start time >= finish time of last selected activity.

**Example result:** A1(1,3), A2(2,5), A3(4,6), A4(6,7), A5(5,8), A6(8,9). Select A1, A3, A4, A6. Count = 4.

**Complexity:** O(n log n); O(n) if input is already sorted by finish time.

## 5. Dynamic Programming

- Solve overlapping subproblems and store their results.
- Requires optimal substructure.
- Memoization = top-down.
- Tabulation = bottom-up.
- General time = number of states × work per state.

## 6. Principle of Optimality

An optimal solution contains optimal solutions to its subproblems, based on the chosen state representation and recurrence.

Generic form:

F(state) = min/max over valid decisions { immediate cost/value + F(next state) }

## 7. Binomial Coefficients

C(n, 0) = 1  
C(n, n) = 1  
C(n, r) = C(n-1, r-1) + C(n-1, r)

Example: C(5,2) = C(4,1) + C(4,2) = 4 + 6 = 10.

**Complexity:** O(nr) time and O(nr) space; optimized space O(r).

## 8. Optimal Binary Search Tree (OBST)

For successful-search frequencies only:

W[i,j] = sum of frequencies from i to j

C[i,j] = min over r {C[i,r-1] + C[r+1,j] + W[i,j]}

Base: C[i,i-1] = 0.

- Frequently searched keys should be closer to root.
- If unsuccessful-search probabilities are given, dummy keys are needed and the recurrence changes.

**Complexity:** O(n³) time, O(n²) space.

## 9. 0/1 Knapsack Using DP

If item i is too heavy:

DP[i,w] = DP[i-1,w]

Otherwise:

DP[i,w] = max(DP[i-1,w], profit[i] + DP[i-1,w-weight[i]])

Base: DP[0,w] = 0 and DP[i,0] = 0.

- Item is either fully selected or rejected.
- Do not use fractional greedy logic.

**Complexity:** O(nW) time and O(nW) space; pseudo-polynomial.

## 10. Matrix Chain Multiplication

Base: m[i,i] = 0

m[i,j] = min over i <= k < j of:

m[i,k] + m[k+1,j] + p[i-1] × p[k] × p[j]

- Matrix order remains fixed.
- Only parenthesization changes.
- Select the split k with minimum multiplication cost.

**Complexity:** O(n³) time, O(n²) space.

## 11. Greedy vs DP

| Greedy | Dynamic Programming |
|---|---|
| Makes local best choice | Evaluates alternatives using subproblems |
| Usually does not reconsider | Stores and reuses results |
| Often less memory | Usually requires table/storage |
| Optimal only with greedy-choice property | Optimal if recurrence correctly models optimal substructure |
| Fractional knapsack | 0/1 knapsack |

## 12. Complexity at a glance

| Algorithm | Time | Auxiliary space |
|---|---|---|
| Greedy control abstraction | Problem-dependent; often O(n log n) with sorting | Problem-dependent |
| Fractional knapsack | O(n log n) | O(n) if separate sorted list |
| Job sequencing | O(n log n + nd) | O(d) |
| Activity selection | O(n log n) | O(1) scan after sorting |
| Binomial coefficients | O(nr) | O(nr), or O(r) optimized |
| OBST | O(n³) | O(n²) |
| 0/1 Knapsack DP | O(nW) | O(nW), or O(W) optimized |
| Matrix-chain multiplication | O(n³) | O(n²) |

## Exam reminders

1. Fractional knapsack and 0/1 knapsack are different problem variants.
2. In job sequencing, place a job in the latest free slot before its deadline.
3. In activity selection, sort by finish time, not start time.
4. In OBST, state clearly whether unsuccessful-search probabilities are included.
5. In matrix-chain multiplication, matrix order cannot change; only brackets change.
6. DP complexity should be derived from states × work per state.
