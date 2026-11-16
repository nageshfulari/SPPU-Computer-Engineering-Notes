# Unit VI – Complete Exam-Ready Answers
## Testing Framework

**Subject:** Software Testing and Quality Assurance (410245-D)  
**University:** Savitribai Phule Pune University (SPPU)  
**Programme:** Fourth Year Computer Engineering, 2019 Pattern  
**Teaching Hours:** 07

> **Answer-writing convention:** Simple academic English, marks-appropriate explanations, plain-text formulas and compact diagrams suitable for reproducing in an SPPU answer sheet. The questions below are the topics prepared in this Unit VI study session.

## Syllabus coverage

- Software Quality, Quality Dilemma and Achieving Software Quality.
- Software Quality Assurance (SQA): elements, tasks, goals and metrics.
- Formal SQA and Statistical SQA.
- Six Sigma.
- ISO 9000.
- SQA Plan.
- Total Quality Management (TQM).
- Product Quality Metrics and In-Process Quality Metrics.
- Software Maintenance.
- Ishikawa's quality control tools: Flow Chart, Checklists, Pareto Diagrams, Histogram, Run Charts, Scatter Diagrams, Control Chart and Cause-and-Effect Diagram.
- Defect Removal Effectiveness (DRE) and Defect Removal Process.
- Case Study: Software Quality in Academic Curriculum.

---

## Q1. Explain Six Sigma characteristics and its role in Software Quality Assurance. [6 Marks]

### 1. Introduction
Six Sigma is a data-driven quality management methodology used to improve processes by identifying and eliminating defects and reducing variations.

In Software Quality Assurance (SQA), Six Sigma helps improve software development processes, reduce errors, increase reliability and deliver high-quality software products.

### 2. Characteristics of Six Sigma
1. **Customer Focus:** Understands customer requirements and aims to deliver software that meets their expectations.
2. **Defect Reduction:** Minimizes defects in software products and improves overall quality.
3. **Process Improvement:** Continuously improves software development and testing processes.
4. **Data-Driven Approach:** Uses measurable data, statistical techniques and analysis to identify root causes of defects.
5. **Variation Reduction:** Reduces variations so development and testing activities produce consistent results.
6. **Continuous Improvement:** Encourages regular monitoring, evaluation and improvement of software processes.
7. **Employee Involvement:** Involves team members in identifying problems and implementing improvements.
8. **Measurable Results:** Evaluates performance using metrics such as defect rates, failure rates and process efficiency.

### 3. Role of Six Sigma in SQA
1. Improves software quality by reducing defects during development.
2. Reduces rework and maintenance costs through early defect identification.
3. Improves testing by identifying frequently occurring defects.
4. Increases customer satisfaction by meeting requirements.
5. Improves process efficiency by identifying unnecessary activities and errors.
6. Supports decisions using statistical data and measurable results.

### 4. Six Sigma DMAIC Methodology
Six Sigma commonly uses DMAIC to improve existing processes.

```
       DEFINE
          |
          v
       MEASURE
          |
          v
        ANALYZE
          |
          v
       IMPROVE
          |
          v
        CONTROL
          |
          v
   Improved Process
```

- **Define:** Identify the quality problem and customer requirements.
- **Measure:** Collect data about the existing process.
- **Analyze:** Identify the root causes of defects.
- **Improve:** Implement solutions to reduce defects.
- **Control:** Monitor the improved process to maintain quality.

### 5. Conclusion
Six Sigma is an effective quality improvement methodology in SQA. It reduces software defects, improves process performance, increases customer satisfaction and supports continuous improvement.

---

## Q2. Explain Ishikawa's Seven Basic Quality Control Tools with suitable diagrams and applications. [6 Marks]

### 1. Introduction
Ishikawa's Basic Quality Control Tools are graphical and statistical techniques used to identify, analyse, monitor and solve quality-related problems. They are useful in SQA for defect analysis, root-cause identification and process improvement.

