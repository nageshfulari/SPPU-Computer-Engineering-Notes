# Unit VI – Complete Exam Answers

**Subject:** Object Oriented Modeling and Design (410244(D))  
**Unit:** VI – Design Pattern  
**Course:** Fourth Year Computer Engineering – SPPU, 2019 Course

> The 18 supplied questions are presented in their original order. Marks, supplied frequency ranges and difficulty labels are retained. Supplementary syllabus answers S1–S3 are available in [Supplementary Syllabus Answers](Supplementary-Syllabus-Answers.md).

## Q1. What is a Design Pattern? Explain different types/categories of Design Patterns. [6 Marks]

A **Design Pattern** is a reusable and proven solution to a commonly occurring problem in software design. It provides a general template or guideline for solving a design problem in a particular context.

Design patterns capture the experience of software designers and improve reusability, flexibility, maintainability and communication among developers.

### Categories of Design Patterns

**1. Creational Patterns**
- Deal with the process of object creation.
- Provide flexible mechanisms for creating objects and hide complex creation logic.
- Examples: Factory Method, Abstract Factory, Singleton, Builder and Prototype.

**2. Structural Patterns**
- Deal with the composition and organization of classes and objects.
- Explain how components can be combined to form larger structures.
- Examples: Adapter, Bridge, Composite, Decorator, Facade, Proxy and Flyweight.

**3. Behavioral Patterns**
- Deal with communication and interaction between objects.
- Define how responsibilities are distributed and how objects cooperate.
- Examples: Observer, Strategy, Command, Iterator, Mediator, State and Visitor.

### Classification

```text
                 Design Patterns
                       |
          +------------+------------+
          |            |            |
      Creational   Structural   Behavioral
          |            |            |
      Object       Class and     Object
      Creation     Object        Interaction
                   Composition
```

**Advantages:** Reusability, maintainability, flexibility, common design vocabulary and improved software structure.

**Conclusion:** Creational, Structural and Behavioral Patterns address object creation, object composition and object interaction respectively.

## Q2. Explain the following: (i) Creational Patterns (ii) Structural Patterns (iii) Behavioral Patterns. [6 Marks]

### (i) Creational Patterns
Creational Patterns deal with object creation. They separate object creation from object usage, hide creation logic and reduce dependency on concrete classes.

Examples:
1. **Factory Method:** Defines an interface for creating objects and lets subclasses decide which class to instantiate.
2. **Abstract Factory:** Creates families of related objects without specifying concrete classes.
3. **Singleton:** Ensures that a class has only one instance.
4. **Builder:** Constructs complex objects step by step.
5. **Prototype:** Creates objects by copying existing objects.

### (ii) Structural Patterns
Structural Patterns deal with the composition and organization of classes and objects. They simplify relationships and help form larger structures.

Examples:
1. **Adapter:** Makes incompatible interfaces work together.
2. **Bridge:** Separates abstraction from implementation.
3. **Composite:** Organizes objects into tree structures.
4. **Decorator:** Adds responsibilities to an object dynamically.
5. **Facade:** Provides a simplified interface to a complex subsystem.
6. **Proxy:** Controls access to another object.
7. **Flyweight:** Shares common objects to reduce memory usage.

### (iii) Behavioral Patterns
Behavioral Patterns deal with communication and interaction between objects. They define responsibility distribution and cooperation.

Examples:
1. **Observer:** Notifies dependent objects when a subject changes.
2. **Strategy:** Defines interchangeable algorithms.
3. **Command:** Encapsulates a request as an object.
4. **Iterator:** Provides sequential access to collection elements.
5. **Mediator:** Centralizes communication between objects.
6. **State:** Changes object behavior according to its internal state.
7. **Visitor:** Separates operations from the objects on which they operate.

| Basis | Creational | Structural | Behavioral |
|---|---|---|---|
| Focus | Object creation | Object composition | Object interaction |
| Purpose | Controls object creation | Organizes classes and objects | Manages communication and responsibilities |
| Examples | Factory, Singleton | Adapter, Bridge | Observer, Strategy |

**Conclusion:** The three categories address creation, composition and interaction, helping build flexible and maintainable systems.

## Q3. Explain the basic elements of a Design Pattern. [4 Marks]

A design pattern has four basic elements:

