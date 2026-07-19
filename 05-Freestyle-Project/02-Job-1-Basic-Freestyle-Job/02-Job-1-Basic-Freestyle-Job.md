# 🚀 Job 1 - Creating Your First Jenkins Freestyle Project

This chapter demonstrates how to create and execute your **first Freestyle Project** in Jenkins.

The objective of this job is to understand the complete lifecycle of a Jenkins job—from creating the project to viewing the build results and console output.

This is the first practical exercise every Jenkins beginner should perform.

---

# 📚 Table of Contents

- Objective
- Prerequisites
- Step 1 - Open Jenkins Dashboard
- Step 2 - Create a New Job
- Step 3 - Configure the Job
- Step 4 - Save the Job
- Step 5 - Build the Job
- Step 6 - View Build History
- Step 7 - View Console Output
- Jenkins Workspace
- Build Lifecycle
- Common Errors
- Best Practices
- Summary

---

# Objective

In this practical exercise, you will learn how to:

- Create a Freestyle Project
- Configure a Jenkins job
- Execute the job manually
- View build history
- Read Console Output
- Understand where Jenkins stores project files

---

# Prerequisites

Before starting this exercise, make sure:

- Jenkins is installed.
- Jenkins service is running.
- You can access Jenkins Dashboard.
- You have administrator access.

Open Jenkins in your browser.

```text
http://localhost:8080
```

Login using your administrator credentials.

---

# Step 1 - Open Jenkins Dashboard

After logging into Jenkins, you will see the Dashboard.

The Dashboard is the starting point for creating and managing Jenkins jobs.

From here you can:

- Create new jobs
- Configure existing jobs
- Run builds
- View build history
- Manage Jenkins

📸 Screenshot:

```
images/jenkins-dashboard.png
```

---

# Step 2 - Create a New Freestyle Project

Click

```
New Item
```

A page appears asking for:

- Job Name
- Project Type

Enter a project name.

Example:

```
First-Freestyle-Job
```

Under **Project Type**, select

```
Freestyle Project
```

Click

```
OK
```

Jenkins creates a new Freestyle Project.

📸 Screenshot:

```
images/new-item.png
```

---

# Step 3 - Configure the Job

The Configuration page opens automatically.

For this first project, no special configuration is required.

You may optionally enter a description.

Example:

```
My first Jenkins Freestyle Project
```

Leave the remaining options unchanged.

Click

```
Save
```

or

```
Apply
```

📸 Screenshot:

```
images/configure-job.png
```

---

# Step 4 - Build the Job

After saving, Jenkins redirects to the project page.

To execute the project, click

```
Build Now
```

Jenkins immediately starts executing the build.

A build number appears under

```
Build History
```

Example

```
#1
```

Every execution creates a new build number.

```
#1

#2

#3

...
```

📸 Screenshot:

```
images/build-now.png
```

---

# Step 5 - Monitor Build Status

After clicking **Build Now**, Jenkins displays the build status.

Possible build statuses include:

| Status | Meaning |
|----------|----------|
| ✅ Success | Build completed successfully |
| ❌ Failed | Build failed |
| ⚠️ Unstable | Tests failed |
| ⏳ Running | Build is currently executing |
| ⛔ Aborted | Build was cancelled |

Successful builds are displayed with a blue or green indicator depending on the Jenkins theme.

---

# Step 6 - View Build History

Every build executed by Jenkins is stored.

Click the build number.

Example

```
#1
```

The build page displays:

- Build Number
- Build Status
- Build Time
- Build Duration
- Console Output
- Changes

This history helps track previous executions.

📸 Screenshot:

```
images/build-history.png
```

---

# Step 7 - View Console Output

The Console Output shows everything Jenkins executed during the build.

To view it:

```
Project
      ↓
Build Number
      ↓
Console Output
```

The Console Output contains:

- Build information
- Execution logs
- Success messages
- Errors
- Warnings

Example:

```text
Started by user admin

Building in workspace C:\ProgramData\Jenkins\.jenkins\workspace\First-Freestyle-Job

Finished: SUCCESS
```

Console Output is the first place to check whenever a build fails.

📸 Screenshot:

```
images/console-output.png
```

---

# Jenkins Workspace

Whenever Jenkins executes a job, it creates a workspace.

The workspace stores:

- Source Code
- Temporary Files
- Build Files
- Artifacts

On Windows, the default workspace location is:

```text
C:\ProgramData\Jenkins\.jenkins\workspace
```

Each job gets its own workspace directory.

Example:

```text
workspace/

├── First-Freestyle-Job/

├── Java-Project/

└── Maven-Project/
```

This workspace location aligns with the notes in your PDF. :contentReference[oaicite:0]{index=0}

---

# Freestyle Job Lifecycle

```text
Open Jenkins
        │
        ▼
Click New Item
        │
        ▼
Enter Job Name
        │
        ▼
Select Freestyle Project
        │
        ▼
Configure Job
        │
        ▼
Save
        │
        ▼
Click Build Now
        │
        ▼
Build Executes
        │
        ▼
View Console Output
        │
        ▼
Build Success
```

---

# Common Errors

## Jenkins Service Not Running

**Problem**

```
This site can't be reached
```

**Solution**

Start the Jenkins service.

---

## Build Failed

Possible reasons:

- Incorrect configuration
- Missing plugins
- Invalid build commands

Check **Console Output** for details.

---

## Build Not Starting

Possible reasons:

- Jenkins service stopped
- Executor unavailable
- Job disabled

---

# Best Practices

- Use meaningful project names.
- Add descriptions to every project.
- Review Console Output after every build.
- Keep only required build history.
- Delete unused jobs.
- Backup important Jenkins jobs.

---

# Interview Questions

## What is a Freestyle Project?

A Freestyle Project is a Jenkins job that allows users to automate tasks through a graphical interface.

---

## What happens when you click Build Now?

Jenkins immediately starts executing the configured job and creates a new build.

---

## Where can you check build logs?

Build logs are available in the **Console Output** section.

---

## What is Build History?

Build History stores information about all previous executions of a Jenkins job.

---

## Where are Jenkins workspaces stored?

On Windows, Jenkins stores workspaces under:

```text
C:\ProgramData\Jenkins\.jenkins\workspace
```

This forms the foundation for the next exercise, where you'll create a **Java Freestyle Project** that compiles and executes Java code using Jenkins.