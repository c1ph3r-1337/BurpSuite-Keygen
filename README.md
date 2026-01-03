# Burp Suite – Keygen & Loader Archive (Reference Only)

> ⚠️ **Disclaimer**  
> This repository/folder is provided **for research, learning, and archival reference only**.  
> It documents historical tooling and experiments related to Burp Suite across different Java and Burp versions.  
> It does **not** provide support for license circumvention, nor does it guarantee functionality on modern JVMs.

---

## Overview

This archive contains:

- A **Burp Suite keygen UI** (Swing-based)
- A **loader / Java agent implementation**
- References to **older and newer Burp Suite versions**
- Notes on **Java compatibility changes** (Java 8 → Java 21+)

The purpose is to **record how tooling evolved** and why certain approaches no longer function on modern Java runtimes.

---

## Contents

### 1. Keygen (UI)

- `KeygenDialog.java`
- Swing-based GUI
- Generates license / activation strings
- Uses legacy cryptographic formats for compatibility with older Burp builds

> ℹ️ On modern Burp + Java 21+, generated values are **not accepted**, due to architectural changes in Burp and the JVM.

---

### 2. Loader / Agent

- `Transformer.java`
- Implemented as a **Java Agent** (`premain` / `agentmain`)
- Uses `ClassFileTransformer`
- Designed to modify bytecode at class-load time

This loader exists in **two historical contexts**:

#### Legacy Loader (Java 8 Era)
- Relied on:
  - `-Xbootclasspath/p`
  - JDK shadowing
  - Pre-verification bytecode patching
- Worked only with **old Burp Suite versions**

#### Modern Agent Attempt (Java 17 / 21+)
- Uses:
  - `-javaagent`
  - Instrumentation API
- Loads successfully, but:
  - **Target classes are never exposed for transformation**
  - JVM module system and early verification prevent modification

Result:
> Agent initializes and waits, but no license-related classes are transformable.

---

## Burp Suite Versions Listed

### Older Burp Suite
- Java 8 compatible
- License checks implemented in load-time patchable classes
- Worked with legacy loaders

### Newer Burp Suite (2024+)
- Requires Java 17 / 21+
- Uses:
  - Early initialization
  - Module encapsulation
  - Hardened verification
- License enforcement is **not load-time patchable**

---

## Java Compatibility Summary

| Java Version | Status |
|-------------|--------|
| Java 8 | Legacy loaders worked |
| Java 9–11 | Partially compatible, fragile |
| Java 17 | Mostly blocked |
| Java 21+ | **Architecturally prevented** |

There is **no modern replacement** for removed JVM mechanisms such as bootclasspath injection.

---

## Important Notes

- This archive is **not a working solution** for modern Burp Suite.
- Java 21+ intentionally removes the capability class that legacy loaders depended on.
- Any included code should be treated as:
  - Educational
  - Historical
  - For JVM / reverse-engineering study only

---

## Intended Audience

- Java / JVM learners
- Reverse-engineering students
- Researchers studying:
  - Java agent limitations
  - JVM security evolution
  - Legacy tooling breakage on modern platforms

---

## Final Statement

> Modern Java runtimes are doing exactly what they were designed to do:  
> **prevent this class of runtime modification**.

This repository documents *why* older approaches stopped working—not how to revive them.

---