1. **Pattern Name:** A meaningful name that identifies the pattern and provides a common vocabulary.
2. **Problem:** Describes the design problem, its context and the conditions in which the pattern is useful.
3. **Solution:** Describes the general arrangement of elements, participating classes, objects, responsibilities and relationships. It is a reusable design structure, not complete source code.
4. **Consequences:** Describes results, benefits, limitations and trade-offs, including effects on flexibility, performance and maintainability.

**Conclusion:** Pattern Name, Problem, Solution and Consequences provide a standard way to describe and reuse design solutions.

## Q4. State and explain the entities involved in a Design Pattern. [5 Marks]

The main entities used to describe a design pattern are:

1. **Participants:** Classes or objects that take part in the pattern. Each participant performs a specific role.
2. **Responsibilities:** Duties or tasks assigned to each participant.
3. **Collaborations:** Describe how participants communicate and work together to achieve the pattern's objective.
4. **Relationships:** Connections among participants, such as inheritance, association, aggregation and composition.
5. **Consequences:** Results, benefits, limitations and trade-offs of applying the pattern.

**Conclusion:** These entities describe the structure of a pattern, the duties of its components, their interactions and the impact of applying the pattern.

## Q5. Explain the Strategy Design Pattern. [4 Marks]

The **Strategy Design Pattern** is a Behavioral Pattern that defines a family of algorithms, encapsulates each algorithm separately and makes them interchangeable. It allows an algorithm to be selected at runtime without changing the client code that uses it.

### Components
1. **Strategy Interface:** Defines a common interface for supported algorithms.
2. **Concrete Strategy:** Implements the interface using a particular algorithm.
3. **Context:** Maintains a reference to a Strategy and delegates execution to it.
4. **Client:** Selects a strategy and provides it to the Context.

### Working
- Each algorithm is implemented in a separate concrete strategy.
- All strategies follow the same interface.
- The Context refers to the selected strategy and delegates execution.
- The Client can change the selected strategy at runtime.

### Example
An online shopping system may support Credit Card, UPI and Net Banking payment strategies. The customer selects a method and the Context invokes the corresponding payment algorithm.

**Advantages:** Runtime flexibility, reusable algorithms, easier maintenance and reduced coupling.

**Conclusion:** Strategy encapsulates interchangeable algorithms and allows the selected algorithm to change without modifying the Context.

## Q6. Explain the Observer Design Pattern. [2 Marks]

The **Observer Design Pattern** is a Behavioral Pattern that defines a one-to-many dependency between objects. When the Subject changes state, its dependent Observers are automatically notified.

**Components:**
1. **Subject:** Maintains observers and provides attach, detach and notify operations.
2. **Observer:** Defines an interface for receiving updates.
3. **Concrete Subject:** Maintains state and notifies observers when it changes.
4. **Concrete Observer:** Implements the Observer interface and updates itself after notification.

**Working:** Observers register with the Subject. When its state changes, the Subject notifies all registered observers, which then process the update.

**Example:** A YouTube channel acts as the Subject and subscribers act as Observers. Subscribers receive notifications when a new video is uploaded.

**Conclusion:** Observer provides automatic notification through a one-to-many relationship between objects.

## Q7. Discuss the Adapter Design Pattern. [1 Mark]

The **Adapter Design Pattern** is a Structural Pattern that allows two incompatible interfaces to work together. It converts the interface of an existing class into the interface expected by the client.

**Working:** The Client sends a request through the Target interface. The Adapter converts it into a form understood by the Adaptee, which performs the operation.

**Example:** A travel plug adapter allows a device with one plug type to connect to a different socket type.

**Advantages:** Reuses existing classes, connects incompatible interfaces and avoids modifying the existing class.

**Conclusion:** Adapter makes incompatible interfaces compatible by converting one interface into another expected by the client.

## Q8. Explain the Client-Dispatcher-Server Design Pattern. [1 Mark]

The **Client-Dispatcher-Server Pattern** is a Communication Pattern used in distributed systems. A Dispatcher acts as an intermediary, locates the appropriate server and forwards client requests.

**Components:**
1. **Client:** Sends service requests.
2. **Dispatcher:** Identifies the appropriate server and forwards requests.
3. **Server:** Processes requests and returns responses.

**Working:** The Client sends a request to the Dispatcher. The Dispatcher locates a suitable Server and forwards the request. The Server processes it and returns the response.

**Example:** An online shopping application may route product, payment and order requests to separate servers.

**Advantages:** Reduces client-server dependency and supports flexibility and scalability.

## Q9. What is a Communication Pattern? Explain any one Communication Pattern in detail. [1 Mark]

