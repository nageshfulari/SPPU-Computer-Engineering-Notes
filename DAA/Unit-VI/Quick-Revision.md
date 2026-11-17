# Unit VI — Quick Revision
## Multithreaded and Distributed Algorithms | DAA (410241)

## 1. Multithreaded algorithms
- Divide computation into concurrent tasks called threads.
- Threads may execute on multiple processor cores.
- Synchronization is needed when tasks share mutable data.

### Performance measures

| Measure | Meaning |
|---|---|
| Work T1 | Total operations / sequential work |
| Span T-infinity | Longest dependency path / critical path |
| Parallelism | T1 / T-infinity |
| Speedup | T1 / Tp |
| Efficiency | Speedup / p |

Lower bound:
Tp >= max(T1/p, T-infinity)

## 2. Parallel loops
- Independent loop iterations can execute concurrently.
- Example: C[i] = A[i] + B[i].
- Work for n constant-time iterations = O(n).
- Ideal span = O(1) with enough processors, excluding scheduling overhead.

## 3. Race condition
- Multiple threads access shared data concurrently.
- At least one access is a write.
- Result depends on execution order.
- Prevent with locks, semaphores, atomic operations or avoiding shared mutable state.

## 4. Spawn and Sync
- spawn: starts a parallel task.
- sync: waits for spawned child tasks to finish before dependent work continues.

## 5. Multithreaded matrix multiplication
For A(m × n) and B(n × p):
C[i][j] = sum over k of A[i][k] × B[k][j]

For square n × n matrices:
- Work = O(n^3).
- Row/output-element parallelization span = O(n), assuming each dot product is sequential.
- Partition by rows or blocks.
- Block-wise method can improve cache locality.

## 6. Multithreaded Merge Sort
- Spawn recursive sort of left and right halves.
- Sync.
- Merge the sorted halves.

Sequential merge:
- Work O(n), span O(n).

Parallel merge (suitable algorithm):
- Work O(n), span O(log n).

Merge Sort:
- Work O(n log n).
- Sequential merge span: O(n).
- With parallel merge span: O(log^2 n) under standard idealized bounds.

## 7. Distributed algorithms
- Multiple networked nodes solve a problem through message passing.
- Each node has local memory.
- Challenges: communication delay, synchronization, message loss, load balance and failures.

## 8. Distributed BFS
- Level-synchronous traversal.
- Start source at distance 0.
- Process current frontier.
- Send discovery messages to owners of neighbours.
- Mark newly discovered vertices.
- Synchronize and advance to next frontier.
- Single-machine BFS: O(V + E).
- Distributed elapsed time depends on messages, network and partitioning.

## 9. Distributed MST
- Distributed Boruvka-style method:
  1. Each vertex starts as a component.
  2. Each component finds minimum outgoing edge.
  3. Communicate selected edges.
  4. Merge components.
  5. Repeat until one component remains.
- Boruvka phases: O(log V).
- Centralized work: O(E log V).
- Distributed communication complexity depends on the model.

## 10. Naive string matching
- Check pattern at every shift.
- Number of shifts = n - m + 1.
- Worst time = O(nm).
- Auxiliary space = O(1).

## 11. Rabin–Karp
- Calculate pattern hash and first window hash.
- Compare hashes.
- Verify characters when hashes match.
- Update hash using rolling hash.

Rolling hash:
tHashNext = (d × (tHash - leadingCharacter × h) + nextCharacter) mod q

where h = d^(m-1) mod q.

- Expected time: O(n + m), under suitable assumptions.
- Worst time: O(nm).
- Spurious hit: hash match but strings differ.

## 12. Plagiarism detection
- Normalize and tokenize documents.
- Select phrases or fingerprints.
- Search using string matching.
- Report matching passages and similarity.
- Human review is required; matching text alone does not prove plagiarism.

## Must-remember complexities

| Algorithm / measure | Complexity |
|---|---|
| Naive string matching | O(nm) worst |
| Rabin–Karp | O(n + m) expected; O(nm) worst |
| Matrix multiplication | O(n^3) work for square matrices |
| Merge Sort | O(n log n) work |
| Sequential merge | O(n) span |
| Parallel merge | O(log n) span with suitable algorithm |
| BFS (single machine) | O(V + E) |
| Boruvka MST (centralized) | O(E log V) work |
