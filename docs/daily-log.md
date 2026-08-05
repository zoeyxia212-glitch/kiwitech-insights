# Daily Learning Log

Add one section after each learning day by following `daily-learning-plan.md`. Keep earlier mistakes and reflections because they show learning progress.

The daily project-learning limit is 120 minutes. Record the actual time spent. When the limit is reached, carry unfinished work into the next learning day instead of studying late.

## Day 1 — Java Environment and CSV Contract

- Date: 2026-08-03
- Time spent: __ / 120 minutes
- Watched: Java P1, P6, P8, P15 and P16
- Built: A runnable `Day1` Java program, a job-listing CSV contract and a sample CSV containing six valid rows and two intentionally invalid rows
- Tests/checks: The Java program finished with exit code 0; the CSV contains the expected eight columns and invalid examples for a missing title and an incorrectly formatted date
- Bug I solved: I initially created the Java file outside the `src` source root, so IntelliJ IDEA would not compile it as part of the module. I moved it into `src` and used the Java class naming convention.
- Why this design: The CSV contract defines valid job-listing data before the same fields are implemented in Java, PostgreSQL, the Spring Boot API and the React interface.
- Alternative and trade-off: Free-form dates and seniority values would make data entry easier, but controlled formats make validation, filtering and market analysis more reliable.
- English explanation: Today I ran my first Java program and designed the CSV data contract for KiwiTech Insights. I used required fields and controlled formats so that imported job data can be validated and analysed consistently.
- Tomorrow's first action: Learn Java variables and data types, then map each CSV field to an appropriate Java type.

### Day 1 checklist

- [√] Run `java -version` and record the installed version.
- [√] Watch Java P1, P6, P8, P15 and P16; skip installation details that are already understood.
- [√] Define the CSV fields: `external_id`, `title`, `company`, `location`, `seniority`, `description`, `posted_date` and `source_url`.
- [√] Define whether each field is required, its format and an example value.
- [√] Create eight sample rows, including one missing title and one invalid date.
- [√] Explain the differences between the JDK, JRE and JVM, and why the project targets Java The JDK provides the tools needed to develop and compile Java applications. It includes the Java runtime, while the JVM executes the compiled Java bytecode. KiwiTech Insights targets Java 17 because it is a stable long-term support version widely used in production.
## Day 2 — Java Literals and Variables

- Date: 2026-08-04
- Time spent: __ / 60 minutes
- Watched: Java P18–P20
- Built: A Java program that represents one job listing using variables
- Tests/checks: The program compiled and printed all eight job-listing fields
- What I learned: I learned how to declare, assign and update variables, and how to choose an appropriate data type.
- Why this design: Appropriate data types define which values are valid and help prevent errors.
- Bug I solved: I changed `externalId` from `int` to `String` because its value contains letters and a hyphen.
- Tomorrow's first action: Learn Java data types and choose stronger types for job-listing fields
## Day 3 — Java Data Types and Identifiers

- Date: 2026-08-05
- Time spent: __ / 120 minutes
- Watched: Java P23–P25
- Built: A Java field-type mapping for the job-listing domain
- Tests/checks: Declared job-import variables using String, int, double, boolean, char and long
- What I learned: I learned how to select data types based on the values that a variable needs to store.
- Why this design: Stronger domain types such as LocalDate and Seniority prevent invalid data and make business logic clearer.
- Bug I solved: I added the L suffix to a long literal and used single quotes for a char value.
- Tomorrow's first action: Learn keyboard input and Java operators.