# Eclipse IDE Installation Guide

This guide will walk you through the steps to install the Eclipse IDE on your computer. Eclipse is a popular integrated development environment (IDE) primarily used for Java development, though it supports other programming languages through plugins.

---

## Prerequisites

- A system running **Windows**, **macOS**, or **Linux**
- **Java Development Kit (JDK)** installed (Eclipse requires a JDK to run)

### Installing JDK (if not already installed)

1. Go to the [Oracle JDK Downloads](https://www.oracle.com/java/technologies/javase-downloads.html) page.
2. Download the latest version for your operating system.
3. Install the JDK and configure your system’s environment variables if needed.

---

## Step-by-Step Eclipse Installation

### Step 1: Download Eclipse Installer

- Visit the official Eclipse website: [https://www.eclipse.org/downloads/](https://www.eclipse.org/downloads/)
- Click on **"Download x86_64"** for your operating system.

### Step 2: Launch the Installer

- On **Windows/macOS**: Run the downloaded `.exe` or `.dmg` file.
- On **Linux**: Extract the tar file and run the `eclipse-inst` executable.

### Step 3: Choose Eclipse IDE for Java Developers

- From the list of available packages, select **"Eclipse IDE for Java Developers"**
- You can also choose other versions based on your use case (e.g., Eclipse for Web or C++ Development).

### Step 4: Installation Settings

- Choose the installation folder (default is usually fine).
- Make sure the correct JDK is detected.
- Click **Install** and accept the license agreements when prompted.

### Step 5: Launch Eclipse

- After installation, click **Launch**.
- Select a workspace directory (this is where your projects will be saved).

---

## Verifying the Installation

1. Open Eclipse.
2. Go to `Help > About Eclipse IDE` to check version and installation details.
3. Create a new Java project to verify that the IDE is working correctly.

---

## Optional: Install Plugins

You can enhance Eclipse functionality by installing plugins:

- Go to `Help > Eclipse Marketplace`
- Search and install plugins like:
  - **EclEmma** for code coverage
  - **PyDev** for Python development
  - **Maven Integration** for project management

---


- **Eclipse won’t start**: Make sure the correct JDK is installed and configured.

---

For more help, visit the [Eclipse Documentation](https://help.eclipse.org/) or [Eclipse Forums](https://www.eclipse.org/forums/).

