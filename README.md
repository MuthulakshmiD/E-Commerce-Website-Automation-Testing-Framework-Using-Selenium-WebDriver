# E-Commerce-Website-Automation-Testing-Framework-Using-Selenium-WebDriver
# E-Commerce Website Automation Testing Framework Using Selenium WebDriver

## Project Overview

**SeleniumAutomationFramework** is a web automation testing framework developed using **Java, Selenium WebDriver, TestNG, and Maven**.

The framework follows the **Page Object Model (POM)** design pattern to automate important user workflows of an e-commerce web application. It is designed to provide reusable, maintainable, and scalable automation test scripts.

The automation is performed on the **Swag Labs** demo e-commerce website.

---

# Application Under Test

## Website Name

**Swag Labs**

## Website URL

```
https://www.saucedemo.com/
```

## Description

Swag Labs is a demo e-commerce application provided by Sauce Labs for practicing automation testing. It contains common shopping workflows such as user login, product selection, adding products to cart, checkout, and logout.

---

# Project Objective

The main objectives of this automation framework are:

- Automate e-commerce workflows using Selenium WebDriver
- Implement Page Object Model (POM)
- Create reusable page classes
- Execute test cases using TestNG
- Manage project dependencies using Maven
- Build a maintainable automation framework

---

# Technology Stack

| Component | Technology |
|-----------|------------|
| Programming Language | Java 21 |
| Automation Tool | Selenium WebDriver 4.35.0 |
| Testing Framework | TestNG 7.10.2 |
| Build Tool | Maven |
| IDE | IntelliJ IDEA |
| Design Pattern | Page Object Model (POM) |
| Browser | Google Chrome |
| Logging | SLF4J Simple Logger |
| Version Control | Git/GitHub |

---

# Maven Dependencies

The project uses the following dependencies:

## Selenium Java

Used for:

- Browser automation
- Web element interaction
- WebDriver control

Version:

```
4.35.0
```

---

## TestNG

Used for:

- Test execution
- Test annotations
- Assertions
- Test management

Version:

```
7.10.2
```

---

## SLF4J Simple Logger

Used for:

- Logging test execution information
- Managing framework logs

Version:

```
2.0.13
```

---

# Project Structure

```
SeleniumAutomationFramework

src
 └── test
      └── java

          com.bank

          ├── base
          │     └── BaseTest.java
          │
          ├── pages
          │     ├── LoginPage.java
          │     ├── DashboardPage.java
          │     ├── ProductPage.java
          │     ├── CartPage.java
          │     ├── CheckoutPage.java
          │     └── LogoutPage.java
          │
          └── tests
                ├── LoginTest.java
                ├── AddToCartTest.java
                ├── CheckoutTest.java
                └── LogoutTest.java

pom.xml
README.md
```

---

# Framework Architecture

```
Test Classes

      |
      ↓

Page Object Classes

      |
      ↓

Selenium WebDriver

      |
      ↓

Chrome Browser

      |
      ↓

Swag Labs Application
```

---

# Page Object Model (POM)

The framework follows the Page Object Model design pattern.

## Benefits

- Improves code readability
- Provides reusable methods
- Separates test logic from page elements
- Reduces code duplication
- Makes framework maintenance easier

---

# BaseTest.java

## Purpose

BaseTest manages browser initialization and cleanup.

## Responsibilities

- Launch Chrome browser
- Configure WebDriver
- Open application URL
- Close browser after test execution

## TestNG Annotations

### @BeforeMethod

Executed before every test.

Used for:

- Browser setup
- Application launch

### @AfterMethod

Executed after every test.

Used for:

- Closing browser
- Releasing resources

---

# Page Classes

## LoginPage.java

Handles login page operations.

### Elements

- Username field
- Password field
- Login button

### Method

```
login(String username, String password)
```

### Functionality

- Enter username
- Enter password
- Click login button

---

## DashboardPage.java

Used for validating successful login.

### Validation

Checks Products page availability.

### Method

```
getPageTitle()
```

Expected Result:

```
Products
```

---

# Test Scenarios

## 1. Login Test

Flow:

```
Open Website

↓

Enter Username

standard_user

↓

Enter Password

secret_sauce

↓

Click Login

↓

Verify Products Page

↓

Test Passed
```

---

## 2. Add To Cart Test

Flow:

```
Login

↓

Select Product

↓

Add Product To Cart

↓

Verify Cart Details
```

---

## 3. Checkout Test

Flow:

```
Login

↓

Add Product

↓

Open Cart

↓

Enter Customer Details

↓

Complete Checkout

↓

Verify Order Success
```

---

## 4. Logout Test

Flow:

```
Login

↓

Open Menu

↓

Click Logout

↓

Verify Login Page
```

---

# Test Credentials

Username:

```
standard_user
```

Password:

```
secret_sauce
```

---

# Test Execution Result

Example execution:

```
Total Tests Run : 1
Passed          : 1
Failures        : 0
Skipped         : 0
```

---

# Future Enhancements

## Explicit Wait Implementation

Replace:

```
Thread.sleep()
```

with:

```
WebDriverWait
```

Benefits:

- Improved synchronization
- Faster execution
- More reliable tests

---

## Additional Framework Features

Planned enhancements:

- Screenshot capture on test failure
- TestNG XML test suite
- Extent Reports integration
- Data-driven testing using Excel
- GitHub repository integration
- CI/CD pipeline integration

---

# How To Run The Project

## Prerequisites

Install:

- Java JDK 21
- Maven
- IntelliJ IDEA
- Google Chrome

---

## Install Dependencies

Run:

```
mvn clean install
```

---

## Execute Test Cases

Run:

```
mvn test
```

