# Unit III – Complete Exam-Ready Answers

**Subject:** Software Testing and Quality Assurance (410245-D)  
**University:** Savitribai Phule Pune University  
**Course:** Fourth Year Computer Engineering, 2019 Pattern  
**Unit:** III – Test Case Design Techniques

Answers are organized for university writing and follow the marks indicated in the supplied question set. Plain-text formulas and hand-reproducible diagrams are used.

---

## Q1. Explain Performance Testing with its uses and a suitable example. [6 Marks]

### 1. Performance Testing

Performance Testing is a type of Non-Functional Testing used to evaluate the speed, responsiveness, stability, scalability and reliability of a software application under a particular workload.

It checks whether the application performs efficiently when users access it and when the system handles different amounts of work.

### 2. Objectives / Uses

1. **Measures Response Time:** Checks how quickly the application responds to user requests.
2. **Measures Throughput:** Determines the number of transactions or requests processed in a given time.
3. **Identifies Bottlenecks:** Finds slow database queries, memory problems, CPU overload and network delays.
4. **Checks Stability:** Verifies whether the application remains stable during continuous usage.
5. **Evaluates Scalability:** Checks whether the system can handle an increase in users or workload.
6. **Improves User Experience:** Helps prevent slow responses, failures and application crashes.

### 3. Types of Performance Testing

- **Load Testing:** Checks system behaviour under expected or specified user load.
- **Stress Testing:** Checks the system beyond normal operating limits to identify its breaking point and failure behaviour.
- **Spike Testing:** Checks behaviour when workload suddenly increases or decreases.
- **Endurance Testing:** Checks system stability under sustained load for a long duration.
- **Scalability Testing:** Evaluates the system's ability to handle increasing workload by adding resources or capacity.

### 4. Example

Consider an online shopping application expected to support 1,000 simultaneous users.

The tester simulates users performing login, product search, adding products to the cart and making payments. The tester records response time, transaction throughput, CPU usage and memory usage.

**Expected Result:** The application should process the expected workload within the defined response-time limits, maintain correct transactions and avoid crashes or data loss.

### Conclusion

Performance Testing evaluates the speed, stability and scalability of software under different workloads. It helps identify performance bottlenecks, improve reliability and ensure a satisfactory user experience.

---

## Q2. Explain White Box Testing and Black Box Testing. Differentiate between them. [6 Marks]

### 1. White Box Testing

White Box Testing is a software testing technique in which the internal structure, source code, logic and execution flow of a program are examined. The tester has knowledge of the internal implementation.

It is also called Structural Testing or Glass Box Testing.

**Features:**
1. Examines source code and internal program structure.
2. Tests statements, branches, conditions, loops and execution paths.
3. Requires programming and code knowledge.
4. Helps identify logical errors and coding defects.
5. Commonly used during unit-level testing.

**Techniques:** Statement Coverage, Branch Coverage, Path Coverage, Condition Coverage and Loop Coverage.

**Example:** A tester examines an if-else program and designs inputs to execute both the True and False branches.

### 2. Black Box Testing

Black Box Testing is a software testing technique in which the external functionality of an application is tested without examining its internal source code or implementation.

The tester provides inputs and compares actual outputs with expected results.

It is also called Functional Testing or Behavioural Testing in common testing terminology.

**Features:**
1. Focuses on external software functionality.
2. Does not require knowledge of source code.
3. Checks whether requirements are satisfied.
4. Identifies missing functions, incorrect outputs and interface defects.
5. Commonly used in functional and system testing.

**Techniques:** Equivalence Class Partitioning, Boundary Value Analysis, Decision Table Testing, State Transition Testing and Use Case Testing.

**Example:** A tester enters valid and invalid usernames and passwords on a login page and verifies the displayed results without viewing the code.

### 3. Difference Between White Box and Black Box Testing

| White Box Testing | Black Box Testing |
|---|---|
| Tests internal code, logic and structure. | Tests external functionality and behaviour. |
| Requires knowledge of source code. | Does not require source-code knowledge. |
| Focuses on how the software works. | Focuses on what the software does. |
| Examines statements, branches, conditions and paths. | Examines inputs, outputs and functional requirements. |
| Commonly performed by developers or code-aware testers. | Commonly performed by software testers. |
| Often applied at unit level. | Often applied at functional and system levels. |
| Examples: Statement and Branch Coverage. | Examples: BVA and Equivalence Class Partitioning. |

### Conclusion

White Box Testing verifies the internal code and logic of software, whereas Black Box Testing verifies its external functionality. Both are important for detecting defects and improving software quality.

---

## Q3. Explain Static Testing Techniques: Informal Reviews, Walkthroughs, Technical Reviews and Inspection. [6 Marks]

### 1. Static Testing

Static Testing is a testing technique in which software requirements, design documents, source code or other work products are examined without executing the program. It helps identify defects early in development.

### 2. Informal Reviews

An Informal Review is an unstructured examination of a document or code by colleagues or team members.

**Features:**
1. No fixed process or formal roles are required.
2. Work products are shared for feedback.
3. Defects and improvements are discussed informally.
4. Requires less time and documentation.
5. Useful for quick feedback during development.

**Example:** A developer asks a colleague to review a function and suggest improvements.

### 3. Walkthroughs

A Walkthrough is a review technique in which the author explains a document, design or code step by step to other participants to obtain feedback and identify defects.

**Features:**
1. The author generally leads the walkthrough.
2. The work product is explained step by step.
3. Participants ask questions and provide suggestions.
4. Helps identify missing requirements and logical errors.
5. Encourages knowledge sharing among team members.

