# learnDaml

A beginner-friendly project for learning [Daml](https://www.daml.com/) — a smart contract language for building distributed applications. This project uses **Daml SDK v2.10.3** and includes example templates and scripts to get you started.

---

## Project Structure

```
learnDaml/
├── daml.yaml              # Project configuration
└── daml/
    ├── Main.daml          # Asset template with Give choice
    └── HelloWorld.daml    # Hello World script
```

---

## Prerequisites

- macOS (Apple Silicon or Intel)
- [Eclipse Adoptium JDK 17+](https://adoptium.net)
- Daml SDK
- Visual Studio Code

---

## Setup Guide

### 1. Install JDK (Eclipse Adoptium)

The Daml SDK requires **Java JDK 11 or higher** (JDK 17 recommended).

1. Go to [https://adoptium.net](https://adoptium.net)
2. Select:
   - **Version:** 17 (LTS) or latest
   - P.S: _I am using the latest version which is 25_
   - **Operating System:** macOS
   - **Architecture:**
     - Apple Silicon → `AArch64`
     - Intel Mac → `x64`
3. Download and run the `.pkg` installer
4. Follow the on-screen installation steps

The JDK installs to:
```
/Library/Java/JavaVirtualMachines/
```

---

### 2. Set `JAVA_HOME` Environment Variable

#### Check available JDKs

```bash
/usr/libexec/java_home -V
```

Example output:
```
Matching Java Virtual Machines (1):
    25.0.2 (arm64) "Eclipse Adoptium" - "OpenJDK 25.0.2"
    /Library/Java/JavaVirtualMachines/temurin-25.jdk/Contents/Home
```

#### Add `JAVA_HOME` to your shell profile

For **zsh** (default on macOS):

```bash
nano ~/.zshrc
```

Add the following lines at the bottom:

```bash
export JAVA_HOME=$(/usr/libexec/java_home)
export PATH=$JAVA_HOME/bin:$PATH
```

Save and exit: `Ctrl+X` → `Y` → `Enter`

Reload your shell:

```bash
source ~/.zshrc
```

> **Using bash?** Edit `~/.bash_profile` instead of `~/.zshrc`.

---

### 3. Verify JDK Installation

```bash
java -version
```

Expected output:
```
openjdk 25.0.2 2026-01-20 LTS
OpenJDK Runtime Environment Temurin-25.0.2+10 (build 25.0.2+10-LTS)
OpenJDK 64-Bit Server VM Temurin-25.0.2+10 (build 25.0.2+10-LTS, mixed mode, sharing)
```

Also verify `JAVA_HOME`:

```bash
echo $JAVA_HOME
```

Expected:
```
/Library/Java/JavaVirtualMachines/temurin-25.jdk/Contents/Home
```

---

### 4. Install Daml SDK

```bash
curl -sSL https://get.daml.com/ | sh
```

Restart your terminal, then verify the installation:

```bash
daml version
```

---

### 5. Install the Daml VS Code Extension

1. Open **Visual Studio Code**
2. Go to the **Extensions** panel (`Cmd+Shift+X`)
3. Search for `Daml`
4. Install the extension published by **Digital Asset**

---



## Resources

- [Daml Documentation](https://docs.daml.com)
- [Daml GitHub](https://github.com/digital-asset/daml)
- [Eclipse Adoptium (JDK)](https://adoptium.net)
- [Daml SDK Release Notes](https://docs.daml.com/support/release-notes.html)