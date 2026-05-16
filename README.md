# QA Portfolio — Alex Styrkul

QA Engineer at Readdle. This repository is an overview of my QA skills and hands-on projects: mobile UI automation, API testing, CI/CD pipelines, and bug reporting.

---

## Table of Contents

- [About Me](#about-me)
- [Mobile Automation](#mobile-automation)
- [API Testing](#api-testing)
- [CI/CD](#cicd)
- [Bug Reporting](#bug-reporting)

---

## About Me

I work as a QA Engineer at Readdle, focusing on mobile (iOS) test automation and API quality. My stack covers XCUITest for native iOS testing, Cypress and Python/pytest for web and API layers, and CircleCI for running tests automatically on every push.

📧 alexroast3@gmail.com

---

## Mobile Automation

**[FileManager-UITests](https://github.com/Alexstyrkul/FileManager-UITests)**

XCUITest automation suite for an open-source iOS FileManager app.

- Language: Swift
- Framework: XCUITest (Apple native)
- Pattern: Page Object Model
- Coverage: file navigation, create/delete/rename operations, file preview

```
FileManager-UITests/
├── Base/          # BaseTest + AppScreen (Page Object base)
├── Screens/       # FileListScreen, FileDetailScreen
└── Tests/         # NavigationTests, FileOperationsTests, FilePreviewTests
```

---

## API Testing

**[clickup-goal-api-tests](https://github.com/Alexstyrkul/clickup-goal-api-tests)**

REST API tests for ClickUp using Python/pytest. Covers full task lifecycle: create → get → update → delete.

- Language: Python
- Framework: pytest + requests
- Auth: token-based via environment variables
- Assertions: status codes + response body validation

---

## CI/CD

**[clickup-goal-api-tests / .circleci](https://github.com/Alexstyrkul/clickup-goal-api-tests/tree/main/.circleci)**

CircleCI pipeline that runs Cypress UI tests on every push and stores an Allure report as a build artifact.

Pipeline steps:
1. Install system dependencies
2. Install Node/Cypress
3. Run tests
4. Generate Allure report
5. Store artifact

---

## Bug Reporting

I use GitHub Issues for structured bug reporting with clear steps to reproduce, expected vs actual results, and environment details.

Example: [Issues in FileManager-UITests](https://github.com/Alexstyrkul/FileManager-UITests/issues)