**Example:** A developer explains the login-module logic to colleagues and discusses possible incorrect conditions.

### 4. Technical Reviews

A Technical Review is a systematic examination of a software work product by technically qualified people to evaluate correctness, technical quality and compliance with standards.

**Features:**
1. Conducted by technically skilled reviewers.
2. Evaluates technical accuracy and design decisions.
3. Checks compliance with technical standards.
4. Identifies defects and possible improvements.
5. Helps improve maintainability and technical quality.

**Example:** Senior developers review a database design to check relationships, constraints and technical requirements.

### 5. Inspection

Inspection is a formal and structured review technique used to identify defects in requirements, design documents or source code. It follows a defined procedure and assigns responsibilities to participants.

**Features:**
1. Follows a formal review process.
2. A moderator coordinates the inspection.
3. Reviewers prepare by examining the work product.
4. Defects are recorded and classified.
5. Follow-up checks whether identified defects have been corrected.

**Typical Inspection Process:**

~~~text
Planning
   |
   v
Overview
   |
   v
Individual Preparation
   |
   v
Inspection Meeting
   |
   v
Rework / Defect Correction
   |
   v
Follow-up
~~~

**Example:** A team formally inspects an SRS document to identify incomplete, ambiguous or inconsistent requirements.

### 6. Summary of Techniques

| Technique | Main Characteristic |
|---|---|
| Informal Review | Unstructured feedback without a fixed procedure. |
| Walkthrough | Author explains the work product step by step. |
| Technical Review | Technically qualified reviewers evaluate correctness and standards. |
| Inspection | Formal review with defined roles, procedure and defect records. |

### Conclusion

Static Testing identifies defects without executing software. Informal Reviews, Walkthroughs, Technical Reviews and Inspections help detect problems early and improve software quality.

---

## Q4. Explain Unit Testing and Integration Testing. Discuss different approaches used in Integration Testing. [6 Marks]

### 1. Unit Testing

Unit Testing is a level of testing in which an individual software component, such as a function, method, class or module, is tested independently to verify that it works correctly.

**Features:**
1. Tests individual modules separately.
2. Usually performed by developers.
3. Helps detect defects early.
4. Makes debugging easier because the tested unit is isolated.
5. Stubs or drivers may be used to simulate dependencies.

**Example:** Testing a function that calculates an account balance with different deposit and withdrawal values.

### 2. Integration Testing

Integration Testing is a level of testing in which two or more individually tested modules are combined and tested to verify their interaction, interfaces and data exchange.

**Features:**
1. Tests communication between integrated modules.
2. Detects interface and data-flow defects.
3. Verifies that combined components work together.
4. Performed after Unit Testing.
5. Helps identify errors that may not appear when modules are tested separately.

**Example:** Integrating Login, Account Details and Fund Transfer modules and verifying that account information is correctly used during a transaction.

### 3. Approaches Used in Integration Testing

**1. Big Bang Integration Testing**

All or most modules are integrated at once and then tested as a complete system.

- Integration is performed after the modules are developed.
- Simple for small applications.
- Defects can be difficult to isolate because many modules are combined simultaneously.

**Example:** Integrating Login, Product Search, Cart, Payment and Order modules together and testing the complete application.

**2. Top-Down Integration Testing**

Testing starts with the top-level module and gradually integrates lower-level modules.

- High-level modules are tested first.
- Lower-level modules are added step by step.
- Stubs simulate lower-level modules that are not yet available.
- Helps test high-level control and design early.

**Example:** Testing the main banking module first and using stubs for account and transaction services that are not yet ready.

**3. Bottom-Up Integration Testing**

Testing starts with low-level modules and gradually integrates higher-level modules.

- Low-level modules are tested first.
- Higher-level modules are added step by step.
- Drivers simulate higher-level modules that are not yet available.
- Helps detect defects in low-level components early.

**Example:** Testing database and transaction-processing modules first, then integrating them with account-management modules using drivers.

**4. Sandwich / Hybrid Integration Testing**

It combines Top-Down and Bottom-Up Integration Testing.

- Testing proceeds from both higher and lower levels.
- The two groups are integrated toward the middle.
- Stubs and drivers may be used.
- Useful for large systems with multiple layers.

### 4. Comparison of Integration Approaches

| Approach | Direction | Supporting Component |
|---|---|---|
| Big Bang | All modules integrated together | No specific stubs or drivers required by the approach |
| Top-Down | Top-level to lower-level | Stubs |
| Bottom-Up | Lower-level to top-level | Drivers |
| Sandwich / Hybrid | Top and bottom levels in parallel | Stubs and drivers |

### Conclusion

Unit Testing verifies individual modules, whereas Integration Testing verifies interaction between modules. Big Bang, Top-Down, Bottom-Up and Sandwich approaches help identify interface and communication defects.

---

## Q5. Explain Statement Coverage and Branch Coverage Testing. [6 Marks]

### 1. Statement Coverage Testing

Statement Coverage is a White Box Testing technique that measures the percentage of executable statements executed at least once by a set of test cases.

**Formula:**

Statement Coverage (%) = (Number of Executed Executable Statements / Total Executable Statements) × 100

**Features:**
1. Checks whether executable statements are run.
2. Identifies statements that are not executed.
3. Requires access to or knowledge of source code.
4. Does not guarantee that every decision outcome is tested.
5. Helps identify untested code.

**Example:**

~~~python
a = 10
b = 5

if a > b:
    print("A is greater")
else:
    print("B is greater")

