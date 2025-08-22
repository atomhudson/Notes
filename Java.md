# Understanding Java

Java is a **platform-independent programming language**.
It works on the principle of **WORA (Write Once, Run Anywhere)** technology, which means you can write Java code once and run it on any platform that has a compatible JVM.

## Java Program Breakdown

A Java program involves three main components:

1. **JVM (Java Virtual Machine)**
2. **JRE (Java Runtime Environment)**
3. **JDK (Java Development Kit)**

## Understanding JVM (Java Virtual Machine)

**Flow of Java Program Execution:**

```
Java Program --> Compiler --> Bytecode --> JVM --> Machine Code --> CPU --> Output
```

* **JVM is platform-dependent**, unlike Java bytecode.
* JVM is an **abstract or virtual machine**; it does not physically exist.
* Different platforms (Windows, macOS, Linux) require different JVM implementations.
* JVM contains a **JIT (Just-In-Time) Compiler**.
* **JIT Compiler** converts Java **bytecode** into **machine code** for faster execution.

**Key Point:** JVM enables platform independence of Java bytecode by providing a consistent runtime environment on any OS.

## Understanding JRE (Java Runtime Environment)

* **JRE = JVM + Java Class Libraries**
* Example Libraries:

  * `java.lang`
  * `java.util`
  * `java.math`
* When your code runs on JVM, it requires certain **libraries** to function properly.
* JRE provides these libraries to JVM for generating bytecode execution.
* You can pass compiled **bytecode** to JRE to run the program, as JVM is embedded inside JRE.

## Understanding JDK (Java Development Kit)

* **JDK is required to write and develop Java programs.**
* Components of JDK:

  * JRE (includes JVM + class libraries)
  * Compiler (`javac`)
  * Debugger
  * Additional development tools
* **JDK = JRE + Development Tools**
* JVM, JRE, and JDK are **platform-dependent**, but **Java bytecode is platform-independent**.

## Diagram: Java Components Overview

`A[Java Program] --> B[Java Compiler (javac)] `

`B --> C[Bytecode (.class files)] `

`C --> D[JVM] `

`D --> E[Machine Code] `

`E --> F[CPU] `

`F --> G[Output]`
