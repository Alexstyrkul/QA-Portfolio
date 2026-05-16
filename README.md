# QA Portfolio — Alex Styrkul

QA Engineer at Readdle. This repository is an overview of my QA skills and hands-on projects: mobile UI automation, API testing, CI/CD pipelines, and bug reporting.

---

## Table of Contents

- [Resume](#resume)
- [About Me](#about-me)
- [Mobile Automation](#mobile-automation)
- [API Testing](#api-testing)
- [CI/CD](#cicd)
- [Bug Reporting](#bug-reporting)

---

## Resume

[View My Resume](./resume.md)

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
- Coverage: login flow, add folder, add photo from gallery

```
FileManagerUITests/
├── Base/
│   ├── BaseTest.swift       # Base test class with setup/teardown and shared helpers
│   └── AppScreen.swift      # Base Page Object with shared wait logic
├── Screens/
│   ├── FileListScreen.swift    # Page Object — file list screen
│   ├── LoginScreen.swift       # Page Object — login screen
│   └── SetPasswordScreen.swift # Page Object — set password screen
└── Tests/
    ├── LoginTests.swift         # Login and password setup flow
    ├── AddFolderTests.swift     # Create folder, empty name validation
    └── AddPhotoTests.swift      # Open photo picker from file list
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

I follow a structured approach to bug reporting — clear reproduction steps, expected vs actual behaviour, environment details, severity classification, and verification test cases.

- [Bug Report Template](./Bug-Reporting/Template.md)
- [Sample Bug Report](./Bug-Reporting/Sample-Bug-Report.md)
