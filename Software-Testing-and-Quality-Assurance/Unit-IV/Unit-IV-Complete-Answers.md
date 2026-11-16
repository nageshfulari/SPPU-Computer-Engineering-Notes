# Unit IV – Complete Exam-Ready Answers

**Subject:** Software Testing and Quality Assurance (410245-D)  
**University:** Savitribai Phule Pune University  
**Course:** Fourth Year Computer Engineering, 2019 Pattern  
**Unit:** IV – Software Quality Assurance and Quality Control

Answers are organized for university writing and follow the marks shown in the supplied question set. Language is simple and technical. Diagrams are kept easy to reproduce by hand.

---

## Q1. Explain why software has defects. Discuss the causes of software defects. [5–6 Marks]

### 1. Introduction

A software defect is an error or fault in a software product that causes it to produce incorrect or unexpected results or fail to meet specified requirements.

Software defects occur because software development involves human activities such as requirement analysis, design, coding and testing. Mistakes at any stage can introduce defects into the final product.

### 2. Why Does Software Have Defects?

1. Software development is complex and involves many components and interactions.
2. Requirements may be incomplete, unclear or frequently changing.
3. Developers may misunderstand customer requirements.
4. Errors can occur during design, coding and integration.
5. Communication gaps may exist between customers, developers and testers.
6. Insufficient testing may allow defects to remain undetected.
7. Time and budget constraints may force teams to compromise on quality.

### 3. Causes of Software Defects

1. **Incorrect or Incomplete Requirements:** Requirements may be ambiguous, missing or misunderstood. Example: a banking application has an incorrectly specified transaction limit.
2. **Communication Gaps:** Poor communication between customers, developers, designers and testers can cause requirements to be misunderstood.
3. **Design Errors:** Errors in architecture, database design or system structure can create performance and reliability problems.
4. **Programming or Coding Errors:** Logical mistakes, incorrect conditions, loops and data handling can produce unexpected results.
5. **Complexity of Software:** Large systems contain interconnected modules and dependencies. A change in one module may affect another.
6. **Frequent Requirement Changes:** Improperly implemented changes can introduce new defects and affect existing functionality.
7. **Insufficient Testing:** Inadequate test cases, test data or testing time may leave defects undetected.
8. **Time and Budget Constraints:** Rushed development may lead to skipped reviews, poor documentation or insufficient testing.

### 4. Conclusion

Software defects arise due to mistakes in requirements, design, coding, communication and testing. Proper requirement analysis, design reviews, coding standards, continuous testing and quality assurance help reduce defects and improve product quality.

---

## Q2. Explain ISO 9000 / ISO 9001 Quality Standards and their importance in Software Testing. [5–6 Marks]

### 1. Introduction

ISO stands for International Organization for Standardization. It develops international standards to support quality, safety, efficiency and consistency in products and services.

The ISO 9000 family provides fundamentals and guidance for Quality Management Systems (QMS). ISO 9001 specifies requirements for a QMS and is the standard in this family against which an organization can be certified.

### 2. Important Standards in the ISO 9000 Family

1. **ISO 9000:** Explains the fundamentals and vocabulary of Quality Management Systems.
2. **ISO 9001:** Specifies requirements for establishing, implementing, maintaining and continually improving a QMS.
3. **ISO 9004:** Provides guidance for improving organizational performance and achieving sustained success.
4. **ISO 19011:** Provides guidelines for auditing management systems.

### 3. Principles of Quality Management

1. Customer Focus – understand and satisfy customer requirements.
2. Leadership – management establishes direction and quality objectives.
3. Engagement of People – employees participate in quality improvement.
4. Process Approach – manage activities as interconnected processes.
5. Improvement – continually improve products and processes.
6. Evidence-Based Decision Making – use data and measurements for decisions.
7. Relationship Management – maintain effective relationships with stakeholders and suppliers.

### 4. Importance of ISO 9001 in Software Testing