A **Communication Pattern** describes how software components or objects communicate and exchange information.

Types include Forwarder-Receiver, Client-Dispatcher-Server and Publisher-Subscriber.

### Publisher-Subscriber Pattern
It allows publishers to generate events and distribute them to interested subscribers through an intermediary Event Channel.

**Components:** Publisher, Subscriber and Event Channel.

**Working:** Subscribers register interest in events. A Publisher generates an event and sends it to the Event Channel. The channel distributes it to relevant subscribers, which process the notification.

**Example:** A news service publishes breaking news and users subscribed to that topic receive notifications.

**Advantages:** Loose coupling, one-to-many communication and scalability.

## Q10. Discuss the structure and variants of the Publisher-Subscriber Design Pattern. [1 Mark]

The **Publisher-Subscriber Pattern** allows publishers to distribute events to multiple subscribers without directly knowing their identities.

### Structure
1. **Publisher:** Generates and publishes events.
2. **Subscriber:** Registers interest and receives notifications.
3. **Event Channel:** Receives events and distributes them to relevant subscribers.
4. **Event:** Information or notification generated by a publisher.

```text
 Publisher
     |
 Publishes event
     v
 Event Channel
    /       \
   v         v
Subscriber  Subscriber
    1           2
```

### Common implementation variants
1. **Centralized:** A central event channel manages subscriptions and distributes events.
2. **Distributed:** Multiple event channels cooperate across network locations.
3. **Synchronous delivery:** The publisher's operation may wait for delivery or processing, depending on the implementation.
4. **Asynchronous delivery:** The publisher sends an event without waiting for subscribers to finish processing it.

**Advantages:** Loose coupling, one-to-many communication, flexibility and scalability.

## Q11. Write short notes on: (i) Client-Dispatcher-Server (ii) Publisher-Subscriber. [1 Mark]

### (i) Client-Dispatcher-Server
A Communication Pattern in which a Dispatcher acts as an intermediary between clients and servers.

- **Client:** Sends requests.
- **Dispatcher:** Locates the appropriate server and forwards the request.
- **Server:** Processes the request and returns a response.

Example: Routing online shopping requests to product, payment or order servers.

Benefits include reduced client-server dependency and support for multiple servers.

### (ii) Publisher-Subscriber
A Communication Pattern in which publishers generate events and distribute them to interested subscribers through an Event Channel.

- **Publisher:** Produces events.
- **Subscriber:** Registers interest and receives notifications.
- **Event Channel:** Distributes events.

Example: Users receive notifications when a subscribed news service publishes a new story.

Benefits include loose coupling and one-to-many communication.

## Q12. Explain the View Handler Pattern in detail. [1 Mark]

The **View Handler Pattern** is a Management Pattern used to manage different views of an application. It provides a centralized mechanism for creating, selecting, displaying and switching views.

**Components:**
1. **View Handler:** Manages creation, selection and switching of views.
2. **View:** Represents the user interface displayed to the user.
3. **Application:** Provides application logic and data required by views.
4. **User:** Interacts with the application through the displayed views.

**Working:** The user requests a view. The View Handler identifies or creates it, obtains the required application data and manages its display and switching.

**Example:** An online banking application may have Login, Account Details, Fund Transfer and Transaction History views.

**Advantages:** Centralized management, reusable views, separation of concerns and easier maintenance.

## Q13. Explain the Command Processor Pattern. [Syllabus]

The **Command Processor Pattern** is a Management Pattern that centralizes the handling and execution of commands or requests. It separates the request sender from the object that performs the operation.

**Components:**
1. **Client:** Creates and submits commands.
2. **Command:** Represents a request or operation.
3. **Command Processor:** Receives commands and manages their execution; it may queue or schedule them.
4. **Receiver:** Performs the requested operation.

**Working:** The Client creates a command and submits it to the Command Processor. The processor manages and dispatches it to the appropriate Receiver. The Receiver performs the operation.

**Example:** In an ATM, a withdrawal request can be represented as a command and processed by the banking service.

**Advantages:** Centralized command management, separation of request creation and execution, and support for queuing or scheduling.

## Q14. Explain the Forwarder-Receiver Pattern. [Syllabus]

The **Forwarder-Receiver Pattern** is a Communication Pattern used in distributed systems. It supports communication between components on different machines by separating message-sending and message-receiving responsibilities.

