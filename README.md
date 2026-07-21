# Selenium Automation Framework

## Project Overview

**Project Name:** Selenium Automation Framework

The Selenium Automation Framework is a Java-based test automation framework built using **Maven** and **Selenium WebDriver**. The framework follows the **Page Object Model (POM)** design pattern to create a scalable, maintainable, and reusable automation structure.

The framework separates:
- Test scripts
- Page objects
- Base configurations
- Reusable utilities

This separation improves code readability, maintenance, and future enhancements.

---

# Technology Stack

| Technology | Purpose |
|------------|---------|
| Java | Programming language |
| Selenium WebDriver | Web UI automation |
| Maven | Project build and dependency management |
| TestNG/JUnit | Test execution framework |
| WebDriver Manager | Browser driver management |
| Page Object Model (POM) | Design pattern for maintainable automation |

---

# Project Folder Structure

```
SeleniumAutomationFramework/
│
├── pom.xml
│
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/
│   │   │       └── bank/
│   │   │           │
│   │   │           ├── Main.java
│   │   │           │
│   │   │           ├── base/
│   │   │           │   └── BaseTest.java
│   │   │           │
│   │   │           ├── pages/
│   │   │           │   ├── LoginPage.java
│   │   │           │   └── DashboardPage.java
│   │   │           │
│   │   │           ├── tests/
│   │   │           │   └── LoginTest.java
│   │   │           │
│   │   │           └── utils/
│   │   │
│   │   └── resources/
│   │
│   └── test/
│       └── java/
│
├── target/
│
└── .mvn/
```

---

# Package Structure

```
com.bank
│
├── Main
│
├── base
│     └── BaseTest
│
├── pages
│     ├── LoginPage
│     └── DashboardPage
│
├── tests
│     └── LoginTest
│
└── utils
```

---

# File Description

## pom.xml

Maven configuration file.

Contains project dependencies such as:

- Selenium WebDriver
- TestNG/JUnit
- WebDriver Manager
- Required Maven plugins

It manages project build, execution, and dependency handling.

---

## Main.java

**Location:**

```
src/main/java/com/bank/Main.java
```

The main entry point of the Java application.

Used for:
- Starting the application
- Performing basic project validation
- Testing initial framework setup

---

# Base Package

## BaseTest.java

**Location:**

```
base/BaseTest.java
```

The base class for all test cases.

Responsibilities:

- Initialize WebDriver
- Configure browser settings
- Open application URL
- Manage browser lifecycle
- Close browser after test execution

Example flow:

```
@BeforeMethod
    Launch Browser

@Test
    Execute Test Case

@AfterMethod
    Close Browser
```

---

# Pages Package

The pages package contains Page Object Model classes.

Each class represents a web page and contains:

- Web elements
- Page actions
- Business methods

---

## LoginPage.java

**Location:**

```
pages/LoginPage.java
```

Represents the application login page.

Contains:

### Web Elements

- Username field
- Password field
- Login button

### Methods

```
enterUsername()
enterPassword()
clickLogin()
```

Example usage:

```
LoginPage login = new LoginPage(driver);

login.enterUsername("user");
login.enterPassword("password");
login.clickLogin();
```

---

## DashboardPage.java

**Location:**

```
pages/DashboardPage.java
```

Represents the dashboard page after successful login.

Contains methods for:

- Validating successful login
- Reading dashboard information
- Performing dashboard actions

Example:

```
verifyDashboardDisplayed()
```

---

# Tests Package

## LoginTest.java

**Location:**

```
tests/LoginTest.java
```

Contains automated login test scenarios.

Responsibilities:

- Uses LoginPage methods
- Executes login workflow
- Validates login success

Example test flow:

```
Open Application
        |
Enter Username
        |
Enter Password
        |
Click Login
        |
Verify Dashboard
```

---

# Utils Package

**Location:**

```
utils/
```

Stores reusable helper classes.

Examples:

## Screenshot Utility

Used for capturing screenshots during failures.

## Excel Reader

Used for reading test data from Excel files.

## Wait Helper

Provides reusable explicit wait methods.

## Configuration Reader

Reads values from configuration files.

Example:

```
config.properties
```

Currently, the utility folder does not contain implementation files.

---

# Resources Folder

**Location:**

```
src/main/resources/
```

Stores project configuration and test resources.

Examples:

```
config.properties
test-data files
logging configuration
```

Currently empty.

---

# Test Folder

**Location:**

```
src/test/java/
```

Used for additional:

- Test classes
- Test suites
- Integration tests

Keeps test execution code separate from application framework code.

---

# Target Folder

```
target/
```

Generated automatically by Maven.

Contains:

- Compiled `.class` files
- Build artifacts
- Test reports

Manual editing is not required.

---

# Page Object Model (POM) Design

This framework follows the Page Object Model approach.

## Benefits:

### Reusability

Common page actions are written once and reused.

### Maintainability

UI changes require updates only in page classes.

### Readability

Test cases contain business flows instead of Selenium commands.

### Scalability

New pages and test cases can easily be added.

---

# Execution Steps

## 1. Clone Repository

```
git clone <repository-url>
```

---

## 2. Navigate to Project Folder

```
cd SeleniumAutomationFramework
```

---

## 3. Install Dependencies

```
mvn clean install
```

---

## 4. Execute Tests

Using Maven:

```
mvn test
```

---

# Future Enhancements

Possible improvements:

- Add reporting using Extent Reports
- Add screenshot capture on failure
- Add data-driven testing
- Add CI/CD integration
- Add parallel execution support
- Add logging framework
- Add cross-browser testing support

---

# Conclusion

The Selenium Automation Framework provides a structured approach for automating web applications using Java and Selenium WebDriver.

By following the Page Object Model design pattern, the framework delivers:

- Clean architecture
- Better maintainability
- Reusable components
- Easy test expansion
- Improved automation efficiency
