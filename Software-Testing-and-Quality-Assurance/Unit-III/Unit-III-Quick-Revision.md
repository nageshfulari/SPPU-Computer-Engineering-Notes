# Unit III – Quick Revision Notes

**Subject:** Software Testing and Quality Assurance (410245-D)  
**Unit:** III – Test Case Design Techniques

Use this file for last-minute revision. The complete explanations and examples are in [Unit III Complete Answers](./Unit-III-Complete-Answers.md).

---

## 1. Software Testing Methodologies

| Methodology | Key idea | Main focus |
|---|---|---|
| White Box Testing | Internal code and structure are examined. | Statements, branches, conditions, paths and loops |
| Black Box Testing | Software is tested without examining internal code. | Inputs, outputs and requirements |
| Grey Box Testing | Testing uses partial knowledge of internal design or implementation. | Interfaces, data flow and behaviour with partial internal knowledge |

**Memory aid:** White = internal code; Black = external behaviour; Grey = partial internal knowledge.

## 2. Static Testing Techniques

Static Testing examines documents or code without executing the software.

| Technique | Remember |
|---|---|
| Informal Review | Unstructured feedback; no fixed procedure |
| Walkthrough | Author explains the work product step by step |
| Technical Review | Technical reviewers evaluate correctness and standards |
| Inspection | Formal review with defined roles, defect recording and follow-up |

**Inspection sequence:** Planning → Overview → Individual Preparation → Inspection Meeting → Rework → Follow-up.

## 3. Dynamic Testing

Dynamic Testing executes software using test inputs and checks actual results.

### Structural / White Box Techniques

| Technique | What is measured or checked |
|---|---|
| Statement Coverage | Executable statements run at least once |
| Branch Coverage | Decision outcomes, such as True and False |
| Path Coverage | Different execution paths |
| Conditional Coverage | Each Boolean condition evaluates True and False |
| Loop Coverage | Loop behaviour for different iteration counts and boundaries |

**Formulas:**

Statement Coverage (%) = (Executed Executable Statements / Total Executable Statements) × 100

Branch Coverage (%) = (Executed Branches / Total Branches) × 100

**Important:** 100% statement coverage does not guarantee 100% branch coverage or path coverage. 100% condition coverage does not automatically guarantee all combinations of conditions or all paths.

### Black Box Techniques

| Technique | Key idea |
|---|---|
| Boundary Value Analysis (BVA) | Test values at and around input limits |
| Equivalence Class Partitioning (ECP) | Divide inputs into valid/invalid classes; select representatives |
| State Transition Testing | Test states, events and transitions |
| Cause Effect Graphing | Map input causes to output effects using logical relationships |
| Decision Table Testing | Test combinations of conditions and resulting actions |
| Use Case Testing | Derive tests from user goals and workflows |

### Experience-Based Techniques

- **Error Guessing:** Predict likely defects from experience.
- **Exploratory Testing:** Learn, design tests and execute them iteratively.

## 4. Integration Testing Approaches

| Approach | Direction | Key support |
|---|---|---|
| Big Bang | All modules integrated at once | No specific stub/driver strategy inherent |
| Top-Down | High-level to low-level | Stubs |
| Bottom-Up | Low-level to high-level | Drivers |
| Sandwich / Hybrid | Top and bottom levels together | Stubs and drivers |

**Unit Testing:** Tests an individual component in isolation.  
**Integration Testing:** Tests interaction and interfaces between combined modules.

## 5. Testing Levels

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

- **Unit:** Individual function, class or module.
- **Integration:** Interaction between modules.
- **System:** Complete integrated application.
- **Acceptance / UAT:** User or customer verifies business acceptance criteria.

## 6. Regression Testing

Regression Testing checks that code changes, bug fixes or new features have not adversely affected existing functionality.

**When used:** New features, code changes, bug fixes, integrations, configuration or environment changes.

**Remember:** Regression = check old functionality after change. Retesting = test a specific defect again after it is fixed.

## 7. Functional vs Non-Functional Testing

