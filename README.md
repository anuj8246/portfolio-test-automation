# portfolio-test-automation

```markdown
# Test Automation Framework

A robust test automation framework supporting  web, mobile and API testing, built with Selenium WebDriver, Appium, RestAssured and Playwright.

## 🏗️ Project Structure


clockwork/
├── 📂 src/
│   ├── 📂 main/
│   │   ├── 📂 java/
│   │   │   ├── 📂 com.qverifi/
│   │   │   │   ├── 📂 app/
│   │   │   │   │   ├── 📂 pages/         # Page Objects
│   │   │   │   │   └── 📂 components/    # Reusable Components
│   │   │   │   ├── 📂 core/
│   │   │   │   │   ├── 📂 driver/        # Driver Management
│   │   │   │   │   ├── 📂 config/        # Configuration
│   │   │   │   │   └── 📂 utils/         # Utilities
│   │   │   │   └── 📂 dsl/               # Domain Specific Language
│   │   │   └── 📂 resources/
│   │   │       ├── 📄 log4j2.xml
│   │   │       └── 📄 config.properties
│   └── 📂 test/
│       ├── 📂 java/
│       │   └── 📂 com.qverifi/
│       │       └── 📂 tests/              # Test Classes
│       └── 📂 resources/
│           └── 📂 testrunners/            # TestNG XML Files
└── 📄 pom.xml


## 🚀 Features

- **Multi-Platform Support**: Web (Selenium) and Mobile testing
- **Page Object Model**: Structured page objects with component-based architecture
- **DSL Support**: Fluent interface for writing readable tests
- **Multiple Browser Support**: Chrome, Firefox, Safari
- **Grid Support**: Selenium Grid integration
- **Reporting**: Extent Reports integration
- **Logging**: Log4j2 implementation
- **Data Driven**: Excel data support with Poiji
- **Email Testing**: MailSlurp integration
- **CI/CD Ready**: Maven profiles for different environments

## 🛠️ Tech Stack

- Java 17
- Selenium WebDriver 4.23.0
- Playwright 1.44.0
- TestNG 7.10.2
- ExtentReports 5.1.2
- Log4j2 2.23.1
- Maven

## ⚙️ Configuration

### Maven Profiles

1. **Browsers**:
   - Local-Google-Chrome (default)
   - Grid-Google-Chrome
   - Local-Mozilla-Firefox
   - Grid-Mozilla-Firefox
   - Local-Safari-in-local-Docker

2. **Test Suites**:
   - Suite-Smoke (default)
   - Suite-Regression

3. **Environments**:
   - Environment-DEV (default)
   - Environment-QA

## 🏃‍♂️ Running Tests

```bash
# Run default configuration
mvn clean test

# Run with specific profiles
mvn clean test -P Grid-Google-Chrome,Suite-Regression,Environment-QA
```

## 📝 Example Test

```java
@Test(description = "Login Test")
void verifySuccessfulSignIn(TestDataEntity tde) {
    goTo getProperty("app.url");
    at HomePage;
    HomePage.headerComponent().loginButton().click();
    HomePage.loginOverlay()
           .enterUsername(tde.getUsername())
           .enterPassword(tde.getPassword())
           .loginButton()
           .click();
    at DashboardPage;
}
```
```
