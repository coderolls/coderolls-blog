---
layout: post
title:  "Introduction to Java Technology (Language and Platform)"
author: gaurav
categories: [ Java, Core Java ]
description: "Java is a general purpose computer programming language. Let's get introduce to an amazing programming language."
featured: false
---

Java is a general purpose computer programming language. Let's get introduce to an amazing programming language.

## Introduction

James Gosling, Mike Sheridan, and Patrick Naughton initiated the Java language project in June 1991. The project was aimed to develop software for a wide variety of network devices and embedded systems.

When the project started they have chosen C++ language, but later they understood the difficulties with C++ and found that these problems could be addressed by creating entirely new simple, reliable, secure language, as a result, the language platform is developed which is simple, secure, distributed, network-based end-user application ranging from worldwide web to the embedded systems.

The language was initially called ‘Oak’ after an oak tree outside the Gosling’s office, then it was as a project Green and finally Java after Java coffee.

The Java language compiled code can run on any platform that supports Java, we don’t have to compile Java code again and again.

When we say Java Technology, it is both programming language as well as a platform.

Let’s understand Java as a programming language.

## Java As a Programming Language

Java is a high-level programming language. It is a concurrent, class-based, object-oriented programming language.

![Java Language Feature](/assets/images/2019-11-29/java-language-feature.webp)

We will understand Java by the following simple terms, let’s discuss one by one,

### **Simple:**

The primary feature of the Java language is, it is Simple. It means anyone can learn java language without extensive programmer training, it is simple to understand.

The James Gosling designed the Java language syntax on the basis of the C/C++ language, so most of the people are already familiar with it. They can easily migrate from the C/C++ to Java.

The fundamental concepts of the Java language can be grasped easily. As a result, it will take very little time to be productive quickly.

### **Object-Oriented:**

To understand object-oriented feature we should understand object technology. In object technology, the classes used to construct the objects and it is intended to be reusable software components.

The Java programming language is an object-oriented programming language, it means every element in java is an object. Though, there is an exception of primitive data types.

As per the  [dept of CS, UTSA](http://www.cs.utsa.edu/~cs3443/ch01.html)

> “Using a modular, object-oriented design and implementation approach can make software development more productive. Object-oriented programs are often easier to understand, correct and modify.”
> 
> –  [Dept of CS, UTSA](http://www.cs.utsa.edu/~cs3443/ch01.html)

### **Robust:**

We can develop highly reliable software using the Java programming language, it provides both compile time as well as run-time checking.

The extremely simple memory management model makes java robust.

The new object is created using a simple ‘new’ keyword, no explicit programmer-defined pointer datatype, no more pointer, and automatic garbage collection. The unused objects will be collected by the Java garbage collector and will be destroyed carefully.

Automatic memory management concept avoids/eliminate all the errors that previously occur in the C/C++ memory management concern. If any, that can be quickly solved.

### **Secure:**

Java technology is developed for distributed environments., so security was always a high priority. Language creators have addressed the concern very well.

The application written in the Java programming language is very secure and can not be easily disturbed by the unauthenticated outsider’s code.

### **Architecture neutral:**

Java applications can be deployed on various hardware platforms and so the application should be executed on the various operating system. This is achieved by using the bytecode.

The Java compiler produces the bytecode, that can be executed on the Java virtual machine ( It is a virtual environment, we will discuss the term in detail below) atop of any operating system.

### **Portable:**

Architecture neutrality solves the binary distribution problem as well as the cross-platform problem. Java code is portable, it can be transported easily.  

You don’t have to compile java code, again and again, it saves time.

Unlike C, Java programs are the same on every platform. Sizes of the basic data types and arithmetic operators are the same on every platform, there is no database incompatibility.

### **Performance:**

The performance was always in consideration while designing the Java language. The Java garbage collector runs as a low priority thread, which makes memory available whenever required, it leads to better performance.

### **Multithreaded:**

Java language supports multithreading. You can run multiple tasks simultaneously using a thread.

## The Java Platform

We are familiar with platforms like Microsoft Windows, Mac OS, Linux distributions. The platform contains hardware as well as software where the code runs.

Unlike others, the Java Platform is a software-only platform.

The Java platform contains

1.  Java Virtual Machine
2.  Java Application Programming Interface (API)

### 1. Java Virtual Machine

The architecture-neutral and portable language platform of Java Technology are called as Java Virtual Machine.

It is a virtual machine on top of the operating system. The Java compiler compiles the java code and creates a bytecode(.class) file. This bytecode runs on the JVM to create machine-specific code.

Java Virtual Machine is behind the platform-independent nature of the Java programming language.

Because the Java compiler on any platform creates the same bytecode (.class). And then we can run that byte code on any Java Virtual Machine.

If you don’t understand this won’t be a worry, I have given a diagram below which will clear all the concepts.

That’s why we can call that Java programming language is platform-independent.

We can write java code on any machine and run on any machine. It is called “Write Once, Run Anywhere”.( WORA)

But when we say about JVM, JVM itself is platform-dependent, yes I have written correctly. Java Virtual Machine is platform dependent.

We need a machine-specific Java Virtual Machine. When you visit the JDK download page there are different JDK for windows and different JDK for MAC OS.

Java Virtual Machine is platform-dependent and that’s why it can create a machine-specific instruction set for your code from the bytecode you have given.

### 2. Java Application Programming Interface (API)  

In Java API, there are a large number of ready-made components that can be used to develop an application. It consists of classes, interfaces, packages along with its methods, fields, and constructors.

The purpose of using Java API is to minimize the number of lines in the code. The most basic programming tasks are performed using Java APIs classes and packages.

## How Java code works

In Java, the source code is written in a file with a .java extension.

When we compile this file with the javac compiler, the .class file will be generated. The .class file contains the bytecode, the bytecode can run on the Virtual Machine.

Refer the following diagram,

![How Java Code Works](/assets/images/2019-11-29/how-java-code-works.webp)

What was your experience when you started learning Java, share with us in the comment section.

Or use Google Pay/UPI at gkukade54@okicici