- **Functional:** What the system does; verifies features and business requirements.
- **Non-Functional:** How well the system operates; verifies performance, security, reliability, compatibility and other quality attributes.

### Functional examples
Unit, Integration, System, User Acceptance, Smoke, Sanity, Regression and Retesting.

### Non-Functional examples
Performance, Memory, Scalability, Compatibility, Security, Cookies, Session, Recovery, Installation, Adhoc, Risk-Based, I18N, L10N and Compliance Testing.

## 8. Non-Functional Topics

| Topic | Key purpose |
|---|---|
| Performance | Speed, response time, throughput and stability under workload |
| Memory | Memory consumption, leaks and memory-related failures |
| Scalability | Ability to handle increasing workload or users |
| Compatibility | Correct operation across supported browsers, devices, OS and environments |
| Security | Protection against unauthorized access and vulnerabilities |
| Cookies | Correct cookie creation, storage, attributes, expiry and deletion |
| Session | Correct session creation, maintenance, timeout and termination |
| Recovery | Ability to recover after crashes, failures or interruptions |
| Installation | Correct installation, upgrade, configuration and uninstallation |
| Adhoc | Informal exploration without predefined test cases |
| Risk-Based | Prioritize tests according to failure probability and impact |
| I18N | Internationalization; design support for different languages and regions |
| L10N | Localization; adapt software to a particular locale |
| Compliance | Verify conformance to applicable laws, regulations, standards or policies |

## 9. Performance Testing Types

- **Load:** Expected or specified workload.
- **Stress:** Beyond normal operating limits; observe failure and recovery behaviour.
- **Spike:** Sudden increase or decrease in workload.
- **Endurance:** Sustained workload over a long duration.
- **Scalability:** Ability to handle increasing workload as capacity or resources change.

## 10. Cookies Testing

- **Session Cookie:** Generally associated with a browser session.
- **Persistent Cookie:** Has a configured expiry or lifetime.
- Check creation, storage, access, update, expiry, deletion and security attributes.
- Security attributes include Secure, HttpOnly and SameSite where appropriate.

## 11. Risk-Based Testing

Risk is assessed using likelihood and impact.

A simple prioritization model:

Risk Score = Probability Rating × Impact Rating

The rating scale must be defined for the project. Test high-risk features first.

## 12. Adhoc Testing

- Informal and flexible.
- No predefined test cases required.
- Uses tester knowledge and intuition.
- Buddy Testing and Pair Testing are collaborative forms often discussed with Adhoc Testing.
- Monkey Testing uses random inputs/actions and is one form of random testing.

## 13. Selenium – Additional Answer / Unit V Topic

Selenium is an open-source suite for browser automation.

| Component | Key role |
|---|---|
| Selenium IDE | Record-and-playback |
| Selenium WebDriver | Programmatic browser automation |
| Selenium Grid | Distributed and parallel test execution |
| Selenium RC | Historical component, replaced by WebDriver in modern usage |

**Syllabus placement:** Selenium belongs to Unit V in the supplied official STQA syllabus. It is retained in the Unit III answer file only because it was requested during this preparation session.

---

## Final Revision Checklist

- [ ] White Box, Black Box and Grey Box Testing
- [ ] Informal Reviews, Walkthroughs, Technical Reviews and Inspection
- [ ] Statement, Branch, Path, Conditional and Loop Coverage
- [ ] BVA and Equivalence Class Partitioning
- [ ] State Transition, Cause Effect, Decision Table and Use Case Testing
- [ ] Error Guessing and Exploratory Testing
- [ ] Unit, Integration, System and Acceptance Testing
- [ ] Smoke, Sanity, Regression and Retesting
- [ ] Performance, Memory, Scalability, Compatibility and Security Testing
- [ ] Cookies, Session, Recovery and Installation Testing
- [ ] Adhoc, Risk-Based, I18N, L10N and Compliance Testing
- [ ] Manual Testing – Online Marketing Software Platform case study
- [ ] Decision Table – online transfer to an already added and approved account

**Reminder:** A topic's absence from the supplied PYQs does not remove it from the official syllabus.
