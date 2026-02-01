# CI Lab Project

## Installation Guide

Steps to install Jenkins on macOS using Homebrew.

## User Manual

Instructions to run Freestyle and Multibranch Pipeline jobs.

## Troubleshooting Guide

Common Jenkins, Git, and Maven issues with solutions.

## Jenkins Jobs

- Freestyle CI Job
- Multibranch Pipeline Job

# CI Lab Project

## Project Overview

This project demonstrates the implementation of Continuous Integration (CI)
using Jenkins. It includes a Freestyle CI job and a Multibranch Pipeline job
that automatically build and test a Java application using Maven whenever
code changes are pushed to GitHub.

The objective of this project is to understand CI concepts, Jenkins job
configuration, plugin management, and automated build execution.

---

## Technologies Used

- Jenkins (LTS)
- Java (JDK 21)
- Maven
- Git & GitHub
- macOS
- Jenkins Plugins (Pipeline, GitHub, Maven, JUnit, Docker, etc.)

---

## Prerequisites

Ensure the following are installed:

- Java JDK 21
- Git
- Maven
- Jenkins (installed via Homebrew)
- GitHub account

---

## Installation Guide (macOS)

1. Install Homebrew:

   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

2. Install Jenkins:

   ```bash
   brew install jenkins-lts
   brew services start jenkins-lts
   ```

3. Access Jenkins:

   ```
   http://localhost:8080
   ```

4. Unlock Jenkins using the initial admin password and install suggested plugins.

---

## Jenkins Job Configuration

### 1. Freestyle CI Job

- Connects to GitHub repository
- Uses Maven to run `mvn clean test`
- Publishes JUnit test reports
- Archives build artifacts
- Displays console output for each build

### 2. Multibranch Pipeline Job

- Automatically detects branches from GitHub
- Uses `Jenkinsfile` for pipeline definition
- Executes stages:
  - Checkout
  - Build & Test
- Displays pipeline execution using Pipeline Overview
- Publishes JUnit test results

---

## How to Run the Jobs

1. Open Jenkins Dashboard
2. Select the job:
   - `Freestyle-CI-Job` or
   - `Multibranch-CI-Pipeline`
3. Click **Build Now**
4. View Console Output, Tests, and Pipeline Overview

---

## Repository Structure

```
CILabProject/
├── src/
│   ├── main/java/com/muj/ci/Calculator.java
│   └── test/java/com/muj/ci/CalculatorTest.java
├── pom.xml
├── Jenkinsfile
├── docker/Dockerfile
├── scripts/
│   ├── build.sh
│   └── deploy.sh
└── README.md
```

---

## Troubleshooting Guide

- **Maven not found**: Configure Maven in Jenkins Global Tool Configuration
- **GitHub API rate limit**: Use GitHub Personal Access Token (PAT)
- **JUnit reports not visible**: Ensure correct report path:
  ```
  **/target/surefire-reports/*.xml
  ```

---

## Author

**Aryan Mishra**  
B.Tech CSE – CI/CD Lab Project  
Manipal University Jaipur
