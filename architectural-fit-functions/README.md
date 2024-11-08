# Introduction to Architecture Fitness Functions

Preserving architectural functions over the lifetime of a product can be a challenge when the product goes through rapid business and technological changes. To cater to this requirement, among the architectural governance techniques, we find architectural fitness functions coming in to play ata evolutionary computing strategy.

Architectural fitness functions are mechanisms that measure how well a software architecture is adhering to specific architectural characteristics, such as performance, security, or scalability. These functions help ensure that a system's architecture evolves in a guided and controlled manner over time. They can encompass a wide range of mechanisms, including code-level metrics, unit tests, chaos engineering tools, and monitoring systems.

## Categories and Characteristics of Architectural Fitness Functions
There are several ways to categorize architectural fitness functions:

### Atomic vs. Holistic

Atomic fitness functions focus on a single architectural characteristic, while holistic functions evaluate a combination of characteristics. For example, checking for cyclic dependencies in a component-based system would be an atomic function, whereas ensuring that caching doesn't negatively impact data security would be a holistic function.

### Triggered vs. Continuous
Triggered fitness functions are run like tests, often as part of continuous integration or deployment pipelines. Continuous functions run constantly, like monitors with thresholds. For instance, a test verifying adherence to RESTful verb responses would be triggered, while a monitor tracking transaction times in a production system would be continuous.

### Automated vs. Manual
Ideally, most fitness functions are automated, just like tests. However, some might involve manual checks or a combination of both.
It's important to note that:

### Differentiate between fitness functions and traditional tests

Fitness functions have an objective outcome. They may have a simple pass/fail result, or they could be dynamic based on the context, like allowing lower performance at higher scales within a certain limit.

They are distinct from traditional tests like unit, functional, or user acceptance tests. Fitness functions focus on architectural characteristics, while traditional tests verify business requirements. 


If the problem being checked can be described without knowledge of the business domain, it's likely an architectural characteristic and therefore a candidate for a fitness function.

|Feature|Unit Test|Fitness Function|
|--|--|--|
|Focus|Correctness of individual code units|Adherence to architectural characteristics
|Scope|Isolated code units (methods, functions)|System-level or component-level|
|Domain Knowledge|May require domain knowledge to define expected behavior|Can be defined without specific domain knowledge|
|Examples|Testing a method for calculating interest on a loan|Checking for cyclic dependencies, enforcing layering rules, measuring response times|

# Applications of Fitness Functions in Evolutionary Architecture
One of the key benefits of using fitness functions is the ability to automate architectural governance. Instead of relying on vague terms like "maintainability," architects can define concrete, testable measures that ensure desired architectural qualities.


## Examples

1. A fitness function could check for cyclomatic complexity above a defined threshold, preventing overly complex methods from being introduced. This promotes maintainability by forcing developers to adhere to good design principles like the Strategy pattern.

1. Another function could enforce the use of a standardized logging library by preventing developers from using the built-in logging mechanism. This ensures consistency across projects.
Benefits of Fitness Function-Driven Development

1. Proactive Issue Detection: Fitness functions help to catch potential issues early in the development process, rather than discovering problems later, when they are more costly and difficult to fix.

1. Continuous Architectural Integrity: By continuously running fitness functions, teams can ensure that the architectural qualities they value are maintained over time, preventing architectural drift.

1. Evidence-Based Governance: Fitness functions provide concrete data to justify architectural decisions and track progress in addressing technical debt.

1. Automated Enforcement of Standards: Fitness functions automate the enforcement of architectural standards, freeing architects from constant manual checks and reducing the risk of human error.


## Examples in Practice

1. Netflix's Simian Army: Netflix uses a suite of tools, including Chaos Monkey and Conformity Monkey, to test their architecture's resilience and adherence to architectural rules.

1. GitHub's Scientist: GitHub's Scientist tool allows them to conduct experiments with new architectural components, ensuring they function correctly and perform well before being fully integrated.


# Examples of Fitness Functions by Architectural Characteristic
The sources provide examples of fitness functions across different architectural characteristics:

## Code Quality:

1. Code complexity checks using tools like JDepend or ArchUnit
1. Enforcement of naming conventions and coding standards
1. Prevention of the use of generic exceptions
1. Restrictions on accessing specific libraries or classes directly

## Resiliency:

1. Chaos engineering experiments using tools like Netflix's Chaos Monkey to simulate failures and test system behavior under stress
1. Synthetic transactions to monitor performance and availability of production systems

## Security:

1. Checks for open ports, SQL injection vulnerabilities, and other security weaknesses
1. Enforcement of using specific security libraries and frameworks
1. Monitoring for changes in open source library license terms

## Performance:

1. Response time measurements for specific transactions or operations
1. Load testing to determine system behavior under heavy traffic
1. Monitoring for resource utilization (CPU, memory, network) to identify bottlenecks

## Scalability:

1. Tests to verify that the system can handle increasing workloads without significant performance degradation
1. Checks for appropriate use of caching and other techniques to improve scalability

## Maintainability:

1. Code complexity checks to prevent overly complex and difficult-to-understand code
1. Enforcement of modularity and loose coupling between components

## Compliance:

1. Verification that data is handled according to relevant regulations (e.g., GDPR, HIPAA)
1. Tests to ensure that logging practices comply with audit requirements

## Operability:
1. Checks for the presence of runbooks, documentation, and alerting mechanisms
1. Verification of proper logging practices to support troubleshooting and incident management



# Evolutionary Database Design
The principles of evolutionary architecture and fitness functions also apply to database design. The same benefits of iterative development, continuous integration, and automated testing can be applied to database schemas and data migrations.

## Key practices in evolutionary database design include:

1. Close collaboration between DBAs and developers
1. Version controlling all database artifacts
1. Treating database changes as migrations
1. Providing each developer with their own database instance
1. Continuously integrating database changes

### Automating database refactorings
These practices ensure that the database can evolve along with the application, minimizing disruption and supporting agile development processes.
Overall, architectural fitness functions are an essential tool in building and maintaining evolutionary architectures that can adapt to changing requirements, technologies, and business needs. They provide a concrete, measurable way to ensure architectural integrity and support the long-term health and success of software systems.

# Practical advice for implementing and managing fitness functions

1. Start with the most critical architectural characteristics. Focus on those that are essential for your application's success and have the most potential impact on its long-term health and maintainability.

1. Continuously evolve your fitness functions. Architectural goals and constraints change over time, so your fitness functions should adapt accordingly.

1. Integrate fitness functions into your development process. This ensures that they are regularly checked and enforced, preventing architectural drift.

Use a combination of automated and manual checks. While automation is ideal, some characteristics might require manual inspection.

# Designing an Automated Fitness Functions Auditor (AFFA)

[Refer the article here](./AutomatedFitnessFunctionsAuditor.md)

Please check the [99x ProductCentral](https://productcentral.io) for a fitting AFFA reference architecture template for your product.
