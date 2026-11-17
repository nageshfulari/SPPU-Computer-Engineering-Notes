# Unit VI – Quick Revision

## Design Pattern Fundamentals
- **Design Pattern:** Reusable, proven solution to a recurring software design problem.
- **Basic elements:** Pattern Name, Problem, Solution, Consequences.
- **Pattern description:** Name, Intent, Motivation, Applicability, Structure, Participants, Collaborations, Consequences, Implementation, Known Uses, Related Patterns.
- **Categories:** Creational (object creation), Structural (composition), Behavioral (interaction).

## Pattern Categories and Examples
- **Creational:** Factory Method, Abstract Factory, Singleton, Builder, Prototype.
- **Structural:** Adapter, Bridge, Composite, Decorator, Facade, Proxy, Flyweight.
- **Behavioral:** Observer, Strategy, Command, Iterator, Mediator, State, Visitor.

## Communication Patterns
- **Forwarder-Receiver:** Separates sending and receiving messages between distributed components.
- **Client-Dispatcher-Server:** Dispatcher locates the appropriate server and forwards client requests.
- **Publisher-Subscriber:** Publishers distribute events to interested subscribers through an event channel.

## Management Patterns
- **Command Processor:** Centralizes receiving, managing and executing commands.
- **View Handler:** Centralizes creation, selection, switching and management of application views.

## Idioms
- **Idiom:** Language-specific, low-level implementation pattern.
- **What idioms provide:** Reusable coding techniques, effective use of language features, consistency and maintainability.
- **Idioms and style:** Idioms express language conventions and promote consistent coding style.
- **Where to find idioms:** Language documentation, programming books, libraries, source code, experienced programmers and developer communities.
- **Counted Pointer:** Maintains a reference count; object is deleted when the count reaches zero. Circular references can prevent deallocation.

## Exemplar
- **Strategy Pattern in online shopping:** PaymentStrategy interface; CreditCardPayment, UPIPayment and NetBankingPayment concrete strategies; PaymentContext delegates payment execution to the selected strategy.
- **Key benefit:** Add or change payment algorithms without changing the context.

## Important Distinctions
| Category | Main concern |
|---|---|
| Creational | How objects are created |
| Structural | How classes and objects are composed |
| Behavioral | How objects communicate and distribute responsibilities |
| Communication | How components exchange messages |
| Management | How application commands and views are managed |
| Idiom | How a language-specific implementation technique is expressed |
