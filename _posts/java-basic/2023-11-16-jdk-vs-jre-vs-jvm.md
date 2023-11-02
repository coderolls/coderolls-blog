---
layout: post
title:  "Compare JDK vs JRE vs JVM"
author: gaurav
categories: [ Java, Core Java ]
featured: false
toc: true
description: "In this article, we will see the comparison between JDK, JRE and JVM."
---

In this article, we will see the comparison between JDK, JRE and JVM.

## Introduction

While talking about the Java programming language we usually hear the terminologies like  JDK, JRE and JVM.

To understand the difference between these terminologies, let's see a use case.

The Java programming language will be used by two types of users. The first ones are Developers, who develop the software in Java and the second ones are the end-users, who use this software for various purposes.

## JVM

JVM stands for Java Virtual Machine.

It is a virtual machine that executes Java bytecode. 

All JVMs can understand the bytecode and convert it to respective executable instructions. This makes Java a platform-independent language.

## JRE 

JRE stands for Java Runtime Environment.

The Java programming language will be used by two types of users. Developers and end-users. JRE can be used by end-users to run the applications. 

The end-users do not need to develop or compile the software, they can directly run it using the JRE.

JRE contains some sets of libraries and JVM.

## JDK

JDK stands for Java Development Kit.

The Java programming language will be used by two types of users. Developers and end-users. JDK can be used by developers to develop and run applications. 

The developer needs to write a Java program, he needs to compile it and debug it. Once it is written and compiled successfully, He can try running it. All this can be done with JDK i.e Java Development Kit

JDK contains the `javac` Java Compiler, debugging tools, JRE and JVM.


Let's see the following diagram to understand the JDK vs JRE vs JVM

![JDK vs JRE vs JVM](/assets/images/2023-11-08/jdk-vs-jre-vs-jvm.png)



