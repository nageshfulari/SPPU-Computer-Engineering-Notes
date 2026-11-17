# Unit VI – Additional Syllabus Answers

**Subject:** Object Oriented Modeling and Design (410244(D))  
**Unit:** VI – Design Pattern  
**Purpose:** Supplementary coverage for syllabus concepts not separately represented in the 18 supplied questions.

> These are supplementary syllabus answers, not additional previous-year questions. They are kept separate so the original question wording, order, marks and frequency labels remain unchanged.

## S1. Explain Pattern Description.

A **Pattern Description** is a structured way of documenting a design pattern so that developers can understand its purpose, structure, implementation and application.

A design pattern description generally contains the following elements:

1. **Pattern Name:** A meaningful name used to identify the pattern.
2. **Intent:** Explains the purpose and objective of the pattern.
3. **Motivation:** Describes a practical situation that explains why the pattern is required.
4. **Applicability:** Specifies the situations in which the pattern can be applied.
5. **Structure:** Shows the arrangement of classes and objects, usually through a UML diagram.
6. **Participants:** Identifies the classes and objects involved in the pattern.
7. **Collaborations:** Explains how the participants communicate and work together.
8. **Consequences:** Describes the benefits, limitations and trade-offs of applying the pattern.
9. **Implementation:** Explains important considerations for implementing the pattern.
10. **Known Uses:** Provides examples of systems in which the pattern is used.
11. **Related Patterns:** Describes relationships with other design patterns.

**Importance:** Pattern description provides a common documentation format. It makes patterns easier to understand, compare, communicate and reuse.

**Conclusion:** A pattern description documents the purpose, applicability, structure, participants, collaborations and consequences of a pattern in a standard format.

## S2. Explain Idioms and their relationship with Programming Style.

An **Idiom** is a low-level, language-specific programming pattern that describes a commonly used technique for solving a recurring implementation problem.

### Idioms and Style

1. Idioms are closely related to the features and conventions of a programming language.
2. They demonstrate appropriate use of language constructs such as classes, inheritance, pointers, constructors and destructors.
3. Following established idioms promotes a consistent programming style.
4. Idioms help programmers write code that is easier for other developers familiar with that language to understand.
5. The same design solution may require different idioms in different programming languages.

### Example – RAII in C++

Resource Acquisition Is Initialization (RAII) is a C++ idiom in which resources are acquired during object construction and released automatically when the object is destroyed.

For example, a file-handling object can open a file in its constructor and close it in its destructor. This supports reliable resource management.

**Importance:** Idioms connect general design principles with practical programming-language techniques and encourage consistent, readable and maintainable code.

**Conclusion:** Idioms are language-specific implementation techniques that help programmers use language features effectively and follow a consistent coding style.

## S3. Explain a Design Pattern for a suitable system (Exemplar).

An **Exemplar** is a practical example that demonstrates how a design pattern can be applied to solve a real-world software design problem.

### Example: Strategy Pattern in an Online Shopping System

**Problem:** An online shopping application supports different payment methods, such as Credit Card, UPI and Net Banking. Implementing all payment algorithms inside one class makes the code difficult to maintain and extend.

**Solution:** Apply the Strategy Design Pattern. Each payment algorithm is implemented in a separate class that follows a common interface.

### Participants

1. **PaymentStrategy:** Common interface defining the payment operation.
2. **CreditCardPayment:** Implements payment using a credit card.
3. **UPIPayment:** Implements payment using UPI.
4. **NetBankingPayment:** Implements payment using net banking.
5. **PaymentContext:** Maintains the selected payment strategy and delegates payment execution to it.
6. **Customer:** Selects the required payment method.

### Working

1. The customer selects a payment method.
2. The PaymentContext receives the selected strategy.
3. The context invokes the payment operation through the common interface.
4. The selected concrete strategy processes the payment.
5. The payment result is returned to the application.

### Advantages

- New payment methods can be added without changing the existing context.
- Payment algorithms remain independent.
- Reduces tight coupling between the context and payment implementations.
- Improves flexibility and maintainability.

**Conclusion:** The Strategy Pattern provides a flexible way to support multiple payment methods by encapsulating each payment algorithm separately.

### UML Class Diagram

See the editable source: [online-shopping-strategy-exemplar.mmd](diagrams/online-shopping-strategy-exemplar.mmd).