1. **Improves Software Quality:** Encourages systematic processes for software development and testing.
2. **Standardizes Processes:** Supports documented and repeatable testing and quality procedures.
3. **Supports Defect Prevention:** Encourages reviews, process monitoring and corrective actions.
4. **Improves Documentation:** Promotes controlled records such as test plans, test results and quality reports.
5. **Increases Customer Satisfaction:** Helps the organization consistently meet specified customer and applicable regulatory requirements.
6. **Supports Continuous Improvement:** Audits, feedback and performance evaluation help improve processes.
7. **Improves Confidence:** Consistent development and testing practices increase confidence in the organization's quality system.

### 5. Simple QMS Process

Customer requirements → Quality Management System → Software development and testing → Evaluation and audit → Corrective action and continual improvement.

### 6. Conclusion

ISO 9000 provides QMS fundamentals and vocabulary, while ISO 9001 specifies QMS requirements. These standards help software organizations establish consistent processes, improve testing practices, reduce process-related defects and increase customer satisfaction.

**Important point:** ISO 9001 certification demonstrates that an organization's QMS meets the standard's requirements within its certified scope. It does not guarantee that every software product is defect-free.

---

## Q3. Explain different levels of Capability Maturity Model (CMM) and its limitations. [5–6 Marks]

### 1. Introduction

The Capability Maturity Model (CMM) is a framework developed by the Software Engineering Institute (SEI) to assess and improve the maturity of an organization's software development processes.

It describes five maturity levels, progressing from unpredictable processes to continuous process improvement.

### 2. Five Levels of CMM

**Level 1 – Initial**
- Processes are informal, unpredictable and poorly controlled.
- Success depends mainly on individual effort.
- Cost and schedule overruns may occur.

**Level 2 – Repeatable**
- Basic project management practices are established.
- Earlier successful project practices can be repeated.
- Project planning, tracking and requirement management are performed.

**Level 3 – Defined**
- Processes are documented, standardized and integrated across the organization.
- Common procedures and guidelines are followed.
- Training supports consistent implementation.

**Level 4 – Managed**
- Processes are measured and controlled using quantitative techniques.
- Metrics are used to monitor quality and process performance.
- Variations in performance are identified and controlled.

**Level 5 – Optimizing**
- Focuses on continuous process improvement.
- Defect prevention and process innovation are encouraged.
- Feedback and measurement are used to improve processes.

### 3. Limitations of CMM

1. **Time Consuming:** Establishing and improving processes may take considerable time.
2. **High Cost:** Training, documentation and assessment require resources.
3. **Documentation Overhead:** Extensive process documentation may increase administrative work.
4. **Not Suitable for Every Organization:** Small organizations may find implementation difficult with limited resources.
5. **No Guarantee of Product Quality:** A high maturity level does not automatically guarantee defect-free software.
6. **Resistance to Change:** Employees may resist new procedures and standardized practices.
7. **Process Focus:** Excessive focus on process maturity may reduce attention to flexibility and changing customer needs.

### 4. Conclusion

CMM provides a structured framework for improving software development processes through five maturity levels, from Initial to Optimizing. Despite limitations such as cost, time and documentation overhead, it helps improve process discipline, project management and continual improvement.

**Memory order:** Initial → Repeatable → Defined → Managed → Optimizing.

---

## Q4. Differentiate between Quality Assurance (QA) and Quality Control (QC). [6 Marks]

### 1. Introduction

Quality Assurance (QA) and Quality Control (QC) are important components of Software Quality Management.

- **Quality Assurance:** A process-oriented activity that focuses on preventing defects by improving and monitoring software development processes.
- **Quality Control:** A product-oriented activity that focuses on identifying defects in software through testing and inspection.

### 2. Difference Between QA and QC

| Quality Assurance (QA) | Quality Control (QC) |
|---|---|
| 1. Focuses on improving the development process. | 1. Focuses on checking the quality of the software product. |
| 2. It is process-oriented. | 2. It is product-oriented. |
| 3. Main objective is defect prevention. | 3. Main objective is defect detection. |
| 4. It is a proactive approach. | 4. It is generally a detection-oriented activity. |
| 5. Applies throughout the software development life cycle. | 5. Evaluates software products and deliverables at appropriate stages. |
| 6. Establishes standards, procedures and guidelines. | 6. Verifies whether the product meets specified quality requirements. |
| 7. Includes process audits, reviews and defining standards. | 7. Includes software testing, product inspection and defect reporting. |
| 8. Involves the development team and quality management roles. | 8. Is commonly performed by testing and quality control roles. |
| 9. Helps prevent defects from being introduced. | 9. Identifies defects present in the product. |
| 10. Example: defining coding standards. | 10. Example: testing login validation. |