print("End")
~~~

For input a = 10 and b = 5, the True branch executes. The else-branch print statement does not execute. If the six executable statements are counted as the two assignments, the if decision, two print statements and final print, five of six are executed.

Statement Coverage = (5 / 6) × 100 = 83.33%

### 2. Branch Coverage Testing

Branch Coverage is a White Box Testing technique that measures the percentage of decision outcomes executed by test cases.

For an if-else decision, the True and False outcomes are the two branches.

**Formula:**

Branch Coverage (%) = (Number of Executed Branches / Total Branches) × 100

**Features:**
1. Checks decision outcomes.
2. Tests True and False outcomes of decisions.
3. Requires knowledge of program logic.
4. Identifies untested branches.
5. Provides stronger decision-outcome testing than statement coverage alone.

**Example:** For the same program:

- Test Case 1: a = 10, b = 5 → True branch.
- Test Case 2: a = 3, b = 5 → False branch.

Both branches execute.

Branch Coverage = (2 / 2) × 100 = 100%

### 3. Difference Between Statement and Branch Coverage

| Statement Coverage | Branch Coverage |
|---|---|
| Measures executable statements executed. | Measures decision branches executed. |
| Focuses on program statements. | Focuses on decision outcomes. |
| Requires every executable statement to run at least once. | Requires every branch outcome to run at least once. |
| May leave a decision outcome untested. | Covers all outcomes of the decisions included in the test. |
| Can be achieved without testing every branch. | Usually requires test cases for each branch outcome. |
| Example: Execute assignment and print statements. | Example: Execute both True and False outcomes of an if-else. |

### Conclusion

Statement Coverage checks execution of program statements, whereas Branch Coverage checks decision outcomes. Both are White Box Testing techniques used to measure code coverage and identify untested logic.

---

## Q6. Explain Regression Testing and its importance. [6 Marks]

### 1. Regression Testing

Regression Testing is a software testing technique used to verify that changes made to an existing application, such as bug fixes, modifications or new features, have not adversely affected previously working functionality.

It ensures that existing features continue to work correctly after software changes.

**Example:** When a new payment option is added to an online shopping application, regression testing checks that login, product search, cart operations and existing payment methods still work correctly.

### 2. Process of Regression Testing

~~~text
Existing Software
       |
       v
Make Code Changes
       |
       v
Select Relevant Test Cases
       |
       v
Execute Regression Tests
       |
       v
Compare Actual and Expected Results
       |
       v
Fix Defects and Re-test
~~~

### 3. Importance of Regression Testing

1. **Maintains Existing Functionality:** Ensures that previously working features continue to work after changes.
2. **Detects New Defects:** Identifies defects introduced by code modifications or new features.
3. **Verifies Bug Fixes:** Checks that a correction has not created another problem.
4. **Improves Software Quality:** Helps maintain system reliability and stability.
5. **Supports Continuous Development:** Allows frequent updates with reduced risk.
6. **Reduces Maintenance Cost:** Helps identify defects before they become more expensive to fix.
7. **Maintains User Experience:** Ensures that existing user workflows are not unexpectedly affected.

### 4. When is Regression Testing Performed?

- When new features are added.
- When existing code is modified.
- After bug fixes.
- After changes to databases or configurations.
- After integration of modified modules.
- When software is migrated to a new environment.

### Conclusion

Regression Testing verifies that software modifications do not break existing functionality. It helps detect newly introduced defects, maintain stability and improve software quality.

---

## Q7. Discuss Boundary Value Analysis and Equivalence Class Partitioning. [6 Marks]

### 1. Boundary Value Analysis (BVA)

Boundary Value Analysis is a Black Box Testing technique in which test cases are designed using values at and around the boundaries of an input range.

It is based on the observation that defects frequently occur near minimum and maximum limits.

**Features:**
1. Focuses on minimum and maximum limits.
2. Tests values just below, at and just above boundaries.
3. Helps identify incorrect boundary conditions.
4. Reduces the number of test cases compared with testing every possible value.
5. Useful for numeric ranges, age limits and input-length restrictions.

**Example:** An application accepts age from 18 to 60, inclusive.

| Test Case | Input Age | Expected Result |
|---|---:|---|
| 1 | 17 | Invalid |
| 2 | 18 | Valid |
| 3 | 19 | Valid |
| 4 | 59 | Valid |
| 5 | 60 | Valid |
| 6 | 61 | Invalid |

### 2. Equivalence Class Partitioning (ECP)

Equivalence Class Partitioning is a Black Box Testing technique in which input data is divided into groups called equivalence classes. Values in one class are expected to be processed similarly, so a representative value is selected from each class.

**Features:**
1. Divides inputs into valid and invalid classes.
2. Selects representative values from each class.
3. Reduces the number of test cases.
4. Assumes values in the same class behave similarly.
5. Helps identify input-validation defects.

**Example:** An application accepts age from 18 to 60, inclusive.

| Equivalence Class | Input Range | Representative Value | Expected Result |
|---|---|---:|---|
| Valid | 18–60 | 30 | Valid |
| Invalid 1 | Below 18 | 15 | Invalid |
| Invalid 2 | Above 60 | 65 | Invalid |

### 3. Difference Between BVA and ECP

| Boundary Value Analysis | Equivalence Class Partitioning |
|---|---|
| Focuses on input boundaries. | Focuses on groups of equivalent input values. |
| Tests minimum, maximum and nearby values. | Tests representative values from each class. |
| Targets errors near input limits. | Targets errors across different input classes. |
| Requires identification of boundaries. | Requires division of input into classes. |
| Often uses several values around each boundary. | Usually selects one representative per class for basic coverage. |
| Example: 17, 18, 19, 59, 60, 61. | Example: 15, 30 and 65. |

