# Product Plan

## Problem

New Zealand junior developers need evidence-based answers to questions such as:

- Which technical skills appear most often in current roles?
- Which combinations are common, such as Java + Spring Boot + React?
- How do Auckland, Wellington and Christchurch differ?
- What changes between junior, intermediate and senior roles?
- Which skill gap should a candidate address first?

## Target user

A graduate, career changer or junior developer applying for software roles in New Zealand.

## Core user journey

1. Import a CSV containing job listings.
2. Review accepted and rejected rows.
3. Browse listings with location, seniority and skill filters.
4. View skill frequency and common technology combinations.
5. Enter current skills and receive a transparent gap analysis.
6. Export analysed data for Power BI.

## MVP boundaries

The first version will use manually collected or sample CSV data. It will not scrape job websites or call paid AI APIs. Recommendations will be rule-based and explainable.

## Success criteria

- Invalid CSV rows produce useful validation messages.
- Imported listings persist in the database.
- Skill counts can be reproduced from source data.
- Filters and rankings work through REST APIs and the React UI.
- Tests run automatically after every push.
- The README enables another developer to run the project.

## Interview value

The project demonstrates requirements analysis, OOP, file operations, collections, algorithms, REST API design, relational data modelling, testing, CI/CD and practical product thinking.