### 3. Relationship

Quality Management includes both QA and QC. QA improves the process and helps prevent defects; QC evaluates the product and detects defects. Together they support improved software quality.

### 4. Conclusion

Quality Assurance prevents defects by improving software development processes, whereas Quality Control detects defects by evaluating the software product. Both work together to improve reliability and customer satisfaction.

**Memory aid:** QA = Process + Prevention; QC = Product + Detection.

---

## Q5. Explain Quality Management System (QMS), its structure, pillars and important aspects. [5–6 Marks]

### 1. Introduction

A Quality Management System (QMS) is a structured system of policies, processes, procedures and responsibilities used by an organization to ensure that products and services consistently meet specified quality requirements and customer expectations.

In software engineering, QMS helps manage software quality throughout the Software Development Life Cycle (SDLC).

### 2. Structure of QMS

1. **Quality Policy:** Defines the organization's overall commitment and direction towards quality.
2. **Quality Objectives:** Establishes measurable goals for improving quality.
3. **Organization and Responsibilities:** Defines roles, responsibilities and authorities.
4. **Processes and Procedures:** Specifies standard methods for development, testing and quality assurance.
5. **Documentation:** Maintains quality manuals, standards, procedures, reports and records.
6. **Monitoring and Measurement:** Evaluates process performance through audits, reviews and metrics.
7. **Corrective Actions:** Identifies problems, removes their causes and prevents recurrence.
8. **Continual Improvement:** Improves processes and product quality using feedback and evaluation.

### 3. Pillars of Quality Management

1. **Customer Focus:** Understand customer needs and satisfy requirements.
2. **Leadership:** Management establishes quality policies, objectives and direction.
3. **Engagement of People:** Employees participate in quality improvement through teamwork and training.
4. **Process Approach:** Activities are managed as interconnected processes.
5. **Improvement:** Processes are regularly evaluated and improved.
6. **Evidence-Based Decision Making:** Decisions are based on data, measurements and quality reports.
7. **Relationship Management:** Maintains effective relationships with customers, suppliers and stakeholders.

### 4. Important Aspects of Quality Management

1. **Quality Planning:** Defines quality standards, objectives and methods.
2. **Quality Assurance:** Ensures appropriate processes are followed to prevent defects.
3. **Quality Control:** Checks software through testing and inspection to identify defects.
4. **Quality Improvement:** Uses corrective actions and improvement activities to enhance quality.
5. **Quality Documentation:** Maintains quality plans, test reports and audit records.
6. **Quality Audits:** Evaluates whether quality procedures and standards are followed.
7. **Customer Satisfaction:** Uses feedback to verify whether software meets user expectations.

### 5. Conclusion

QMS provides a systematic approach to managing and improving software quality. Its structure, pillars and important aspects help organizations establish standard processes, prevent defects, improve productivity and achieve customer satisfaction.

---

## Q6. Explain Quality Plan in detail. [6 Marks]

### 1. Introduction

A Quality Plan is a document that defines the quality standards, objectives, procedures, responsibilities and activities required to achieve the desired quality of a software product.

It describes how quality will be maintained, monitored and controlled throughout the SDLC.

### 2. Objectives

1. Define quality standards and objectives.
2. Ensure that software meets customer requirements.
3. Identify defects at an early stage.
4. Define QA and QC activities.
5. Establish responsibilities of team members.
6. Improve software reliability and maintainability.
7. Support continuous improvement.

### 3. Components of a Quality Plan