**Syllabus note:** The supplied Unit VI syllabus heading says “Seven Basic Tools” but enumerates eight entries. All eight listed entries are included below.

### 2. Tools

**1. Flowchart**

A Flowchart represents the sequence of activities and decisions in a process using standard symbols connected by arrows.

```
       (Start)
          |
          v
   [Requirement Analysis]
          |
          v
       [Coding]
          |
          v
       [Testing]
          |
          v
    <Defects Found?>
       /       \
     Yes        No
      |          |
      v          v
 [Debugging]  [Release]
      |
      v
  [Retesting]
```

**Applications:** Represents software workflows; documents login, registration and payment processes; identifies unnecessary steps and process errors.

**2. Checklist (Check Sheet)**

A Checklist or Check Sheet is a structured form used to collect, record or verify information systematically.

| Defect / Activity | Tally | Total |
|---|---|---:|
| UI errors | `||||` | 4 |
| Login errors | `|||` | 3 |
| Database errors | `||` | 2 |
| Validation errors | `|||||` | 5 |

**Applications:** Records software defects; verifies testing activities; ensures standards are followed; collects data about recurring problems.

**3. Pareto Diagram**

A Pareto Diagram is a bar chart that arranges problems in descending order of frequency. It is associated with the Pareto principle, commonly expressed as the 80/20 rule.

```
Defects
  |
  | █████████████  Validation
  | ██████████     UI Errors
  | ███████        Login Errors
  | ████           Database Errors
  +---------------------------->
       Defect Categories
```

**Applications:** Identifies frequently occurring defects; prioritizes corrective actions; focuses improvement effort on major problems.

**4. Histogram**

A Histogram represents the frequency distribution of numerical data using adjacent bars.

```
Frequency
  |
  |       ███
  |   ███ ███
  |   ███ ███ ███
  | ███ ███ ███ ███
  +-------------------->
    1-2  2-3  3-4  4-5
       Response Time (sec)
```

**Applications:** Analyses response-time distribution; studies performance variation; identifies unusual patterns in numerical measurements.

**5. Run Chart**

A Run Chart is a line graph that displays data collected over time. It helps identify trends, shifts and patterns.

```
Defects
  |
  |  *
  |     *
  |   *   *
  |         *   *
  |             *
  +-------------------->
       Testing Time
```

**Applications:** Tracks defects across testing cycles; monitors development progress; identifies increasing or decreasing trends.

**6. Scatter Diagram**

A Scatter Diagram plots two numerical variables to identify a possible relationship or correlation between them.

```
Defects
  |
  |             *
  |          *
  |       *  *
  |    *
  |  *
  +-------------------->
       Code Complexity
```

**Applications:** Studies code complexity against defect count; analyses testing effort against defects detected; identifies possible factors affecting quality.

**7. Control Chart**

A Control Chart monitors process performance over time using a Centre Line (CL), Upper Control Limit (UCL) and Lower Control Limit (LCL).

```
Value
  |
UCL|-----------------------
  |    *       *
CL |----*---*------*--------
  | *       *   *
LCL|-----------------------
  +------------------------>
          Time
```

**Applications:** Monitors defect rates; identifies unusual process variations; checks whether a quality process is statistically stable.

**8. Cause-and-Effect Diagram**

A Cause-and-Effect Diagram, also called the Fishbone or Ishikawa Diagram, identifies possible causes of a problem.

```
People --------\
Methods ---------\
Tools ------------>------ Software Defects
Process ---------/
Environment ----/
```

**Applications:** Identifies possible root causes of defects; analyses problems related to people, methods, tools and processes; supports corrective actions.

### 3. Conclusion
The quality control tools help collect and analyse data, understand processes, identify root causes and monitor quality. They support systematic defect analysis and continuous improvement in SQA.

---

## Q3. Explain Total Quality Management (TQM) in detail. [6 Marks]

