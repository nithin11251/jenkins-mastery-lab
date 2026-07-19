# ⚙️ Jenkins Installation

This guide explains how to install Jenkins on both **Windows** and **Ubuntu/Linux**. Before installing Jenkins, make sure Java is installed because Jenkins runs on the Java Virtual Machine (JVM).

---

# 📚 Table of Contents

- Introduction
- System Requirements
- Prerequisites
- Installing Jenkins on Windows
- Installing Jenkins on Ubuntu/Linux
- Unlocking Jenkins
- Installing Suggested Plugins
- Creating the First Admin User
- Verifying the Installation
- Common Troubleshooting
- Summary

---

# Introduction

Jenkins is an open-source automation server used to build, test, and deploy software applications. It runs as a standalone application and requires Java to be installed on the system.

Jenkins can be installed on:

- Windows
- Linux
- macOS
- Docker
- Kubernetes

In this section, we will focus on Windows and Ubuntu/Linux installation.

---

# System Requirements

Before installing Jenkins, verify that your system meets the following requirements.

| Component | Requirement |
|-----------|-------------|
| Operating System | Windows 10/11 or Ubuntu 22.04+ |
| RAM | Minimum 2 GB (4 GB Recommended) |
| Disk Space | Minimum 10 GB |
| Java | Java 21 or later |
| Internet | Required for downloading packages and plugins |

---

# Prerequisites

Before installing Jenkins:

- Install Java (JDK or JRE)
- Verify Java installation
- Ensure administrator/root access
- Ensure internet connectivity

To verify Java installation:

### Windows

```cmd
java -version
```

### Linux

```bash
java -version
```

If Java is installed correctly, the version information will be displayed.

---

# Installing Jenkins on Windows

## Step 1: Download Jenkins

Visit the official Jenkins website and download the latest **Long-Term Support (LTS)** Windows installer (`.msi`).

The LTS version is recommended because it is stable and receives regular security updates.

---

## Step 2: Run the Installer

Locate the downloaded `.msi` file.

Double-click it to start the installation wizard.

Click **Next** to continue.

---

## Step 3: Choose Installation Directory

Select the location where Jenkins should be installed.

The default installation directory is usually:

```text
C:\Program Files\Jenkins
```

You can keep the default location or choose another directory.

Click **Next**.

---

## Step 4: Configure the Jenkins Service

During installation, Jenkins asks how it should run.

You can allow Jenkins to run as a Windows Service.

Running Jenkins as a service ensures that it starts automatically whenever Windows starts.

Click **Next**.

---

## Step 5: Select the Port Number

Jenkins uses **Port 8080** by default.

Default URL:

```text
http://localhost:8080
```

If Port 8080 is already occupied by another application, choose a different available port.

---

## Step 6: Configure Java

The installer automatically detects the installed Java version.

If Java is not detected:

- Install Java
- Restart the installer
- Select the correct Java installation path

Continue the installation.

---

## Step 7: Install Jenkins

Click **Install**.

The installer copies all required files and configures the Jenkins service.

After installation completes, click **Finish**.

---

# Installing Jenkins on Ubuntu/Linux

## Step 1: Update Package Information

```bash
sudo apt update
```

Updating the package list ensures the latest package information is available.

---

## Step 2: Install Java

Install Java using:

```bash
sudo apt install fontconfig openjdk-21-jre
```

Verify installation:

```bash
java -version
```

---

## Step 3: Add the Jenkins Repository Key

```bash
sudo wget -O /etc/apt/keyrings/jenkins-keyring.asc \
https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
```

The key verifies that Jenkins packages are trusted.

---

## Step 4: Add the Jenkins Repository

```bash
echo "deb [signed-by=/etc/apt/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian-stable binary/" | sudo tee \
/etc/apt/sources.list.d/jenkins.list > /dev/null
```

This adds the official Jenkins package repository.

---

## Step 5: Update Packages Again

```bash
sudo apt update
```

This refreshes the package list including the Jenkins repository.

---

## Step 6: Install Jenkins

```bash
sudo apt install jenkins
```

This installs Jenkins and its required files.

---

## Step 7: Start Jenkins

Start the Jenkins service:

```bash
sudo systemctl start jenkins
```

Enable Jenkins to start automatically after every system reboot:

```bash
sudo systemctl enable jenkins
```

Check service status:

```bash
sudo systemctl status jenkins
```

If the service is active, Jenkins has been installed successfully.

---

# Unlocking Jenkins

After installation, open your browser.

```
http://localhost:8080
```

The first screen asks for the **Administrator Password**.

### Windows

The password is located in:

```text
C:\ProgramData\Jenkins\.jenkins\secrets\initialAdminPassword
```

### Linux

Retrieve it using:

```bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

Copy the password and paste it into the Jenkins Unlock page.

Click **Continue**.

---

# Install Suggested Plugins

After unlocking Jenkins, choose:

```
Install Suggested Plugins
```

Jenkins downloads and installs the most commonly used plugins required for building projects.

This process may take several minutes depending on your internet speed.

---

# Create the First Administrator

Once plugins are installed, Jenkins asks you to create the first administrator account.

Provide the following details:

- Username
- Password
- Full Name
- Email Address

Click **Save and Continue**.

---

# Verify Installation

Open your browser and visit:

```text
http://localhost:8080
```

If the Jenkins Dashboard appears without errors, the installation is successful.

You are now ready to create your first Jenkins project.

---

# Common Troubleshooting

## Java Not Found

Verify Java installation:

```bash
java -version
```

If Java is missing, install Java and restart Jenkins.

---

## Jenkins Service Not Running

Restart Jenkins.

Linux:

```bash
sudo systemctl restart jenkins
```

Windows:

Restart the Jenkins service from the **Services** application.

---

## Port Already in Use

If another application is using Port 8080:

- Stop the conflicting application
- Or configure Jenkins to use another port

---

## Unable to Access Jenkins

Check whether the Jenkins service is running.

Also verify that your firewall allows access to the configured port.

---

# Summary

In this chapter, you learned:

- Jenkins system requirements
- Prerequisites
- Windows installation
- Ubuntu/Linux installation
- Unlocking Jenkins
- Installing plugins
- Creating the administrator account
- Verifying the installation
- Common troubleshooting steps

The next chapter covers the **Jenkins Dashboard**, where you'll explore the Jenkins user interface, menus, and basic navigation.