1. **Quality Objectives:** Defines measurable project quality goals.
2. **Quality Standards:** Specifies standards and guidelines to be followed.
3. **Roles and Responsibilities:** Defines responsibilities of developers, testers, managers and QA staff.
4. **Quality Assurance Activities:** Includes process audits, reviews and inspections to prevent defects.
5. **Quality Control Activities:** Includes testing and product inspection to identify defects.
6. **Testing Strategy:** Defines testing levels, techniques, tools, environments and test data.
7. **Quality Metrics:** Defines measurements such as defect density and test coverage.
8. **Documentation and Reporting:** Specifies test plans, test cases, defect reports and audit records.
9. **Risk Management:** Identifies quality risks and defines actions to reduce them.
10. **Review and Improvement:** Defines how quality performance will be reviewed and improved.

### 4. Steps in Preparing a Quality Plan

1. Study project requirements and scope.
2. Define measurable quality objectives.
3. Select applicable standards and procedures.
4. Assign quality-related responsibilities.
5. Plan QA, QC and testing activities.
6. Define metrics, tools and reporting methods.
7. Document the plan and communicate it to stakeholders.
8. Monitor the plan and update it when required.

### 5. Advantages

- Improves software quality and reliability.
- Reduces defects and development errors.
- Supports effective use of resources.
- Improves communication among team members.
- Maintains consistency in development.
- Increases customer satisfaction.

### 6. Conclusion

A Quality Plan is an important document in software quality management. It defines quality objectives, standards, responsibilities, testing activities and monitoring procedures. It helps prevent defects and ensures that the final product meets customer expectations.

---

## Q7. Explain Customer Satisfaction and its importance in Software Quality. [5 Marks]

### 1. Introduction

Customer Satisfaction refers to the degree to which a software product meets or exceeds customer expectations and requirements.

It is achieved when software provides the expected functionality, performance, reliability, security and usability.

### 2. Factors Affecting Customer Satisfaction

1. **Functionality:** Software provides the required features and functions.
2. **Reliability:** Software operates correctly without frequent failures.
3. **Performance:** Application responds quickly and uses resources efficiently.
4. **Usability:** Software is easy to learn and operate.
5. **Security:** User information and sensitive data are protected.
6. **Compatibility:** Software works across supported devices, browsers and operating systems.
7. **Maintainability:** Software can be updated and modified effectively.
8. **Customer Support:** Timely assistance and issue resolution improve user experience.

### 3. Importance in Software Quality

1. **Improves Software Quality:** Feedback helps identify defects and areas for improvement.
2. **Builds Customer Loyalty:** Satisfied customers are more likely to continue using and recommend the software.
3. **Improves Market Reputation:** Satisfaction increases organizational credibility.
4. **Reduces Complaints:** Understanding requirements reduces dissatisfaction and support requests.
5. **Supports Continuous Improvement:** Feedback helps improve features and performance.
6. **Increases Business Success:** Customer retention supports business growth.
7. **Ensures Requirement Fulfilment:** Helps verify whether software meets actual user needs.

### 4. Methods to Measure Customer Satisfaction

1. Customer surveys and questionnaires.
2. User feedback and suggestions.
3. Customer interviews.
4. Usage and feature-adoption analysis.
5. Complaint analysis.
6. Customer Satisfaction Score (CSAT).

Example: If 80 out of 100 customers provide a positive satisfaction rating:

Customer Satisfaction = (80 / 100) × 100 = 80%.

### 5. Conclusion

Customer satisfaction is an important indicator of software quality. Continuous feedback helps organizations improve functionality, reliability, performance and usability, thereby building customer loyalty and supporting business success.

---

## Q8. Explain the characteristics of software. [6 Marks]

### 1. Introduction

Software is a collection of programs, procedures, data and related documentation that instructs a computer to perform specific tasks. Software has characteristics that make it different from physical products such as hardware.

### 2. Characteristics