### 1. Introduction
Total Quality Management (TQM) is an organization-wide management approach that focuses on continuously improving the quality of products, services and processes to achieve customer satisfaction.

In SQA, TQM involves all employees in improving software development, testing and maintenance processes.

### 2. Characteristics of TQM
1. **Customer Focus:** Gives priority to customer requirements and satisfaction.
2. **Continuous Improvement:** Regularly improves software development and testing processes.
3. **Employee Involvement:** Involves developers, testers and managers in quality improvement.
4. **Process-Oriented Approach:** Improves processes rather than only detecting defects in the final product.
5. **Teamwork:** Encourages cooperation and communication among departments.
6. **Fact-Based Decisions:** Uses data, quality metrics and statistical techniques.
7. **Management Commitment:** Requires leadership, resources and support from top management.

### 3. Principles of TQM
- Quality is everyone's responsibility.
- Customer satisfaction is the main objective.
- Defects should be prevented rather than corrected later.
- Continuous improvement should be part of daily activities.
- Decisions should be based on facts and measurements.
- Effective communication and teamwork should be encouraged.

### 4. Implementation of TQM in SQA
1. Understand customer requirements.
2. Set quality objectives and standards.
3. Involve all employees in quality activities.
4. Improve development and testing processes.
5. Measure and monitor software quality.
6. Take corrective actions when problems occur.
7. Continue improving the process.

### 5. Benefits of TQM
1. Improves software quality and reliability.
2. Increases customer satisfaction.
3. Reduces defects, rework and maintenance costs.
4. Improves productivity through better processes.
5. Encourages employee participation and teamwork.
6. Supports continuous process improvement.

### 6. Example
For an online banking application, the company collects customer feedback, follows coding standards, tests the application continuously, monitors defects and improves the product based on feedback. This organization-wide approach supports reliability, security and customer satisfaction.

### 7. Conclusion
TQM focuses on customer satisfaction, employee involvement and continuous improvement. In SQA, it improves development and testing processes, reduces defects and helps deliver high-quality software.

---

## Q4. Explain how to maintain Software Quality Assurance (SQA). [5–6 Marks]

### 1. Introduction
Software Quality Assurance (SQA) is a systematic approach used to ensure that software processes and products meet specified quality standards and requirements. Maintaining SQA involves continuously monitoring, evaluating and improving software development activities.

### 2. Methods to Maintain SQA
1. **Define Quality Standards:** Establish coding, documentation, testing and development standards.
2. **Prepare an SQA Plan:** Define quality objectives, responsibilities, activities and review procedures.
3. **Conduct Reviews and Audits:** Review requirements, design, source code and test cases; verify compliance with standards.
4. **Perform Software Testing:** Conduct unit, integration, system, acceptance, functional and non-functional testing.
5. **Use Quality Metrics:** Monitor defect density, failure rate, test coverage and DRE.
6. **Apply Configuration Management:** Control source code, documents, versions and changes.
7. **Provide Training and Employee Involvement:** Train team members and encourage responsibility for quality.
8. **Continuous Process Improvement:** Analyse recurring defects and implement corrective and preventive actions.

### 3. SQA Maintenance Process
```
 Define Quality Standards
          |
          v
    Prepare SQA Plan
          |
          v
   Reviews and Audits
          |
          v
    Software Testing
          |
          v
   Measure Quality
          |
          v
  Identify and Correct Defects
          |
          v
  Continuous Improvement
          |
          +------> Repeat
```

### 4. Benefits
- Improves software reliability and performance.
- Reduces defects and development costs.
- Ensures compliance with quality standards.
- Increases customer satisfaction.
- Improves productivity and development efficiency.
- Supports continuous improvement.

### 5. Conclusion
Maintaining SQA requires quality standards, planning, reviews, audits, testing and continuous improvement. These activities help prevent defects and deliver reliable software.

---