### Conclusion

BVA tests values at and around input boundaries, whereas ECP divides input data into valid and invalid groups and tests representative values. Both techniques reduce test effort and improve test effectiveness.

---

## Q8. Explain System Testing and Acceptance Testing. [6 Marks]

### 1. System Testing

System Testing is a level of testing in which the complete integrated software application is tested as a whole to verify whether it meets specified functional and non-functional requirements.

It is performed after Integration Testing and before Acceptance Testing.

**Features:**
1. Tests the complete integrated application.
2. Verifies whether modules work together correctly.
3. Checks functional and non-functional requirements.
4. Usually performed by an independent testing team.
5. Identifies defects in overall system behaviour.

**Example:** In an online shopping application, system testing checks registration, login, product search, cart, payment, order confirmation and tracking as a complete workflow.

### 2. Acceptance Testing

Acceptance Testing is performed to verify whether the developed software meets business requirements and user expectations. It helps determine whether the software is ready for delivery or deployment.

It is generally performed by customers, end users or their representatives.

**Features:**
1. Verifies business and user requirements.
2. Usually performed by customers or end users.
3. Uses realistic business scenarios.
4. Checks whether acceptance criteria are satisfied.
5. Supports the decision to accept the software for release.

**Types:**
- **User Acceptance Testing (UAT):** End users verify that the application supports their business needs.
- **Alpha Testing:** Selected users or internal testers evaluate the software at the developer's site before external release.
- **Beta Testing:** Selected real users evaluate the software in their own environment before final release.

**Example:** Customers verify that an online shopping application allows them to purchase products, make payments and receive order confirmations as required.

### 3. Difference Between System and Acceptance Testing

| System Testing | Acceptance Testing |
|---|---|
| Tests the complete integrated software system. | Verifies whether software meets user and business needs. |
| Focuses on overall system behaviour and requirements. | Focuses on acceptance criteria and real business use. |
| Usually performed by an independent testing team. | Usually performed by customers or end users. |
| Performed after Integration Testing. | Generally performed after System Testing. |
| Identifies defects in the complete system. | Determines whether the software is acceptable for delivery. |
| Checks functional and non-functional requirements. | Checks whether business requirements are fulfilled. |
| Example: Testing the complete shopping workflow. | Example: Customer validates the shopping workflow against business needs. |

### 4. Position in Testing Levels

~~~text
Unit Testing
     |
     v
Integration Testing
     |
     v
System Testing
     |
     v
Acceptance Testing
~~~

### Conclusion

System Testing verifies the complete integrated application against specified requirements, whereas Acceptance Testing verifies whether the software meets customer expectations and is ready for delivery.

---

## Q9. Explain Selenium. [Additional question – Selenium is in Unit V of the supplied syllabus]

### 1. Introduction

Selenium is an open-source suite of tools used to automate web browsers for testing web applications. It supports programming languages such as Java, Python, C# and JavaScript and is used for browser-based functional and regression testing.

### 2. Features

1. Open-source and freely available.
2. Supports major browsers such as Chrome, Firefox, Edge and Safari.
3. Supports multiple programming languages.
4. Works across operating systems such as Windows, Linux and macOS.
5. Automates browser actions such as clicking, typing and navigation.
6. Can be integrated with frameworks such as JUnit, TestNG and PyTest.

### 3. Components of Selenium

**1. Selenium IDE**
- A browser-based record-and-playback tool.
- Records user interactions and replays them.
- Useful for simple tests and beginners.

**2. Selenium WebDriver**
- Automates browsers through programming-language APIs.
- Interacts with browser elements and performs user actions.
- Suitable for advanced and maintainable automation scripts.

**3. Selenium Grid**
- Runs tests across multiple machines, browsers and environments.
- Supports parallel test execution.
- Helps reduce execution time and supports cross-browser testing.

**4. Selenium RC (Historical Component)**
- Selenium Remote Control was an older component that used a server to execute browser automation commands.
- It has been replaced by WebDriver in modern Selenium usage and is retained here because it appears in the historical Selenium suite terminology used in some course materials.

### 4. Working of Selenium WebDriver

~~~text
Test Script
    |
    v
Selenium WebDriver
    |
    v
Browser Driver / Browser Automation Interface
    |
    v
Web Browser
    |
    v
Web Application
    |
    v
Execution Result
~~~

**Working Steps:**
1. The tester writes an automation script in a supported language.
2. WebDriver receives commands from the script.
3. The browser automation interface sends commands to the browser.
4. The browser performs actions such as clicking, typing and navigation.
5. The test script checks actual behaviour against expected results.

### 5. Applications

- Automating login and registration tests.
- Testing web forms and validations.
- Performing regression testing.
- Performing cross-browser testing.
- Automating repetitive browser-based test cases.

### 6. Advantages and Limitations

**Advantages:**
- Free and open-source.
- Supports multiple browsers and programming languages.
- Reduces repetitive manual effort.
- Supports parallel testing through Grid.
- Integrates with test frameworks.

**Limitations:**
- Primarily designed for web browser automation, not desktop application testing.
- WebDriver automation requires programming knowledge.
- Test reporting and test management generally require additional tools.
- CAPTCHA and some browser-level interactions cannot be reliably automated directly.

### Conclusion

