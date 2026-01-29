eBay Search

Overview

This project is a web test automation solution implemented using Playwright to automate and validate the search flows on the eBay website.
The solution was designed to be simple, maintainable, and scalable, while following automation best practices such as the Page Object Model (POM) and data-driven testing.

Automated User Flow

The automated scenario covers the following steps:

Navigate to https://www.ebay.com/

Validate that the user has successfully landed on the main page.

Search for a specific keyword (mazda mx-5).

Validate the obtained search results.

Log the number of returned search results.

Apply a filter Transmission → Manual

Log whether the filter option was available and applied successfully.

Framework Design
Technology Stack

Language: TypeScript

Automation Tool: Playwright

Test Runner: Playwright Test Runner

Design Pattern: Page Object Model (POM)

Reporting: Allure Report

Test Data Source: External JSON file

Project Structure
├── Tests
│   └── SearchTCs.spec.ts
├── pages
│   ├── MainPage.ts
│   └── ResultsPage.ts
├── TestData
│   └── products.json
├── playwright.config.ts
├── package.json
└── README.md

Page Object Model

The solution follows the Page Object Model to ensure clean separation between test logic and UI interactions:

1-MainPage

Validates landing on the main page using a unique UI element (Start now)

Performs the search action using test data passed from the test layer.

2-ResultsPage

Retrieves search results.

Returns the total number of results.

Validates that result titles contain the searched keyword.

Applies the Transmission → Manual filter with proper conditional handling.

Test data is intentionally kept outside the page classes and passed from the test layer to ensure better maintainability and reusability.

Reporting

The project uses Allure Report to provide a clear and detailed execution report:

Displays test execution status (pass/fail)

Logs the number of returned search results

Logs whether the "Manual" transmission filter was visible and applied

This ensures better visibility and traceability of test execution outcomes.

How to Run the Tests
1-Install Dependencies
npm install

2-Run Tests with Allure Report
npm run test:allure


This command:

Executes the Playwright tests

Generates the Allure results

Automatically opens the Allure report (for both passed and failed test runs)
