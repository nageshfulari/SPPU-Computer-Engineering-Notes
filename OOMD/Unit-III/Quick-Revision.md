# OOMD – Unit III: Quick Revision

## Advanced State Modeling

- **State:** Condition of an object at a particular time.
- **Event:** Occurrence that may trigger a state change.
- **Transition:** Movement from one state to another due to an event.
- **Composite State:** State containing nested substates.
- **Sequential Composite State:** One region; one substate active at a time.
- **Concurrent / Orthogonal Composite State:** Multiple regions active concurrently.
- **Concurrency notation:** Orthogonal regions separated by a divider inside a composite state.

## Class Model vs State Model

- Class Model = static structure: classes, attributes, operations, relationships.
- State Model = dynamic behavior: states, events, transitions.
- Class model identifies object types; state model describes the life cycle of their objects.

## Use Case Modeling

| Element / Relationship | Remember |
|---|---|
| Actor | External role; stick figure |
| Use Case | System function; oval |
| System Boundary | Rectangle around use cases |
| Association | Solid line between actor and use case |
| `<<include>>` | Mandatory reused behavior; arrow from base to included use case |
| `<<extend>>` | Optional/conditional behavior; arrow from extending use case to base use case |
| Generalization | Hollow triangle points to the general parent |

## Sequence Diagram

- Shows messages exchanged by participants in time order.
- Time generally moves from top to bottom.
- Components: actor, participant/object, lifeline, activation bar, messages, destruction occurrence.
- Synchronous: sender waits for completion.
- Asynchronous: sender does not wait.
- Return: dashed arrow.
- Self-message: message sent by an object to itself.

## Activity Diagram

- Shows workflow/control flow among actions.
- Initial node: filled circle.
- Activity/action: rounded rectangle.
- Control flow: arrow.
- Decision / merge: diamond.
- Fork / join: thick bar.
- Activity final: bull's-eye symbol.
- Guard conditions: `[Yes]`, `[No]`, `[condition]`.

## High-Value Diagrams to Practice

1. Composite state – sequential and concurrent regions.
2. ATM Use Case Diagram and two use case scenarios.
3. Online Reservation Use Case Diagram.
4. ATM Cash Withdrawal Sequence Diagram.
5. Online Shopping Sequence Diagram.
6. Rent a Car Sequence Diagram.
7. ATM Activity Diagram.
8. Email Login Activity Diagram.
9. Hospital Management Activity Diagram.
10. Two-Wheeler Sales Activity Diagram.
11. Cash Dispenser State Diagram.
12. Telephone Line State Diagram.

## Fast Recall

- Sequence Diagram: **Who sends what message to whom, and when?**
- Activity Diagram: **What steps happen in the workflow?**
- State Diagram: **What state is the object in, and what event changes it?**
- Class Model: **What classes and structural relationships exist?**
- Use Case Diagram: **Which external actors use which system functions?**