Selenium is a widely used open-source browser automation suite. IDE supports record-and-playback, WebDriver supports programmatic browser automation, and Grid supports distributed and parallel execution. Selenium helps reduce manual effort in web application testing.

---

## Q10. Explain Dynamic Testing Techniques, including Structural Testing Techniques. [6 Marks]

### 1. Dynamic Testing

Dynamic Testing is a software testing technique in which the software is executed with different inputs to verify actual behaviour and compare actual results with expected results.

It helps identify defects that occur during program execution.

**Features:**
1. Requires execution of the program or application.
2. Tests actual application behaviour.
3. Identifies runtime and functional defects.
4. Uses test cases with different inputs.
5. Can be performed manually or using automation.

### 2. Types of Dynamic Testing Techniques

Dynamic Testing techniques include Structural, Black Box and Experience-Based techniques.

### 3. Structural Testing Techniques

Structural Testing examines the internal structure, logic and execution flow of a program. It is a White Box Testing approach.

1. **Statement Coverage:** Measures the percentage of executable statements executed at least once.

   Statement Coverage (%) = (Executed Executable Statements / Total Executable Statements) × 100

2. **Branch Coverage:** Measures the percentage of decision outcomes executed. For an if-else decision, both True and False outcomes are tested.

   Branch Coverage (%) = (Executed Branches / Total Branches) × 100

3. **Path Coverage:** Checks different possible execution paths through the program.

4. **Conditional Coverage:** Verifies that each individual Boolean condition evaluates to both True and False at least once.

5. **Loop Coverage:** Tests loops for different iteration counts and boundary conditions, including zero, one and multiple iterations where applicable.

### 4. Black Box Testing Techniques

Black Box Testing checks external functionality without examining internal source code.

- **Boundary Value Analysis:** Tests values at and around input boundaries.
- **Equivalence Class Partitioning:** Divides inputs into classes and tests representative values.
- **Decision Table Testing:** Tests combinations of conditions and their corresponding actions.
- **State Transition Testing:** Checks system behaviour when events cause transitions between states.
- **Use Case Testing:** Designs tests from user workflows and interactions.
- **Cause Effect Graphing:** Represents logical relationships between input conditions (causes) and outputs (effects) to derive test cases.

### 5. Experience-Based Testing Techniques

These techniques use tester knowledge, experience and intuition.

- **Error Guessing:** Testers predict likely defects based on experience and design tests for error-prone conditions.
- **Exploratory Testing:** Testers learn the application, design tests and execute them in an iterative manner.

### 6. Classification Diagram

~~~text
                 Dynamic Testing
                       |
          +------------+------------+
          |            |            |
          v            v            v
      Structural    Black Box   Experience-Based
       Testing       Testing       Testing
          |            |            |
     Statement       BVA          Error Guessing
     Branch          ECP          Exploratory
     Path            Decision
     Condition       State Transition
     Loop            Use Case
                     Cause Effect
~~~

### Conclusion

Dynamic Testing verifies software by executing it with different inputs. Structural, Black Box and Experience-Based techniques help detect logic errors, functional defects and runtime failures.

---

## Q11. Explain Experience-Based Testing Techniques: Error Guessing and Exploratory Testing. [6 Marks]

### 1. Experience-Based Testing

Experience-Based Testing is a testing approach in which test cases are designed using the tester's knowledge, experience, intuition and understanding of the application.

It is useful for identifying defects that may not be covered by predefined test cases.

**Features:**
1. Uses tester knowledge and experience.
2. Focuses on error-prone areas.
3. Can supplement formal testing techniques.
4. Helps discover defects missed by predefined test cases.
5. Requires observation and judgement by the tester.

### 2. Error Guessing

Error Guessing is an Experience-Based Testing technique in which testers predict likely defects using previous experience and knowledge of common mistakes.

**Features:**
1. Based on tester experience and intuition.
2. Targets likely error-prone conditions.
3. Does not require a fixed formal procedure.
4. Helps identify defects not covered by standard test cases.
5. Often checks invalid inputs and exceptional conditions.

**Example:** For a login page, a tester may check blank username, incorrect password, special characters, very long input and repeated failed login attempts.

### 3. Exploratory Testing

Exploratory Testing is a technique in which learning the application, designing tests and executing tests take place together. The tester explores different functions and adapts further tests based on observations.

**Features:**
1. Testing, learning and test design occur together.
2. Does not depend entirely on predefined test cases.
3. Uses tester creativity and observation.
4. Helps discover unexpected defects.
5. Useful when documentation is incomplete or time is limited.

**Example:** In an online shopping application, the tester explores adding and removing products, changing quantities, applying invalid coupons, refreshing during checkout and navigating between pages.

### 4. Difference Between Error Guessing and Exploratory Testing

| Error Guessing | Exploratory Testing |
|---|---|
| Predicts defects from prior experience. | Explores application behaviour to discover defects. |
| Focuses on suspected error-prone areas. | Can cover a broader range of functionality. |
| Test ideas are based on likely mistakes. | Test ideas evolve while the application is explored. |
| Mainly uses intuition about common failures. | Uses learning, observation, creativity and adaptation. |
| Often targets known or suspected error conditions. | Can reveal unexpected behaviours and defects. |
| Example: Trying blank or invalid login values. | Example: Exploring an entire shopping and checkout workflow. |

### Conclusion

Error Guessing predicts likely defects using experience, whereas Exploratory Testing combines learning, test design and execution. Both help discover defects that predefined test cases may miss.

---

## Q12. Explain Loop Coverage Testing and its types. [6 Marks]

### 1. Loop Coverage Testing