## Q5. Explain SQA Tasks, Goals and Metrics. [5–6 Marks]

### 1. Introduction
Software Quality Assurance is a planned and systematic set of activities performed throughout the SDLC to ensure that software processes and products meet specified quality requirements. Its three important aspects are Tasks, Goals and Metrics.

### 2. SQA Tasks
1. **Preparation of SQA Plan:** Defines quality standards, responsibilities, procedures and activities.
2. **Standards Definition:** Establishes software development, coding, documentation and testing standards.
3. **Reviews and Audits:** Verifies that software activities follow defined standards.
4. **Software Testing:** Ensures that appropriate testing is performed to identify defects.
5. **Defect Tracking:** Records, monitors and analyses defects.
6. **Configuration Management:** Controls software changes, source code and document versions.
7. **Reporting:** Communicates quality-related issues and prepares quality reports.

### 3. Goals of SQA
1. **Quality Improvement:** Ensure that software meets specified quality requirements.
2. **Defect Prevention:** Prevent errors during development rather than only correcting them after delivery.
3. **Process Compliance:** Ensure that activities follow standards and procedures.
4. **Customer Satisfaction:** Deliver software that meets customer expectations.
5. **Cost Reduction:** Reduce development and maintenance costs through early defect identification.
6. **Continuous Improvement:** Improve software processes, quality and productivity.

### 4. SQA Metrics
SQA metrics are measurable values used to evaluate software quality and the effectiveness of quality assurance activities.

| Metric | Description |
|---|---|
| Defect Density | Number of defects per unit size of software. |
| Defect Removal Efficiency | Measures effectiveness of defect removal before delivery. |
| Test Coverage | Percentage of testable items covered by testing. |
| Failure Rate | Number of software failures during a specified period. |
| Rework Effort | Effort required to correct defects and modify software. |
| Customer Defect Rate | Defects reported by customers after delivery. |

**Important formulas:**

- Defect Density = Total Number of Defects / Software Size
- Test Coverage = (Items Tested / Total Testable Items) × 100
- DRE = [Defects Removed Before Delivery / (Defects Removed Before Delivery + Defects Found After Delivery)] × 100

### 5. Relationship Between Tasks, Goals and Metrics

| Aspect | Purpose | Example |
|---|---|---|
| Tasks | Activities performed to maintain quality | Reviews, audits and testing |
| Goals | Objectives to be achieved | Defect prevention and customer satisfaction |
| Metrics | Measures used to evaluate quality | Defect density and test coverage |

### 6. Conclusion
SQA tasks define the activities required to maintain quality, goals specify desired objectives, and metrics measure effectiveness. Together, they help prevent defects and deliver reliable software.

---

## Q6. Explain activities and parameters required to achieve high Software Quality. [6–8 Marks]

### 1. Introduction
Software Quality is the degree to which a software product satisfies specified requirements, user expectations and quality standards. Achieving high quality requires proper planning, systematic development, continuous testing and regular improvement throughout the SDLC.

### 2. Activities Required to Achieve High Software Quality
1. **Requirement Analysis:** Collect and analyse customer requirements; ensure they are complete, clear, consistent and testable.
2. **Software Quality Planning:** Prepare an SQA plan and define objectives, standards, responsibilities and quality metrics.
3. **Proper Software Design:** Develop clear and modular architecture; follow simplicity, reusability and maintainability principles.
4. **Coding Standards:** Follow coding guidelines and perform code reviews to identify errors.
5. **Software Testing:** Perform unit, integration, system and acceptance testing, including functional and non-functional testing.
6. **Reviews and Audits:** Review requirements, design, code and test documents; verify compliance with standards.
7. **Configuration and Change Management:** Control source-code versions and modifications to prevent unintended defects.
8. **Continuous Improvement:** Monitor metrics, analyse root causes and improve development and testing processes.

