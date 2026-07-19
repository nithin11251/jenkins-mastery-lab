# 📦 Job 3 - Build a Maven Project Using a Jenkins Freestyle Project

In this practical exercise, you will configure a **Freestyle Project** to build a Maven application stored in a GitHub repository.

Unlike the previous Java project, Maven automatically manages project dependencies, compilation, testing, and packaging through the `pom.xml` file.

This exercise introduces Maven build commands and Jenkins tool configuration.

---

# 📚 Table of Contents

- Objective
- Prerequisites
- Maven Project Structure
- Step 1 - Create a Maven Project
- Step 2 - Upload Project to GitHub
- Step 3 - Create a Freestyle Job
- Step 4 - Configure Source Code Management
- Step 5 - Configure Build Steps
- Step 6 - Build the Project
- Step 7 - View Console Output
- Configuring Maven, Git and JDK in Jenkins
- Common Maven Commands
- Common Errors
- Best Practices
- Interview Questions
- Summary

---

# Objective

After completing this exercise, you will learn how to:

- Build Maven projects in Jenkins
- Connect Jenkins with a GitHub Maven repository
- Execute Maven commands
- Configure Maven tools
- Analyze Maven build logs

---

# Prerequisites

Before starting, ensure you have:

- Jenkins installed
- Java JDK installed
- Maven installed
- Git installed
- GitHub account

Since these were covered in previous chapters, only Maven-specific configuration is discussed here.

---

# Maven Project Structure

Create a Maven project.

Example

```text
maven-project/

├── src/
│   ├── main/
│   └── test/
│
├── pom.xml
│
└── README.md
```

The **pom.xml** file is the heart of every Maven project.

According to your notes, both the **src** folder and **pom.xml** should be uploaded to the GitHub repository before creating the Jenkins job. :contentReference[oaicite:0]{index=0}

---

# Step 1 - Create a Maven Project

Create a Maven project locally.

Example

```text
maven-project
```

Verify the project contains:

- src/
- pom.xml

Commit the project to GitHub.

---

# Step 2 - Upload the Project to GitHub

Push the Maven project repository.

Example

```text
https://github.com/username/maven-project.git
```

Ensure:

- pom.xml exists
- src folder exists

---

# Step 3 - Create a Freestyle Project

This step is identical to **Job 1**.

Refer to:

> **02-Job-1-Basic-Freestyle-Job**

Create a new **Freestyle Project** and open the **Configure** page.

---

# Step 4 - Configure Source Code Management

Open

```
Source Code Management
```

Select

```
Git
```

Enter

```
Repository URL
```

Example

```text
https://github.com/username/maven-project.git
```

Specify the branch.

Example

```text
main
```

📸 Suggested Screenshot

```
images/git-scm.png
```

---

# Step 5 - Configure Build Steps

Scroll to

```
Build
```

Click

```
Add Build Step
```

Select

```
Execute Windows batch command
```

Enter one of the following Maven commands.

Compile project

```bat
mvn compile
```

Package application

```bat
mvn package
```

Clean previous build

```bat
mvn clean
```

Clean and Package

```bat
mvn clean package
```

According to your notes, these are the commonly used commands during the build process. :contentReference[oaicite:1]{index=1}

📸 Suggested Screenshot

```
images/maven-build-step.png
```

---

# Step 6 - Build the Project

Click

```
Build Now
```

Jenkins performs the following actions.

1. Clone GitHub repository

2. Read pom.xml

3. Download required dependencies

4. Compile source code

5. Package application

6. Display build result

---

# Step 7 - View Console Output

Open

```
Build History

↓

Build Number

↓

Console Output
```

Example

```text
Checking out Git repository...

Reading pom.xml...

Downloading dependencies...

Compiling source...

BUILD SUCCESS
```

📸 Suggested Screenshot

```
images/maven-console-output.png
```

---

# Configuring Maven, Git and JDK

Before building Maven projects, Jenkins must know where these tools are installed.

Open

```
Manage Jenkins

↓

Tools
```

Configure:

- Git
- JDK
- Maven

You can either:

- Install automatically

or

- Specify the local installation path

Finally click

```
Apply

↓

Save
```

This configuration step is specifically mentioned in your notes. :contentReference[oaicite:2]{index=2}

📸 Suggested Screenshot

```
images/tool-configuration.png
```

---

# Common Maven Commands

| Command | Description |
|----------|-------------|
| mvn clean | Deletes previous build files |
| mvn compile | Compiles source code |
| mvn test | Runs tests |
| mvn package | Creates JAR/WAR |
| mvn install | Installs artifact locally |
| mvn clean package | Clean and package project |

---

# Common Errors

## mvn is not recognized

Cause

Maven is not installed or configured.

Solution

Configure Maven under

```
Manage Jenkins → Tools
```

---

## pom.xml not found

Cause

Repository structure is incorrect.

Solution

Ensure the repository root contains

```
pom.xml
```

---

## Dependency download failed

Cause

Internet connection or repository issue.

Solution

Verify network connectivity and Maven repository access.

---

# Best Practices

- Always commit `pom.xml`.
- Keep dependencies updated.
- Use `mvn clean package` for production builds.
- Configure Maven through Jenkins Tools.
- Store source code in Git.

---

# Interview Questions

### What is Maven?

Maven is a build automation and dependency management tool for Java projects.

---

### What is pom.xml?

It is the Project Object Model file that defines project configuration, dependencies, plugins, and build information.

---

### Which Maven command creates a JAR file?

```text
mvn package
```

---

### Where do you configure Maven in Jenkins?

```
Manage Jenkins

↓

Tools
```

---


This exercise extends the Freestyle Project by introducing Maven-based builds, as outlined in your handwritten notes. :contentReference[oaicite:3]{index=3}