# Volde
<p align="center">
  <img src="https://github.com/dsh311/Volde/blob/main/docs/Volde.gif" alt="Volde" width="700"/>
</p>

**Volde** is a runtime introspection and analysis toolkit for exploring the internal behavior of running processes.

It is a research project focused on runtime introspection, reverse engineering techniques, and scripting-driven experimentation within a live process.

Volde is implemented as a dynamically loaded library (DLL) that, once loaded into a process in a controlled research environment, provides an interactive interface for inspecting modules, analyzing exported functions, and performing runtime experimentation.

> ⚠️ **Research Use Only**  
> This project is intended strictly for educational and research purposes.  
> All testing and experimentation were performed in isolated lab environments.

---

# Overview

Modern software security research often requires visibility into the internal state of running applications. **Volde** explores how a dynamically loaded analysis toolkit can provide runtime visibility, scripting capabilities, and low-level inspection tools directly inside a process.

Volde provides capabilities for:

- Process module inspection  
- Exported function discovery  
- Function disassembly  
- Runtime function invocation  
- Embedded scripting  
- .NET runtime hosting

The project explores how flexible runtime analysis tooling can be built by combining native code, scripting environments, and runtime instrumentation techniques.

---

# Features

## Interactive Runtime Interface

Volde presents a graphical interface within the host process, allowing researchers to interactively explore the runtime environment and perform analysis tasks.

---

## Process Module Inspection

Enumerates all modules loaded within the current process, providing visibility into:

- Loaded DLLs
- Module base addresses
- Module metadata

---

## Exported Function Discovery

Volde can enumerate exported functions for loaded modules, enabling quick inspection of available callable entry points within the process.

---

## Function Disassembly

Exported functions can be disassembled using the **Zydis** disassembly engine, allowing low-level inspection of:

- Assembly instructions
- Function structure
- Control flow

---

## Dynamic Function Invocation

Volde supports dynamic invocation of arbitrary functions at runtime using:

- **Lua scripting**
- **libffi** for foreign function interface support

This allows researchers to experiment with calling functions dynamically without compiling additional code.

---

## Embedded Lua Scripting

Lua is embedded into Volde to provide a flexible scripting environment for automating runtime experiments.

Example use cases include:

- Automating function calls
- Inspecting memory structures
- Rapid prototyping of runtime experiments
- Driving analysis workflows

---

## .NET Runtime Hosting

Volde supports dynamically loading and hosting:

- **.NET Framework**
- **.NET Core / .NET**

This enables managed assemblies to be loaded directly into the host process and executed alongside native code.

---

# Technologies Used

- **C++** — native runtime implementation  
- **Lua** — embedded scripting environment  
- **libffi** — dynamic function invocation  
- **Zydis** — x86/x64 disassembly  
- **Windows API**  
- **.NET Runtime Hosting APIs**

---

# Learning Goals

Volde was developed to explore several areas relevant to software security research and reverse engineering:

- Runtime program analysis
- Process introspection
- Binary disassembly
- Dynamic function invocation
- Scripting-driven experimentation
- Native and managed runtime interoperability

---

# Example Workflow

A typical workflow when using Volde might involve:

1. Loading the Volde analysis DLL into a test process.
2. Inspecting loaded modules within the process.
3. Enumerating exported functions from a module.
4. Disassembling selected functions to analyze behavior.
5. Using Lua scripts to call functions or automate analysis tasks.
6. Loading managed assemblies through the embedded .NET runtime for further experimentation.

---

# Project Status

Volde is a **research prototype** created for experimentation and learning. The project demonstrates how runtime analysis tooling can be built by combining native code, scripting environments, and disassembly libraries.

---

# Disclaimer

This project is provided strictly for **educational and research purposes**.

It was developed and tested exclusively in isolated lab environments. The techniques explored in this project are commonly used in debugging, reverse engineering, and software security research.