Loop Coverage Testing is a White Box Testing technique used to verify the correctness of loops by executing them for different numbers of iterations.

It checks loop behaviour under conditions such as zero, one, multiple and boundary iterations.

**Features:**
1. Tests loop execution under different iteration conditions.
2. Identifies errors in loop initialization and termination.
3. Checks whether loops execute the expected number of times.
4. Helps detect infinite loops and incorrect loop conditions.
5. Applies to for, while and do-while loops.

### 2. Types of Loop Testing

**1. Simple Loop Testing**
- Tests a single loop.
- Checks zero, one, two, typical and boundary iterations.
- Helps identify errors in loop conditions and termination.
- Example: Testing a loop that prints numbers from 1 to 5.

**2. Nested Loop Testing**
- Tests a loop inside another loop.
- Testing generally starts with the innermost loop while outer loops are kept at suitable minimum values; outer loops are then tested progressively.
- Helps identify errors in nested iteration.
- Example: Testing two loops used to traverse a matrix.

**3. Concatenated Loop Testing**
- Tests two or more loops placed one after another.
- Independent loops can be tested separately.
- Dependent loops should be tested with their dependency in mind.
- Example: One loop calculates a sum and a later loop displays results.

**4. Unstructured Loop Testing**
- Concerns loops with irregular control flow or multiple entry and exit paths.
- Such loops are difficult to test and maintain.
- They should preferably be redesigned into structured loops.
- Example: A loop with irregular jumps and multiple exits.

### 3. Example

~~~python
for i in range(1, 4):
    print(i)
~~~

The loop is expected to execute three times.

| Test Case | Iterations | Expected Behaviour |
|---|---:|---|
| 1 | 0 | Loop body is not executed, if zero iterations are permitted by the setup. |
| 2 | 1 | One iteration occurs. |
| 3 | 2 | Two iterations occur. |
| 4 | 3 | Three iterations occur. |

### 4. Summary

| Type | Description | Example |
|---|---|---|
| Simple | One loop | Print a sequence of values |
| Nested | A loop inside another loop | Matrix traversal |
| Concatenated | Multiple sequential loops | Separate calculation and display loops |
| Unstructured | Irregular loop control flow | Loop with multiple exits |

### Conclusion

Loop Coverage Testing checks loop execution, iteration boundaries, initialization and termination. Simple, Nested, Concatenated and Unstructured Loop Testing address different loop structures.

---

## Q13. Explain Path Coverage and Conditional Coverage Testing. [6 Marks]

### 1. Path Coverage Testing

Path Coverage is a White Box Testing technique that checks different possible execution paths through a program. An execution path is a sequence of statements and branch outcomes followed from program entry to exit.

**Features:**
1. Focuses on program execution paths.
2. Helps identify errors in control flow.
3. Requires knowledge of internal program structure.
4. Test cases are designed to execute selected paths.
5. Complete path coverage may be impractical or impossible in programs with loops or many combinations.

**Example:**

~~~python
a = 10
b = 5

if a > b:
    print("A is greater")
else:
    print("B is greater")

print("End")
~~~

Two paths exist for this simple decision:

- Path 1: True → Print “A is greater” → Print “End”.
- Path 2: False → Print “B is greater” → Print “End”.

| Test Case | Inputs (a, b) | Path |
|---|---|---|
| 1 | (10, 5) | True path |
| 2 | (3, 5) | False path |

Both paths are executed in this example.

### 2. Conditional Coverage Testing

Conditional Coverage is a White Box Testing technique that checks whether each individual Boolean condition in a decision evaluates to both True and False at least once.

**Features:**
1. Focuses on individual Boolean conditions.
2. Requires each condition to take both True and False values.
3. Helps identify errors in logical expressions.
4. Requires knowledge of source code.
5. Does not by itself guarantee complete branch or path coverage.

**Example:**

~~~python
if (a > 10) and (b < 20):
    print("Condition satisfied")
else:
    print("Condition not satisfied")
~~~

Individual conditions:

- Condition A: a > 10
- Condition B: b < 20

| Test Case | a | b | Condition A | Condition B |
|---|---:|---:|---|---|
| 1 | 15 | 25 | True | False |
| 2 | 5 | 10 | False | True |

Each individual condition evaluates to True once and False once. Therefore, the test set achieves 100% condition coverage.

### 3. Difference Between Path and Conditional Coverage

| Path Coverage | Conditional Coverage |
|---|---|
| Tests different execution paths. | Tests individual Boolean conditions. |
| Focuses on program control flow. | Focuses on True and False outcomes of each condition. |
| Test cases execute selected sequences of branches and statements. | Test cases make each condition evaluate both ways. |
| Helps identify control-flow defects. | Helps identify logical-condition defects. |
| Can become difficult with loops and complex paths. | Depends on the number and interaction of Boolean conditions. |
| Example: Execute both paths of an if-else. | Example: Test both outcomes of A and B separately. |

### Conclusion

Path Coverage verifies execution paths, whereas Conditional Coverage verifies the True and False outcomes of individual Boolean conditions. Both are structural White Box Testing techniques.

---

## Q14. Differentiate between Functional Testing and Non-Functional Testing. [6 Marks]

### 1. Functional Testing

Functional Testing verifies whether software functions according to specified functional requirements. It checks what the system does by testing features, operations and expected outputs.

**Examples:** Login, registration, payment processing, Unit Testing, Integration Testing, System Testing, Acceptance Testing, Smoke Testing, Sanity Testing, Regression Testing and Retesting.

### 2. Non-Functional Testing