1. **Developed, Not Manufactured:** Software is created through requirement analysis, design, coding and testing. Its major cost is development rather than reproduction.
2. **Does Not Physically Wear Out:** Software does not wear out like hardware. However, it may become outdated or harder to maintain as technology and requirements change.
3. **Intangible:** Software is a logical product that cannot be physically touched. It consists of programs, data and documentation.
4. **Highly Complex:** Software contains interconnected modules, functions and logical operations. Dependencies make large systems difficult to understand and maintain.
5. **Easy to Reproduce:** Once developed, additional copies can generally be created at very low cost.
6. **Continuously Changing:** Software is modified to meet changing user requirements, technology and business needs.
7. **Requires Maintenance:** Maintenance includes correcting defects, adapting to new environments and improving functionality.
8. **Often Custom-Built:** Software is frequently developed according to specific customer or organizational requirements, although reusable components are also used.

### 3. Conclusion

Software is an intangible, complex and continuously evolving product. It is developed rather than manufactured and does not physically wear out. Understanding these characteristics helps organizations plan development, testing, maintenance and quality management.

---

## Q9. Explain the requirements of a product: Stated/Implied and Present/Future requirements. [4 Marks]

### 1. Introduction

Product requirements define the features, functions, characteristics and quality expectations that a product must satisfy to meet customer needs.

### 2. Stated and Implied Requirements

**Stated Requirements**
- Explicitly specified by the customer or user.
- Clearly mentioned in requirement documents, agreements or specifications.
- Example: A banking application must allow users to transfer money online.

**Implied Requirements**
- Not directly mentioned but naturally expected by customers.
- Necessary for the product to be useful, reliable and acceptable.
- Example: A banking application should protect customer information through appropriate security controls.

### 3. Present and Future Requirements

**Present Requirements**
- Requirements that must be satisfied in the current operating environment.
- Represent immediate customer needs.
- Example: An application must support the currently specified operating-system versions.

**Future Requirements**
- Requirements that may arise due to changing technology, customer expectations or business needs.
- The product should be designed to accommodate future modifications where appropriate.
- Example: An application should support future upgrades and additional features.

### 4. Conclusion

Understanding stated, implied, present and future requirements helps developers satisfy current customer expectations while keeping the product adaptable to future needs.

---

## Q10. Explain the Software Development Process and its steps. [6–8 Marks]

### 1. Introduction

The Software Development Process is a systematic sequence of activities performed to develop, deliver and maintain a software product. It defines how software is planned, designed, developed, tested and deployed to satisfy customer requirements and quality standards.

### 2. Steps

1. **Requirement Analysis:** Collect and analyse customer needs. Identify functional and non-functional requirements and prepare the Software Requirement Specification (SRS).
2. **Planning and Feasibility Study:** Estimate scope, cost, time and resources. Evaluate technical, economic and operational feasibility.
3. **Software Design:** Convert requirements into architecture and design. Define modules, interfaces, database structure and data flow. Prepare HLD and LLD where applicable.
4. **Coding and Implementation:** Convert the design into executable code using suitable languages, frameworks and tools. Follow coding standards.
5. **Software Testing:** Test the software to identify defects and verify requirements. Perform suitable testing levels such as unit, integration, system and acceptance testing.
6. **Deployment:** Install and release tested software into the target environment. Complete configuration and user setup.
7. **Maintenance:** Correct defects, adapt software to new environments and improve functionality after deployment.

### 3. Process Flow

Requirement Analysis → Planning and Feasibility → Design → Coding → Testing → Deployment → Maintenance.

### 4. Importance

- Provides a systematic development approach.
- Helps manage time, cost and resources.
- Improves software quality and reliability.
- Reduces development risks and errors.
- Supports communication and coordination.
- Makes testing and maintenance more manageable.

### 5. Conclusion

The Software Development Process provides a structured approach for developing high-quality software. Each phase has a specific purpose, from requirement analysis to maintenance, and helps ensure that the final product meets customer requirements.

---

## Q11. Discuss problematic areas in the Software Development Life Cycle (SDLC). [6 Marks]

### 1. Introduction

The Software Development Life Cycle (SDLC) is a systematic process used to develop and maintain software. Problems may occur during its phases and affect software quality, cost, delivery time and customer satisfaction.

### 2. Problematic Areas