### 3. Parameters / Quality Characteristics
| Parameter | Description |
|---|---|
| Functionality | Software provides the required functions correctly. |
| Reliability | Software operates consistently without failures. |
| Usability | Software is easy to learn and use. |
| Efficiency | Software uses resources effectively and provides good performance. |
| Maintainability | Software is easy to modify, debug and update. |
| Portability | Software can be transferred to different platforms or environments. |
| Security | Software protects data and prevents unauthorized access. |
| Testability | Software can be tested and verified against requirements. |

### 4. Process for Achieving High Software Quality
```
  Requirement Analysis
          |
          v
    Quality Planning
          |
          v
     Software Design
          |
          v
        Coding
          |
          v
   Testing and Reviews
          |
          v
   Quality Evaluation
          |
          v
   Software Delivery
          |
          v
 Continuous Improvement
```

### 5. Conclusion
High software quality is achieved through requirement analysis, quality planning, good design, coding standards, systematic testing and continuous improvement. Quality characteristics such as functionality, reliability, usability, efficiency and maintainability help deliver software that satisfies customer requirements.

---

## Q7. Explain Defect Removal Effectiveness (DRE) and its importance. [5 Marks]

### 1. Introduction
Defect Removal Effectiveness (DRE) is a software quality metric used to measure the effectiveness of defect detection and removal activities performed during the SDLC. It indicates how effectively defects are removed before software delivery.

### 2. Formula
**DRE = [E / (E + D)] × 100**

Where:
- E = Number of defects found and removed before software delivery.
- D = Number of defects found after software delivery.

### 3. Example
Given:
- Defects removed before delivery (E) = 90
- Defects found after delivery (D) = 10

Calculation:

DRE = [E / (E + D)] × 100

DRE = [90 / (90 + 10)] × 100

DRE = (90 / 100) × 100

**DRE = 90%**

Therefore, the Defect Removal Effectiveness is 90%.

### 4. Importance of DRE
1. **Measures Testing Effectiveness:** Evaluates how effectively defects are identified before delivery.
2. **Improves Software Quality:** Higher DRE indicates fewer defects remain in delivered software.
3. **Reduces Maintenance Cost:** Early defect removal reduces post-delivery correction effort.
4. **Increases Customer Satisfaction:** Reduces failures and problems experienced by customers.
5. **Identifies Process Weaknesses:** Highlights weaknesses in development, reviews and testing.
6. **Supports Process Improvement:** Provides measurable information to improve SQA activities.

### 5. Interpretation
- **High DRE:** Indicates effective defect detection and removal before delivery.
- **Low DRE:** Indicates that more defects are escaping into delivered software and improvement is required.

### 6. Conclusion
DRE evaluates the effectiveness of defect detection and removal. A higher DRE helps improve software quality, reduce maintenance costs and minimize post-delivery defects.

---

## Q8. Differentiate between Run Charts and Control Charts. [5–6 Marks]

### 1. Introduction
Run Charts and Control Charts are graphical tools used in SQA to monitor process performance over time. A Run Chart identifies trends and patterns, while a Control Chart also uses statistical control limits to evaluate process stability.

### 2. Differences

| Sr. No. | Run Chart | Control Chart |
|---|---|---|
| 1. | Displays process data collected over time. | Displays process data with statistical control limits. |
| 2. | Generally uses a median as a central reference line. | Uses Centre Line (CL), Upper Control Limit (UCL) and Lower Control Limit (LCL). |
| 3. | Identifies trends, shifts and patterns. | Identifies trends and unusual process variations. |
| 4. | Does not normally use statistical control limits. | Uses statistically calculated control limits. |
| 5. | Simple to prepare and interpret. | Requires statistical calculations and analysis. |
| 6. | Helps observe changes in process performance. | Helps determine whether a process is statistically stable. |
| 7. | Used for basic process monitoring. | Used for monitoring and controlling process quality. |

### 3. Diagrams