Non-Functional Testing verifies quality attributes and operating characteristics of software. It checks how well the system works in terms of performance, security, reliability, compatibility and other quality requirements.

**Examples:** Performance, Memory, Scalability, Compatibility, Security, Cookies, Session, Recovery, Installation, Adhoc, Risk-Based, I18N, L10N and Compliance Testing.

### 3. Difference Between Functional and Non-Functional Testing

| Functional Testing | Non-Functional Testing |
|---|---|
| Tests software functions and features. | Tests software quality attributes. |
| Focuses on what the system does. | Focuses on how well the system operates. |
| Verifies functional requirements. | Verifies non-functional requirements. |
| Checks inputs, outputs and business operations. | Checks performance, security, reliability and compatibility. |
| Identifies missing or incorrect functionality. | Identifies quality and operating-condition problems. |
| Examples include login and payment testing. | Examples include performance and security testing. |

### 4. Examples

**Functional:** In an online banking application, verify that a user can log in, view a balance and transfer money correctly.

**Non-Functional:** In the same application, verify that the system can support a specified number of simultaneous users while meeting response-time and security requirements.

### Conclusion

Functional Testing verifies whether software performs required functions correctly, whereas Non-Functional Testing evaluates the quality and efficiency with which it performs.

---

## Q15. Explain Cookies Testing with an example. [6 Marks]

### 1. Cookies Testing

Cookies Testing verifies whether cookies are correctly created, stored, accessed, updated, expired and deleted by a web application.

Cookies are small pieces of data stored by a website in a user's browser. They may be used to maintain sessions, remember preferences and support other website functions.

### 2. Features of Cookies Testing

1. **Cookie Creation:** Checks whether cookies are created when required.
2. **Cookie Storage:** Verifies that cookies are stored correctly in the browser.
3. **Cookie Expiration:** Checks whether cookies expire according to their configured lifetime.
4. **Cookie Deletion:** Verifies that cookies are removed or invalidated when required, such as during logout.
5. **Cookie Security:** Checks attributes such as Secure, HttpOnly and SameSite where applicable.
6. **Cookie Modification:** Verifies that cookie values are updated correctly.

### 3. Types of Cookies

**Session Cookies**
- Usually exist for the duration of a browser session.
- Commonly used for session management.
- Normally removed when the session ends, depending on browser behaviour and implementation.

**Persistent Cookies**
- Have a specified expiry time or lifetime.
- May remain in the browser after it is closed.
- Can be used to remember preferences or other permitted information.

### 4. Example

Consider an online shopping website where a user logs in and adds products to a cart.

| Test Case | Testing Activity | Expected Result |
|---|---|---|
| 1. Cookie Creation | User logs in. | Required session cookie is created. |
| 2. Cookie Storage | Inspect browser cookie storage. | Cookie is stored with expected attributes. |
| 3. Session Maintenance | Navigate between pages. | Valid session is maintained. |
| 4. Expiration | Allow the configured session lifetime to end. | Session is no longer valid. |
| 5. Logout | User logs out. | Session is invalidated; related cookie is cleared or made unusable. |
| 6. Security Attributes | Inspect cookie attributes. | Appropriate Secure, HttpOnly and SameSite settings are applied. |

### 5. Importance

1. Ensures correct session management.
2. Checks that user preferences are handled correctly.
3. Helps identify session-related security weaknesses.
4. Verifies correct expiration and deletion.
5. Improves website reliability and user experience.

### Conclusion

Cookies Testing checks the correct creation, storage, management, expiration and deletion of browser cookies. It supports reliable session management and helps verify cookie security.

---

## Q16. Explain Security Testing and Compatibility Testing. [6 Marks]

### 1. Security Testing

Security Testing is a type of Non-Functional Testing used to identify vulnerabilities and verify that software protects data and resources against unauthorized access and attacks.

It evaluates whether confidentiality, integrity and availability are adequately protected.

**Features:**
1. **Authentication:** Checks whether only valid users can log in.
2. **Authorization:** Verifies that users can access only permitted resources.
3. **Data Protection:** Checks protection of sensitive information.
4. **Vulnerability Detection:** Identifies weaknesses such as SQL Injection and Cross-Site Scripting.
5. **Session Management:** Checks secure creation, use and termination of sessions.
6. **Access Control:** Verifies restrictions on protected operations and data.

**Example:** In online banking, verify that a customer cannot access another customer's account, sensitive information is protected and unauthorized transactions are prevented.

### 2. Compatibility Testing

Compatibility Testing is a type of Non-Functional Testing used to verify that software works correctly across different browsers, operating systems, devices, hardware and environments.

**Features:**
1. **Browser Compatibility:** Checks application behaviour in browsers such as Chrome, Firefox, Edge and Safari.
2. **Operating System Compatibility:** Checks supported operating systems such as Windows, Linux, macOS, Android and iOS.
3. **Device Compatibility:** Checks desktops, laptops, tablets and smartphones.
4. **Hardware Compatibility:** Verifies behaviour with supported hardware configurations.
5. **Network Compatibility:** Checks operation under supported network environments.
6. **Version Compatibility:** Checks behaviour across supported browser or software versions.

**Example:** An online shopping website is tested on different browsers, operating systems and screen sizes to verify that pages, buttons, images and checkout functions work consistently.

### 3. Difference Between Security and Compatibility Testing