1. **Requirement-Related Problems:** Requirements may be incomplete, unclear or misunderstood. Frequent changes can affect development.
2. **Planning and Estimation Problems:** Incorrect estimates of cost, time and resources can cause delays and budget overruns.
3. **Design-Related Problems:** Poor architecture, database design or system structure can create performance and reliability issues.
4. **Coding and Implementation Problems:** Programming mistakes, incorrect logic and poor coding practices introduce defects. Module integration may create compatibility problems.
5. **Testing-Related Problems:** Insufficient testing, inadequate test cases and limited test data may leave defects undetected.
6. **Communication and Coordination Problems:** Poor communication between customers, developers, testers and managers can cause misunderstandings and delays.
7. **Deployment Problems:** Configuration, installation, data migration and environment differences may affect release.
8. **Maintenance-Related Problems:** Changes may introduce new defects. Poor documentation makes maintenance difficult.
9. **Resource and Skill Problems:** Shortage of skilled staff, tools, infrastructure or budget may affect quality and delivery.

### 3. Methods to Reduce Problems

- Perform proper requirement analysis and validation.
- Prepare realistic plans and estimates.
- Follow suitable design principles and coding standards.
- Conduct reviews, inspections and testing.
- Maintain communication and documentation.
- Use risk management and continuous quality improvement.

### 4. Conclusion

Problematic areas can occur at every SDLC stage. Proper planning, quality assurance, effective communication, documentation and continuous testing help reduce these problems.

---

## Q12. Explain different types of products based on criticality to the user, with examples. [8 Marks]

### 1. Introduction

Criticality refers to the importance of a software product to its users and the impact of its failure. A failure may cause inconvenience, financial loss, business interruption or loss of human life.

### 2. Types of Products

**1. Safety-Critical Products**
- Directly related to human life and safety.
- Failure may cause injury, loss of life or environmental damage.
- Require strict quality standards, extensive testing and safety verification.
- Examples: aircraft flight-control systems, medical life-support systems, nuclear power plant control systems and railway signalling systems.

**2. Mission-Critical Products**
- Essential for completing an important mission or operation.
- Failure may prevent an organization from performing critical activities.
- Require high reliability, availability and fault tolerance.
- Examples: military communication systems, satellite control systems and spacecraft navigation systems.

**3. Business-Critical Products**
- Essential for normal business operations.
- Failure may cause financial losses, business interruption and customer dissatisfaction.
- Require suitable backup, security and recovery mechanisms.
- Examples: banking transaction systems, ERP systems, e-commerce platforms and hospital management systems.

**4. Non-Critical Products**
- Not essential for human safety, mission completion or major business operations.
- Failure generally causes inconvenience rather than serious damage.
- Examples: personal entertainment applications, wallpaper applications, simple calculator applications and digital clock applications.

### 3. Comparison

| Product Type | Impact of Failure | Example |
|---|---|---|
| Safety-Critical | Injury or loss of human life | Aircraft control system |
| Mission-Critical | Important mission cannot be completed | Satellite control system |
| Business-Critical | Financial loss or business interruption | Banking system |
| Non-Critical | Minor inconvenience | Wallpaper application |

### 4. Importance of Classification

1. Determines the required testing effort.
2. Helps identify and prioritize risks.
3. Defines reliability, availability and security requirements.
4. Supports appropriate allocation of skilled resources.
5. Helps select suitable quality standards and testing techniques.
6. Reduces the impact of failures through safety, backup and recovery measures.

### 5. Conclusion

Classification based on criticality helps organizations understand the impact of software failure on users. Different product types require different levels of quality assurance, testing and reliability.

---

## Q13. Explain two methods of Software Quality Control. [6 Marks]

### 1. Introduction

Software Quality Control (SQC) is the process of monitoring and evaluating software products to identify defects and ensure that they meet specified quality requirements.

Two important methods are Software Testing and Software Reviews/Inspections.

### 2. Method 1 – Software Testing

- Software testing executes software to identify defects and verify whether it satisfies specified requirements.
- It checks correctness, functionality, performance and reliability.
- Testing is performed at different levels.

**Types:**
1. Unit Testing – tests individual modules or components.
2. Integration Testing – checks interactions between integrated modules.
3. System Testing – tests the complete software system.
4. Acceptance Testing – verifies whether software meets customer requirements.