**A. Run Chart**
```
Number of Defects
  |
10| *
  |    *
 8|       *
  |          *
 6|------------- Median
  |              *
 4|                 *
  +------------------------>
       Testing Cycles
```

**B. Control Chart**
```
Process Value
  |
UCL|---------------------------
  |    *       *
  |       *         *
 CL|------*---*----------------
  | *              *
LCL|---------------------------
  +--------------------------->
             Time
```

### 4. Applications in SQA
- **Run Chart:** Tracks defects during testing cycles, monitors development progress and identifies quality trends.
- **Control Chart:** Monitors defect rates, identifies unusual process variations and evaluates process stability.

### 5. Conclusion
A Run Chart identifies trends and patterns in process data, whereas a Control Chart uses statistical control limits to monitor process stability. Both help monitor performance and improve software quality.

---

## Q9. Explain Software Maintenance and its importance. [5 Marks]

### 1. Introduction
Software Maintenance is the process of modifying and updating software after delivery to correct defects, improve performance, adapt to changing environments and meet new user requirements. It ensures that software remains useful, reliable and efficient.

### 2. Types of Software Maintenance

**1. Corrective Maintenance**
- Corrects errors and defects discovered after software delivery.
- Example: Fixing a login failure or calculation error.

**2. Adaptive Maintenance**
- Modifies software to work in a changed environment.
- Example: Updating an application to support a new operating system or database version.

**3. Perfective Maintenance**
- Improves functionality, performance and usability according to user requirements.
- Example: Adding a search feature or improving response time.

**4. Preventive Maintenance**
- Modifies software to prevent future problems and improve maintainability.
- Example: Refactoring complex code and updating documentation.

### 3. Software Maintenance Process
```
   Change Request
         |
         v
  Impact Analysis
         |
         v
   Plan Changes
         |
         v
  Modify Software
         |
         v
   Testing and Validation
         |
         v
   Release Updated Software
```

### 4. Importance of Software Maintenance
1. **Defect Correction:** Corrects errors discovered after delivery.
2. **Improved Performance:** Enhances speed, efficiency and performance.
3. **Adaptability:** Supports new hardware, operating systems and technologies.
4. **User Satisfaction:** Supports changing customer requirements.
5. **Security Improvement:** Helps fix vulnerabilities and protect software.
6. **Increased Software Life:** Extends the useful life of software.
7. **Reduced Future Costs:** Preventive maintenance reduces major failures and expensive modifications.

### 5. Conclusion
Software Maintenance keeps software operating correctly and efficiently after delivery. Corrective, adaptive, perfective and preventive maintenance improve reliability, security, performance and useful life.

---

## Q10. Compare Flowchart and Histogram. [5–6 Marks]

### 1. Introduction
Flowchart and Histogram are basic quality control tools used in SQA. A Flowchart represents process steps, whereas a Histogram represents the frequency distribution of numerical data.

### 2. Differences

| Sr. No. | Flowchart | Histogram |
|---|---|---|
| 1. | Represents the sequence of activities in a process. | Represents the frequency distribution of numerical data. |
| 2. | Uses symbols such as oval, rectangle, diamond and arrows. | Uses adjacent rectangular bars. |
| 3. | Shows the flow and relationship between process steps. | Shows distribution and variation of collected data. |
| 4. | Used mainly for process analysis and documentation. | Used mainly for statistical data analysis. |
| 5. | Helps identify unnecessary steps and process errors. | Helps identify patterns, variations and unusual distributions. |
| 6. | Does not primarily represent numerical frequency. | Represents numerical values and their frequencies. |
| 7. | Example: Software login or registration process. | Example: Distribution of software response times. |

### 3. Diagrams

**A. Flowchart – Login Process**
```
       (Start)
          |
          v
   / Enter Credentials /
          |
          v
   < Valid Details? >
       /       \
     Yes        No
      |          |
      v          v
  [Dashboard] [Show Error]
      |          |
      v          |
     (End) <-----+
```

