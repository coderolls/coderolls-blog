---
layout: post
title:  "Java: The Platform-Independent Programming Language"
author: gaurav
categories: [ Java, Core Java ]
featured: false
toc: true
description: "In this article, we will learn about Java's platform independence and how Java achieves it."
---

In this article, we will learn about [Java's platform](/java-introduction) independence and how Java achieves it.

## Introduction

The software programs are very specific to the hardware and operation systems it is written on. When we write a piece of code on a platform, it will compile and run on that sample platform. But for the diversity and portability of the code or software, it is important that it should run on other platforms too. 

But In practicality, there are some limitations to it. Some programming languages are platform-dependent which means the code written on the platform can run on that platform only. For example C.

But Java is an exception to it.

> **Java is a platform-independent programming language.**
>
> Java achieves platform independence with the help of **bytecode** and **Java Virtual Machine**.

Let's see what does it mean by platform independence.

## What is Platform Independence?

If a code written on one platform can run on any other platform, then it is platform independence.

In Java programming language a program written on a platform can be run on any other platform, provided a JVM is installed.

So, in Java we can **Write Once Run Anywhere (WORA)**.

## How Java Achieves Platform Independence?

When a developer writes a program it is in human readable format. i.e. `.java` file.

When we compile it, the Java compiler converts it to the **bytecode**. i.e. `.class` file. Bytecode is not a native code for a machine. It can be understood by JVMs only. 

Then J**ava Virtual Machine** (JVM) executes the bytecode. At the end, we can see the output of the program.

Let's take an example to understand the process. Assume, the below code is in a HelloWorld.java file.

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello World!");
    }
}
```

![An image showing How Java Achieves Platform Independance.](/assets/images/2023-11-04/java-platform-independent.png)

## Conclusion
1. Java Programming language is a platform independent. We can **Write Once Run Anywhere (WORA)**.
2. Java Virtual Machine (JVM) is not platform-independent. Different Operating systems have different types of executable instructions. So there are different JVMs for different OS.
3. All JVMs can understand the bytecode and convert it to respective executable instructions. This makes Java a platform-independent language.