**Example:** Testing a banking application to verify login, fund transfer and balance enquiry.

**Advantages:**
- Identifies defects before release.
- Improves reliability.
- Verifies functional and non-functional requirements.

### 3. Method 2 – Software Reviews and Inspections

- Reviews are examination activities used to identify defects in software work products without executing the program.
- They can examine requirements, design, source code and documentation.
- Reviews may involve developers, testers and technical experts.

**Types:**
1. Informal Review – documents or code are checked informally.
2. Walkthrough – the author explains the work product step by step.
3. Technical Review – technical experts evaluate correctness and quality.
4. Inspection – a formal review that follows defined procedures and roles.

**Example:** Reviewing source code to identify incorrect logic, missing conditions and coding-standard violations.

**Advantages:**
- Detects defects early.
- Reduces the cost of correcting defects.
- Improves code quality and documentation.
- Prevents defects from reaching later stages.

### 4. Difference Between the Two Methods

| Software Testing | Reviews and Inspections |
|---|---|
| Executes software to identify defects. | Examines work products without executing software. |
| Identifies failures during execution. | Identifies defects in requirements, design, code and documents. |
| Dynamic quality control method. | Static quality control method. |
| Requires executable software for execution-based testing. | Can be performed before program execution. |
| Example: Testing login functionality. | Example: Reviewing login source code. |

### 5. Conclusion

Software Testing and Software Reviews/Inspections are important methods of Software Quality Control. Testing identifies defects through execution, whereas reviews identify defects through examination. Both help improve software quality, reliability and customer satisfaction.

---

# Additional Plain-Topic Explanations

These notes reinforce three important concepts independently of the question-wise answers above.

## A. ISO 9000 / ISO 9001 – Plain Topic

ISO (International Organization for Standardization) develops international standards to support quality, safety and consistency. The ISO 9000 family provides fundamentals and guidance for Quality Management Systems.

| Standard | Main purpose |
|---|---|
| ISO 9000 | QMS fundamentals and vocabulary |
| ISO 9001 | QMS requirements; certifiable standard |
| ISO 9004 | Guidance for sustained organizational success |
| ISO 19011 | Guidelines for management-system auditing |

**Seven quality management principles:** Customer Focus, Leadership, Engagement of People, Process Approach, Improvement, Evidence-Based Decision Making and Relationship Management.

**Software example:** A software company documents and controls its requirement analysis, development, testing, audit and corrective-action processes under its QMS.

**Key distinction:** ISO 9000 explains fundamentals and vocabulary; ISO 9001 specifies requirements for a QMS. Certification does not guarantee that every product is defect-free.

## B. Capability Maturity Model (CMM) – Plain Topic

CMM is a framework developed by the Software Engineering Institute (SEI) to assess and improve the maturity of software development processes.

| Level | Name | Main idea |
|---:|---|---|
| 1 | Initial | Unpredictable and informal processes |
| 2 | Repeatable | Basic project management practices |
| 3 | Defined | Documented and standardized processes |
| 4 | Managed | Quantitatively measured and controlled processes |
| 5 | Optimizing | Continuous process improvement |

**Importance:** Process improvement, better project management, reduced process risks, consistent practices and measurable improvement.

**Limitations:** Time-consuming, costly, documentation overhead, difficult for some small organizations, and no automatic guarantee of defect-free software.

## C. Software Defects – Plain Topic

A software defect is a fault in a software product that can cause incorrect or unexpected behaviour or failure to meet requirements.

**Error → Defect → Failure**
- Error: A human mistake during development.
- Defect: A fault introduced into a software work product.
- Failure: Incorrect behaviour observed during execution.

**Major causes:** Incorrect requirements, communication gaps, design errors, coding mistakes, complexity, changing requirements, insufficient testing and time/budget constraints.

**Example:** An incorrect calculation formula in banking software is a defect. If a transaction displays an incorrect balance during execution, the user observes a failure.

**Prevention:** Requirement validation, design and code reviews, coding standards, testing, quality audits and maintenance.