**B. Histogram – Response Time**
```
Frequency
  |
  |       ███
  |   ███ ███
  |   ███ ███ ███
  | ███ ███ ███ ███
  +-------------------->
    1-2  2-3  3-4  4-5
       Response Time (sec)
```

### 4. Applications
- **Flowchart:** Represents development and testing workflows; documents application processes; identifies unnecessary steps.
- **Histogram:** Analyses response-time distribution; studies performance variations; analyses numerical quality measurements.

### 5. Conclusion
A Flowchart helps understand and analyse process steps, whereas a Histogram helps analyse the frequency distribution of numerical data. Both support quality and process improvement.

---

## Q11. Explain Histogram, Flowchart and Control Chart. [6 Marks]

### 1. Histogram
A Histogram is a graphical quality control tool used to represent the frequency distribution of numerical data using adjacent rectangular bars. It helps identify variations and patterns.

**Diagram – Software Response Time**
```
Frequency
  |
  |       ███
  |   ███ ███
  |   ███ ███ ███
  | ███ ███ ███ ███
  +-------------------->
    1-2  2-3  3-4  4-5
       Response Time (sec)
```

**Working:**
1. Collect numerical data.
2. Divide the data into suitable intervals.
3. Calculate the frequency of each interval.
4. Represent the data using adjacent bars.
5. Analyse the distribution and variations.

**Applications:** Analysing response-time distribution, studying performance variations and identifying unusual numerical patterns.

### 2. Flowchart
A Flowchart is a graphical representation of a process using standard symbols connected by arrows. It shows the sequence of activities and decisions.

**Common symbols:**

| Symbol | Meaning |
|---|---|
| Oval | Start / End |
| Rectangle | Process |
| Diamond | Decision |
| Parallelogram | Input / Output |
| Arrow | Flow direction |

**Diagram – Login Process**
```
       (Start)
          |
          v
   / Enter Credentials /
          |
          v
   < Valid Details? >
       /       \
     Yes        No
      |          |
      v          v
  [Dashboard] [Show Error]
      |          |
      v          |
     (End) <-----+
```

**Working:**
1. Identify the process.
2. Start with the beginning symbol.
3. Represent activities using suitable symbols.
4. Connect symbols using arrows.
5. Include decision points.
6. End the flowchart after the process is complete.

**Applications:** Representing development workflows, documenting application processes and identifying unnecessary steps.

### 3. Control Chart
A Control Chart is a statistical quality control tool used to monitor process performance over time and determine whether a process is statistically stable.

**Important lines:**
- **UCL:** Upper Control Limit – upper boundary of expected process variation.
- **CL:** Centre Line – central process value.
- **LCL:** Lower Control Limit – lower boundary of expected process variation.

**Diagram**
```
Process Value
  |
UCL|---------------------------
  |    *       *
  |       *         *
 CL|------*---*----------------
  | *              *
LCL|---------------------------
  +--------------------------->
             Time
```

**Working:**
1. Collect process measurements at regular intervals.
2. Calculate the centre line and control limits.
3. Plot measurements on the chart.
4. Compare points with the control limits.
5. Investigate unusual patterns or points outside the limits.

**Applications:** Monitoring defect rates, evaluating testing-process stability and identifying unusual process variations.

### 4. Conclusion
Histogram analyses frequency distribution, Flowchart represents process activities, and Control Chart monitors process stability. Together, they help identify problems and improve software quality.

---

## Preparation and coverage note

The answers above consolidate the questions explicitly prepared in this study session. The official syllabus also names Quality Dilemma, Formal and Statistical SQA, ISO 9000, SQA Plan, Product and In-Process Quality Metrics, Defect Removal Process and the Software Quality in Academic Curriculum case study. These topics should be cross-checked against the separate Unit IV material and the remaining Unit VI source material before treating this answer file as exhaustive coverage of every syllabus bullet.
