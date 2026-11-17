# OOMD – Unit IV Quick Revision

## Very High Priority
- Architectural Styles (6/6): Data-Centered, Data-Flow, Call-and-Return, Object-Oriented, Layered.
- External Control categories (6/6): Procedure-Driven and Event-Driven; Event-Driven includes Broadcast-Based and Interrupt-Driven.
- Global Resource Handling (4/6): centralized management, allocation, synchronization, sharing and deadlock handling.

## High Priority
- Data Storage Management (3/6): storage selection, organization, access, security, integrity and distribution.
- Reuse Plan (3/6): Library, Framework and Pattern.
- Batch vs Continuous Transformation (3/6).
- Subsystem decomposition and allocation (3/6).
- ATM Architecture (3/6).

## Medium Priority
- Component Diagram: Component, Interface (provided/required), Dependency, Port, Connector and Subsystem.
- Deployment Diagram: Node, Association and Dependency.
- ATM Deployment Diagram.
- Interactive Interface, Dynamic Simulation, Real-Time System and Transaction Manager.

## Low Priority
- External Control vs Internal Control.
- Subsystem communication.
- System Design definition and example.
- System Performance Estimation.

## Key Definitions
- **Architectural Style:** Overall organization of software components and their interactions.
- **External Control:** Control flow managed by a separate mechanism.
- **Internal Control:** Individual objects manage their own behavior.
- **Global Resource:** Resource shared by multiple components or subsystems.
- **Reuse Plan:** Plan for identifying reusable components, libraries, frameworks and patterns.
- **Subsystem:** Related classes, objects or components grouped to perform a specific function.
- **System Design:** Defines architecture, components, interfaces, data organization and control strategies.
- **Performance Estimation:** Predicts response time, throughput, resource use, concurrency and scalability.
- **Component Diagram:** UML structural view of software components and dependencies.
- **Deployment Diagram:** UML structural view of hardware nodes and deployed software artifacts.

## Important Comparisons

### External Control vs Internal Control
| External | Internal |
|---|---|
| Separate controller/events manage flow | Objects manage their own behavior |
| Overall execution flow | Individual object behavior |
| Procedure calls/event handling | Messages and state transitions |

### Library vs Framework vs Pattern
| Library | Framework | Pattern |
|---|---|---|
| Reusable code | Reusable application structure | Reusable design solution |
| Application calls library | Framework controls flow | Developer implements solution |

### Batch vs Continuous Transformation
| Batch | Continuous |
|---|---|
| Processes collected groups | Processes data as it arrives |
| Output after batch | Output continuously |
| Scheduled processing | Real-time/near-real-time processing |

## UML Diagram Reminders
- Component: rectangle with component marker.
- Provided Interface: lollipop (circle).
- Required Interface: socket (semicircle).
- Dependency: dashed arrow toward supplier.
- Port: small square on component boundary.
- Deployment Node: 3D-style rectangle.
- Node Association: solid communication line.
- Deployment Dependency: dashed arrow.

## Exam Preparation
1. Prepare all Very High and High topics first.
2. Practice diagrams for Architectural Styles, External Control, subsystem decomposition, ATM Deployment and ATM Architecture.
3. Revise comparison tables before the exam.
4. Do not skip lower-frequency questions; some are asked for 7 marks.
