# Jenkins Pipeline Design – SIT223 8.2C Task 1

This document describes a secure DevSecOps pipeline with seven stages, identifying tools and their purposes.

## Stage 1: Source Code Management

- **Purpose:** Fetch code from a version control system (e.g., GitHub).
- **Tool:** Git, GitHub
- **Security:** Use of personal access tokens or SSH keys for secure access.

## Stage 2: Build

- **Purpose:** Compile the source code and manage dependencies.
- **Tool:** Maven, Gradle, or npm
- **Security:** Integrate dependency scanning tools such as OWASP Dependency-Check.

## Stage 3: Static Code Analysis

- **Purpose:** Detect code-level vulnerabilities and maintain code quality.
- **Tool:** SonarQube, Checkmarx, or ESLint
- **Security:** Prevent insecure or poor-quality code from advancing in the pipeline.

## Stage 4: Unit Testing

- **Purpose:** Verify that individual components work as intended.
- **Tool:** JUnit, Mocha, Jest
- **Security:** Helps ensure the correctness of secure functions and logic.

## Stage 5: Integration Testing

- **Purpose:** Test how components interact with each other.
- **Tool:** Postman, Newman, Selenium
- **Security:** Detect potential security issues at the integration level (e.g., misconfigured API endpoints).

## Stage 6: Security Testing (SAST/DAST)

- **Purpose:** Scan the application for security vulnerabilities.
- **Tool:** OWASP ZAP, Snyk, Trivy
- **Security:** Perform automated security scans to detect CVEs and common vulnerabilities.

## Stage 7: Deployment

- **Purpose:** Deploy the tested and verified code to a staging or production environment.
- **Tool:** Docker, Kubernetes, or simple SCP/SSH deployment
- **Security:** Ensure deployment uses secure practices, such as signed images and protected environment variables.

## Summary Table

| Stage                | Tool               | Security Focus                           |
| -------------------- | ------------------ | ---------------------------------------- |
| Source Code          | GitHub             | Token/SSH authentication                 |
| Build                | Maven, npm         | Dependency scanning                      |
| Static Code Analysis | SonarQube, ESLint  | Code quality and vulnerability detection |
| Unit Testing         | Jest, Mocha        | Validate component-level logic           |
| Integration Testing  | Postman, Selenium  | Validate system interaction              |
| Security Testing     | OWASP ZAP, Snyk    | Identify known vulnerabilities           |
| Deployment           | Docker, Kubernetes | Secure deployment practices              |