| Security Testing | Compatibility Testing |
|---|---|
| Identifies security weaknesses and vulnerabilities. | Checks operation across different environments. |
| Focuses on protecting data and resources. | Focuses on consistent behaviour across platforms. |
| Evaluates confidentiality, integrity and availability. | Evaluates browser, device, OS and environment support. |
| Detects threats such as SQL Injection and XSS. | Detects environment-specific layout and functional issues. |
| Tests authentication, authorization and access control. | Tests browsers, operating systems, hardware and devices. |
| Example: Protecting online banking accounts. | Example: Testing a website on Chrome, Firefox, Android and iOS. |

### Conclusion

Security Testing protects software from vulnerabilities and unauthorized access, whereas Compatibility Testing ensures that software works correctly across supported platforms and environments.

---

## Q17. Explain Risk-Based Testing. [6 Marks]

### 1. Risk-Based Testing

Risk-Based Testing is a testing approach in which testing activities are prioritized according to the risks associated with software features or components.

It focuses more testing effort on areas that have a higher likelihood of failure and/or greater impact if failure occurs.

### 2. Risk Assessment

Risk is commonly assessed using two factors:

- **Probability:** Likelihood that a failure will occur.
- **Impact:** Severity of the consequences if the failure occurs.

A simple prioritization model is:

Risk Score = Probability Rating × Impact Rating

The rating scale must be defined by the project or organization.

| Risk Level | Description | Testing Priority |
|---|---|---|
| High | High likelihood and/or serious impact. | Highest |
| Medium | Moderate likelihood or impact. | Medium |
| Low | Low likelihood and minor impact. | Lower |

### 3. Process of Risk-Based Testing

~~~text
Identify Risks
      |
      v
Analyze Probability and Impact
      |
      v
Evaluate Risk Level
      |
      v
Prioritize Test Areas
      |
      v
Plan and Execute Tests
      |
      v
Monitor and Reassess Risks
~~~

**Steps:**
1. **Risk Identification:** Identify features or components that may fail.
2. **Risk Analysis:** Estimate probability and impact of each risk.
3. **Risk Evaluation:** Assign risk levels using the defined rating method.
4. **Test Planning:** Allocate test effort according to risk priority.
5. **Test Execution:** Test high-risk areas first, followed by other areas.
6. **Risk Monitoring:** Review test results and update priorities when needed.

### 4. Example

Consider an online banking application.

| Module | Possible Risk | Risk Level | Priority |
|---|---|---|---|
| Login | Unauthorized access | High | Highest |
| Fund Transfer | Incorrect transfer or transaction failure | High | Highest |
| Profile Management | Incorrect profile update | Medium | Medium |
| Help Section | Incorrect help information | Low | Lower |

Login and Fund Transfer receive more testing attention because their failure may cause serious security or financial consequences.

### 5. Advantages

1. Prioritizes critical application areas.
2. Uses time and testing resources efficiently.
3. Helps detect high-impact defects early.
4. Reduces the likelihood of serious business failures.
5. Improves confidence in software quality.

### Conclusion

Risk-Based Testing prioritizes testing according to the likelihood and impact of software failures. It helps focus effort on critical areas and reduce business risk before release.

---

## Q18. Explain Adhoc Testing with an example. [6 Marks]

### 1. Adhoc Testing

Adhoc Testing is an informal testing approach performed without predefined test cases or a detailed formal test plan. Testers use their understanding, experience and intuition to explore the application and identify defects.

It is flexible and can complement planned testing. It should not be treated as a replacement for systematic test coverage.

### 2. Features

1. **No Predefined Test Cases:** Testers are not restricted to a prepared set of test cases.
2. **Informal Approach:** It does not follow a fixed formal procedure.
3. **Experience-Based:** Uses tester knowledge and intuition.
4. **Quick Defect Discovery:** May reveal unexpected defects.
5. **Flexible Testing:** Testers can explore different features and conditions.
6. **Limited Documentation:** Test steps may not be documented in detail unless a defect is found.

### 3. Commonly Described Forms

**1. Buddy Testing**
- A developer and tester work together on the same module.
- Combines development and testing knowledge.
- Helps identify defects through collaboration.

**2. Pair Testing**
- Two testers work together on the same application or feature.
- One may perform actions while the other observes and suggests tests.
- Encourages discussion and alternative test ideas.

**3. Monkey Testing**
- Random or unexpected inputs and actions are supplied to the application.
- Helps identify crashes and unexpected behaviour.
- It is one form of random testing and is not a synonym for every type of Adhoc Testing.

### 4. Example

Consider an online shopping application. A tester explores it without predefined test cases:

1. Leaves login fields blank.
2. Clicks Checkout repeatedly.
3. Adds and removes products rapidly.
4. Refreshes the page during checkout.
5. Enters special characters in the search field.
6. Navigates backward during a transaction.

**Expected Behaviour:**
- The application should not crash.
- Invalid inputs should be handled safely.
- Duplicate orders or payments should not be created.
- Cart information should remain consistent.
- Unexpected navigation should not corrupt transaction data.

If unexpected behaviour occurs, the tester records and reports the defect.

### 5. Advantages

1. Requires less preparation.
2. May reveal unexpected defects.
3. Allows flexible exploration.
4. Can supplement formal test cases.
5. Useful for quick investigation of suspicious areas.

### 6. Limitations

1. Depends heavily on tester skill.
2. Test coverage is difficult to measure.
3. Defects may be difficult to reproduce without notes.
4. Important scenarios may be missed.
5. Results may be inconsistent between testers.

### Conclusion

Adhoc Testing is an informal and flexible approach that uses tester experience to discover defects without relying on predefined test cases. It is useful as a supplement to systematic testing.
