# Competition Management System - Project Setup Summary Report

## 1. Project Overview
The system is designed to manage competitors in a competition, calculate their scores, and generate reports.

## 2. Project Structure
We created a project with the following structure:


├── src/
│ ├── main/
│ │ └── java/
│ │ ├── Competitor.java
│ │ ├── CompetitorList.java
│ │ ├── Manager.java
│ │ └── Name.java

## 3. Setup Process
- Created a batch script for Windows to set up the project structure.
- The script creates all necessary directories and files.
- Empty Java files were created for the main classes: Competitor, CompetitorList, Manager, and Name.
- A sample data file (competitors.txt) was created with example competitor data.
- A .gitignore file was set up to exclude unnecessary files from version control.
- A README.md file was created with basic project information and instructions.
- A build.gradle file was set up for Gradle configuration, including dependencies and tasks.
- A tasks.json file was created for VS Code to easily run Gradle tasks.

## 4. Key Components

### 4.1 Java Classes
- **Competitor**: Represents an individual competitor with attributes like number, name, level, scores, and an extra attribute.
- **CompetitorList**: Manages a collection of competitors and provides methods for adding, removing, and retrieving competitors.
- **Manager**: Handles file I/O and report generation.
- **Name**: Represents a competitor's name with first, middle, and last name components.

### 4.2 Build System
Gradle was chosen as the build system for this project. The build.gradle file includes:
- Java and Application plugins
- JUnit Jupiter for testing
- Main class specification (Manager)
- JavaDoc generation configuration

## 5. Next Steps
- Implement the Java classes using the provided templates.
- Write unit tests for all classes in the CompetitorTest.java file.
- Implement the score calculation logic in the Competitor class.
- Develop the report generation functionality in the Manager class.
- Write comprehensive JavaDoc comments for all classes, especially CompetitorList.
- Create class and activity diagrams for the project report.


## 6. Conclusion
The project structure and build system are now set up and ready for development. This setup provides a solid foundation for implementing the Competition Management System according to the assignment requirements. The use of Gradle and VS Code tasks will streamline the development process, allowing for easy building, testing, and documentation generation.


## CLASS DIAGRAM

![Picture](https://github.com/user-attachments/assets/8f31cd54-98c6-44db-8736-63d643e6b2b0)



```java
import utils.Manager;

public class Main {
    public static void main(String[] args) {
        Manager manager = new Manager();
        manager.run();
    }
}
```
