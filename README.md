# Simple Maven Project for Jenkins CI/CD

This is a basic Java Maven project with JUnit tests, designed for Jenkins CI/CD and Git integration.

## Structure
- `pom.xml`: Maven configuration with JUnit dependency
- `src/main/java/com/example/App.java`: Main Java class
- `src/test/java/com/example/AppTest.java`: JUnit test class
- `Jenkinsfile`: Jenkins pipeline for build and test

## Usage
1. Clone the repository using Git.
2. Build and test locally with:
   ```
   mvn clean compile
   mvn test
   ```
3. Use Jenkins to run the pipeline defined in `Jenkinsfile`.
