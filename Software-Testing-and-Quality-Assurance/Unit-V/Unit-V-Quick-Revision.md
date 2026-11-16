# Unit V – Quick Revision
## Automation Testing Tools / Performance Testing Tools

**Subject:** Software Testing and Quality Assurance (410245-D) | **SPPU 2019 Pattern**

## 1. Automation Testing
- Uses tools and scripts to execute test cases automatically.
- Compares actual results with expected results and records outcomes.
- Best suited to repetitive, regression and large-scale tests.

**Process:** Requirement analysis → Tool selection → Test planning → Script development → Environment setup → Execution → Result analysis/reporting → Maintenance.

**Benefits:** Saves time, reduces repetitive errors, increases coverage, reuses scripts, supports regression and parallel execution, provides reports.

**Tool selection:** Application compatibility, language support, browser/platform support, ease of use, cost, integration, reporting, maintenance and team skills.

## 2. Automation Frameworks
- **Linear:** Record-and-playback sequence.
- **Modular:** Divides application into reusable modules.
- **Data-driven:** Separates test data from scripts.
- **Keyword-driven:** Uses action keywords to describe tests.
- **Hybrid:** Combines framework approaches.

**Common elements:** Test scripts, test data, reusable libraries, element locators/object repository, execution engine, configuration, logs and reports.

## 3. Manual vs Automation Testing

| Manual | Automation |
|---|---|
| Human executes steps | Scripts/tools execute steps |
| Better for exploratory/usability | Better for repetitive/regression |
| Repeated execution takes longer | Repeated execution is faster |
| Lower initial tool setup | Initial scripting/tool investment |
| Results may be recorded manually | Logs/reports can be generated |

## 4. Selenium Tool Suite
- **IDE:** Record-and-playback tool; useful for simple tests.
- **RC:** Older client-server browser automation; deprecated.
- **WebDriver:** Programmatic browser automation through browser drivers/protocols.
- **Grid:** Distributes WebDriver sessions across browsers/machines; supports parallel testing.

**Remember:** IDE = record/playback; RC = legacy server; WebDriver = browser control; Grid = distributed execution.

## 5. Other Automation Tools
- **SoapUI:** API and web-service testing; SOAP/REST requests, assertions and response validation.
- **RPA:** Software bots automate repetitive, rule-based business processes. It is not the same as test automation.
- **Tosca:** Commercial model-based, low-code test automation platform; reusable modules and regression testing.
- **Appium:** Open-source automation for native, hybrid and mobile web apps on Android/iOS.

## 6. Performance Testing
Evaluates speed, responsiveness, stability, scalability and resource behaviour under a workload.

**Uses:** Measure response time and throughput; check stability/capacity; identify bottlenecks; evaluate scalability.

**Types:**
- Load: expected workload.
- Stress: beyond normal workload.
- Spike: sudden workload change.
- Endurance/Soak: sustained workload.
- Scalability: increasing workload/resources.

**Tools:** Apache JMeter, LoadRunner, Gatling, k6, Locust, NeoLoad.

## 7. Apache JMeter
- Open-source, Java-based load/performance testing tool.
- **Aim:** Simulate virtual users and measure application responses.
- **Components:** Test Plan, Thread Group, Sampler, Assertion, Listener, Timer.
- **Workflow:** Test Plan → Thread Group → Samplers → Assertions/Listeners → Run → Analyse.
- **Metrics:** Response time, throughput, error rate.

## 8. Cucumber
- Open-source Behaviour-Driven Development (BDD) tool.
- Uses Gherkin feature files.
- Main elements: Feature, Scenario, Given, When, Then, Step Definitions, Test Runner.
- Can integrate with Selenium; Cucumber itself is not a browser automation tool.

Example:
```gherkin
Scenario: Valid login
  Given the user is on the login page
  When valid credentials are entered
  Then the home page should appear
```

## 9. PYQ High-Frequency Topics

Based on the seven supplied papers:
- Automated Testing Process – 6/7
- RPA – 6/7
- Performance Testing – 6/7
- Selenium IDE – 5/7
- Benefits of Automation – 4/7
- Selenium WebDriver – 4/7
- Selenium Tool Suite (explicit suite question) – 4/7
- Tool Selection – 2/7
- Selenium Grid – 2/7
- Selenium RC – 1/7
- Apache JMeter – 1/7

**Important:** Frequency is retrospective evidence from the supplied sample, not a prediction or guarantee. SoapUI, Tosca, Appium, Automation Frameworks and Cucumber were not observed as standalone questions in these seven papers, but they remain official syllabus topics.

## 10. Quick Memory Aids
- Automation process: Analyse → Select → Plan → Script → Setup → Execute → Report → Maintain.
- Selenium: IDE / RC / WebDriver / Grid.
- JMeter: Plan / Thread Group / Sampler / Assertion / Listener.
- Cucumber: Feature → Scenario → Given/When/Then → Step Definitions → Execution.
- Performance: Response time / Throughput / Errors / Stability / Scalability.
