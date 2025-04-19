
# Java Maven Build Job with Jenkins

This project demonstrates how to build a simple Java application using **Maven** through **Jenkins**. It is part of the DevOps Internship program focused on understanding the basics of CI/CD pipelines using open-source tools.

---

## Table of Contents

1. [Objective](#objective)  
2. [Tools Used](#tools-used)  
3. [Project Structure](#project-structure)  
4. [Source Code](#source-code)  
5. [Jenkins Setup Guide](#jenkins-setup-guide)  
6. [Expected Output](#expected-output)  
7. [Deliverables](#deliverables)  
8. [Outcomes (What You'll Learn)](#outcomes-what-youll-learn)  
9. [Interview Preparation](#interview-preparation)  

---

## Objective

To learn how to:
- Set up a Java Maven project
- Use Jenkins to automate the build process
- Understand console output and build lifecycle

---

## Tools Used

- **Jenkins** (installed locally or via Docker)
- **Java JDK** 8 or 11
- **Maven**
- **Git** (optional – for local file handling)

---

## Project Structure

```
hello-java-maven/
│
├── pom.xml
└── src/
    └── main/
        └── java/
            └── HelloWorld.java
```

---

## Source Code

### HelloWorld.java

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, Jenkins + Maven!");
    }
}
```

### pom.xml

```xml
<project>
  <modelVersion>4.0.0</modelVersion>
  <groupId>com.example</groupId>
  <artifactId>hello</artifactId>
  <version>1.0</version>
  <build>
    <plugins>
      <plugin>
        <groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-compiler-plugin</artifactId>
        <version>3.8.1</version>
        <configuration>
          <source>1.8</source>
          <target>1.8</target>
        </configuration>
      </plugin>
    </plugins>
  </build>
</project>
```

---

## Jenkins Setup Guide

1. **Start Jenkins using Docker**:
   ```bash
   docker run -p 9090:8080 jenkins/jenkins:lts
   ```

2. **Access Jenkins**:
   - URL: `http://localhost:9090`

3. **Configure Maven in Jenkins**:
   - Go to: `Manage Jenkins` > `Global Tool Configuration`
   - Add Maven (e.g., version 3.8.6)

4. **Create a Jenkins Job**:
   - Create a Freestyle Project
   - In the **Build** section:
     - Choose: *Invoke top-level Maven targets*
     - Set Goal: `clean package`

5. **Save & Build** the job

---

## Expected Output

- The Jenkins **Console Output** should display:  
  ```
  BUILD SUCCESS
  ```

---

## Deliverables

- Java HelloWorld app with Maven setup
- Freestyle Jenkins job configured
- Screenshot of successful Jenkins build

---

## Outcomes (What You'll Learn)

- What a Jenkins job is
- How to trigger builds manually
- How Jenkins uses Maven to compile Java code
- How to read and understand Jenkins console output

---

## Author
 
 Created as part of the **Elevate Labs DevOps Internship** by Srikanth Berla.
 
 ## License
 
 This project is intended for educational purposes.