**Components:**
1. **Forwarder:** Sends messages through a communication mechanism.
2. **Receiver:** Accepts incoming messages and delivers them to the appropriate application component.
3. **Communication Channel:** Transfers messages between the Forwarder and Receiver.
4. **Application Components:** Generate requests and process received messages.

**Working:** A sending component generates a message. The Forwarder sends it through the Communication Channel. The Receiver accepts it and delivers it to the destination application component. A response can be sent back using the same mechanism.

**Example:** A bank branch sends an account inquiry to a central banking server through a network.

**Advantages:** Separation of communication responsibilities, support for distributed communication and improved modularity.

## Q15. Show and explain the relationships between Patterns. [1 Mark]

Design Patterns are not independent solutions. They may use, complement or provide alternatives to one another.

1. **Uses:** One pattern uses another as part of its implementation. Example: Abstract Factory may use Factory Method.
2. **Similar Purpose:** Patterns may address related problems using different approaches. Example: Strategy and State both use composition and delegation but solve different problems.
3. **Complementary:** Patterns can work together to provide a larger solution. Example: Composite and Iterator can be combined to traverse a tree structure.
4. **Alternative:** Different patterns may provide alternative approaches to a design problem. Example: Strategy and Template Method support algorithm variation in different ways.
5. **Combination:** Several patterns can be combined to design a flexible system.

**Conclusion:** Understanding pattern relationships helps designers select and combine suitable patterns.

## Q16. What is a Pattern? Discuss Pattern Categories in detail. [1 Mark]

A **Pattern** is a reusable and proven solution to a commonly occurring problem in a particular context. It describes a general approach rather than a complete implementation.

### Categories
- **Creational:** Deal with object creation. Examples: Factory Method, Abstract Factory, Singleton, Builder and Prototype.
- **Structural:** Deal with class and object composition. Examples: Adapter, Bridge, Composite, Decorator, Facade, Proxy and Flyweight.
- **Behavioral:** Deal with object interaction and responsibility distribution. Examples: Observer, Strategy, Command, Iterator, Mediator, State and Visitor.

**Conclusion:** Patterns provide reusable solutions, and the three major categories address creation, composition and interaction.

## Q17. Define Idioms. What can Idioms provide? Where can Idioms be found? [1 Mark]

**Idioms** are low-level, language-specific patterns that describe commonly used solutions to recurring programming problems.

### What Idioms Provide
1. Reusable implementation techniques.
2. Effective use of programming-language features.
3. Consistent coding style.
4. Clearer and more maintainable code.
5. Practical guidance for common implementation problems.

### Where Idioms Can Be Found
1. Programming-language documentation.
2. Programming books and language references.
3. Source-code libraries and open-source projects.
4. Experienced programmers' practices.
5. Tutorials, technical articles and developer communities.

**Example:** RAII in C++ uses object construction and destruction to manage resource lifetime.

**Conclusion:** Idioms provide language-specific implementation techniques and can be learned from documentation, books, libraries, source code and experienced programmers.

## Q18. Explain the Counted Pointer example in detail. [1 Mark]

A **Counted Pointer** is an idiom for managing dynamically allocated memory by maintaining a reference count for an object. It tracks how many counted pointers refer to the same object. The object is deleted when the count reaches zero.

### Working
1. **Object Creation:** Create an object and initialize its reference count to 1.
2. **Pointer Copying:** When another counted pointer refers to the object, increment the count.
3. **Pointer Assignment:** Decrement the old object's count and increment the new object's count.
4. **Pointer Destruction:** Decrement the count when a counted pointer is destroyed.
5. **Memory Deallocation:** Delete the object when its count reaches zero.

### Example
Suppose P1, P2 and P3 refer to Object A:
- P1 refers to A: count = 1.
- P2 refers to A: count = 2.
- P3 refers to A: count = 3.
- P1 is destroyed: count = 2.
- P2 is destroyed: count = 1.
- P3 is destroyed: count = 0; A can be deleted.

### Advantages
- Automates object lifetime management.
- Allows shared ownership.
- Reduces some causes of memory leaks.

### Limitations
- Reference counting introduces processing and memory overhead.
- Circular references can prevent the count from reaching zero.
- Copying, assignment and destruction must be implemented correctly.

**Conclusion:** Counted Pointer manages shared dynamically allocated objects using reference counting and deletes an object when no counted pointers refer to it.

---

## Supplementary Syllabus Answers

For additional syllabus coverage of Pattern Description, Idioms and Style, and Exemplar, refer to [Supplementary Syllabus Answers](Supplementary-Syllabus-Answers.md).
