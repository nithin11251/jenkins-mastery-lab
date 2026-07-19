# ☕ Job 2 - Build and Run a Java Program Using a Jenkins Freestyle Project

In this practical exercise, you will create a **Freestyle Project** that downloads Java source code from a GitHub repository, compiles it using the Java compiler (`javac`), and executes it using the Java Virtual Machine (`java`).

This exercise introduces **Source Code Management (SCM)** and **Build Steps**, two essential concepts in Jenkins.

---

# 📚 Table of Contents

- Objective
- Prerequisites
- Project Workflow
- Step 1 - Create a Java Project
- Step 2 - Upload Project to GitHub
- Step 3 - Create a Freestyle Job
- Step 4 - Configure Source Code Management
- Step 5 - Configure Build Steps
- Step 6 - Save the Job
- Step 7 - Build the Project
- Step 8 - View Console Output
- Expected Output
- Common Errors
- Best Practices
- Interview Questions
- Summary

---

# Objective

After completing this exercise, you will be able to:

- Clone source code from GitHub
- Configure Git in Jenkins
- Compile Java source code
- Execute Java programs
- Understand Build Steps
- Analyze Console Output

---

# Prerequisites

Ensure the following software is installed.

- Jenkins
- Java JDK
- Git
- GitHub Account

Also verify that:

- Jenkins is running
- Git is installed
- Java is available in the system PATH
- The Java project has been uploaded to GitHub

---

# Project Workflow

```text
Java Project
      │
      ▼
Upload to GitHub
      │
      ▼
Create Freestyle Job
      │
      ▼
Clone Repository
      │
      ▼
Compile Java Program
      │
      ▼
Run Java Program
      │
      ▼
Console Output
```

---

# Step 1 - Create a Java Project

Create a simple Java project.

Example:

```
JavaDemo
```

Project structure

```text
JavaDemo/

└── HelloWorld.java
```

Example program

```java
public class HelloWorld {

    public static void main(String[] args) {

        System.out.println("Hello Jenkins");

    }

}
```

---

# Step 2 - Upload the Project to GitHub

Create a GitHub repository.

Example

```
java-demo
```

Push the Java project.

Repository structure

```text
java-demo/

└── HelloWorld.java
```

Once uploaded, copy the repository URL.

Example

```
https://github.com/username/java-demo.git
```

---

# Step 3 - Create a Freestyle Project

Open Jenkins Dashboard.

Click

```
New Item
```

Enter

```
Java-Freestyle-Project
```

Select

```
Freestyle Project
```

Click

```
OK
```

📸 Screenshot

```
images/create-job.png
```

---

# Step 4 - Configure Source Code Management

Open

```
Configure
```

Locate

```
Source Code Management
```

Select

```
Git
```

Paste your repository URL.

Example

```
Repository URL

https://github.com/username/java-demo.git
```

Choose the branch.

Usually

```
main
```

or

```
master
```

If the repository is private, configure Git credentials.

📸 Screenshot

```
images/git-configuration.png
```

---

# Step 5 - Configure Build Steps

Scroll down to

```
Build Steps
```

Click

```
Add build step
```

Choose

```
Execute Windows batch command
```

Enter the following commands.

```bat
javac HelloWorld.java

java HelloWorld
```

Explanation

### javac

Compiles Java source code.

Produces

```
HelloWorld.class
```

---

### java

Runs the compiled class.

Displays the program output.

📸 Screenshot

```
images/build-step.png
```

---

# Step 6 - Save the Job

Click

```
Apply
```

Then click

```
Save
```

The project configuration is now complete.

---

# Step 7 - Execute the Build

Open the project.

Click

```
Build Now
```

Jenkins performs the following actions automatically.

1. Downloads source code from GitHub

2. Opens the workspace

3. Executes

```bat
javac HelloWorld.java
```

4. Executes

```bat
java HelloWorld
```

5. Displays the result

---

# Step 8 - View Console Output

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
Started by user admin

Cloning repository...

Compiling Java source...

Running Java program...

Hello Jenkins

Finished: SUCCESS
```

📸 Screenshot

```
images/console-output.png
```

---

# Understanding Build Steps

The Build Step section tells Jenkins what commands should be executed.

Example

```bat
javac HelloWorld.java

java HelloWorld
```

Jenkins executes each command one after another.

If any command fails, the build stops immediately.

---

# Expected Output

```text
Hello Jenkins

Finished: SUCCESS
```

---

# Common Errors

## javac is not recognized

Cause

Java JDK is not configured.

Solution

- Install JDK
- Configure JAVA_HOME
- Add Java to PATH

---

## Repository not found

Cause

Incorrect GitHub URL

Solution

Verify

- Repository URL
- Branch name
- Credentials

---

## Could not find main class

Cause

Incorrect class name

Solution

Run

```bat
java HelloWorld
```

instead of

```bat
java HelloWorld.java
```

---

## Compilation Failed

Cause

Java syntax errors.

Solution

Compile locally first.

---

# Best Practices

- Keep one Java project per repository.
- Always use Git.
- Use meaningful repository names.
- Verify Java locally before pushing.
- Review Console Output after every build.
- Use the latest LTS version of Java.

---

# Interview Questions

## What is Source Code Management in Jenkins?

SCM connects Jenkins with version control systems such as Git, GitHub, GitLab, and Bitbucket.

---

## Why is Git used in Jenkins?

Git allows Jenkins to download the latest source code before executing a build.

---

## What is the difference between javac and java?

| Command | Purpose |
|----------|----------|
| javac | Compiles Java source code |
| java | Executes compiled Java class |

---

## What is Build Step?

A Build Step is a command or task executed by Jenkins during a build.

---

## Where can build errors be found?

In the Console Output.

---


This exercise is based on configuring a Freestyle Java project with Git SCM and Windows batch commands (`javac` and `java`), as described in your handwritten notes. :contentReference[oaicite:0]{index=0}

The next exercise demonstrates how to build a **Maven Project** using a Freestyle Job and Maven commands such as `mvn clean`, `mvn compile`, and `mvn package`.