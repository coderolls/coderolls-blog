---
layout: post  
title: "Difference Between Abstract Class and Interface In Java"  
author: gaurav  
categories: [Java, Java Interview Questions]  
toc: true
description: "In this tutorial, we will see difference between abstract class and interface in Java."
---

In this tutorial, we will see difference between abstract class and interface in Java.

## Introduction

Interfaces form a contract between **the class and the outside world**, and this contract is enforced at build time by the compiler.

An *abstract class* is a class that is **declared with `abstract` keyword**—it may or may not include abstract methods. Abstract classes cannot be instantiated, but they can be subclassed.

We all know that Defaults and Static methods are introduced in Java 8.

We can have business logic in the interface with default and static methods. So the measure difference that interface can not have concrete methods and abstract class have concrete methods is no more. But still there are many differences in the interface and abstract class as discussed below.

## Difference Between Interface And Abstract Class After Java 8 i.e. Interface Vs  Abstract Class After Java 8

| Property             | Interface                                                    | Abstract Class                                               |
| -------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Variables            | **Every variable present inside the interface is always public, static, and final,** whether we are declaring or not. | The variables present inside the abstract class **need not be public static and final.** We can have other types of variables too. |
| Variables            | We **can not declare protected, transient and volatile variables** in the interface. | There are **no restrictions on abstract class variable modifiers**. We can have protected, transient and volatile variables in the Abstract class. |
| Default Methods      | After Java 8, an i**nterface can have default methods.**     | **Abstract Class can not have default methods**.             |
| Final Methods        | As we know, an interface can have default and static methods along with abstract methods. But **Interfaces don’t support final methods**. | **Abstract classes support final as well as non-final methods** and static as well as non-static methods along with abstract methods. |
| Constructors         | We **can not have constructors** inside the interface.       | We **can declare a constructor inside an abstract class**, that can be used at the time of child object creation. |
| Multiple Inheritance | **A class can implement multiple interfaces**. So multiple inheritances are possible with Interfaces. | **A class can extend only one abstract class**. So multiple inheritances are not possible with abstract classes. |

## Difference Between Interface And Abstract Class Before Java 8 i.e. Interface Vs  Abstract Class Before Java 8

Here we will see difference between interface and abstract class before Java 8 version.

| Property                | Interface                                                    | Abstract Class                                               |
| ----------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| When to use?            | If we **don't know anything about implementation and we just have requirement specifications** then we should go for an interface. | If we do not have a complete idea about implementation then we should go for the Abstract class. i.e **In case of partial implementation**, we should go for Abstract Class. |
| Methods                 | Inside the interface, **all methods are public and abstract** by default. Hence we can achieve 100% abstraction with an interface. | Every method present in the abstract class need not be public and abstract. **In addition to abstract methods, we can have concrete methods too**. |
| Modifiers               | Since all the methods are public and abstract, we **can not use any other modifiers. (Other than public and abstract)** | Since we can concrete methods in the Abstract class, **there are no restrictions on abstract class method modifiers.** |
| Variables               | **Every variable present inside the interface is always public, static, and final,** whether we are declaring or not. | The variables present inside the abstract class **need not be public static and final.** We can have other types of variables too. |
| Variables               | We **can not declare protected, transient and volatile variables** in interface. | There are **no restrictions on abstract class variable modifiers**. We can have protected, transient and volatile variables in Abstract class. |
| Variable Initialisation | At the time of declaration, **we need to initialize the variables compulsorily**. Otherwise, we will get compile time error. | For Abstract class variables, **it is not necessary to initialize them at the time of declaration**. |
| Blocks                  | Inside the interface, **we can not declare instances and static blocks**. Otherwise, we will get compile time error. | Inside the abstract class, we **can declare instances and static blocks**. |
| Constructors            | We **can not have constructors** inside the interface.       | We **can declare a constructor inside an abstract class** that can be used at the time of child object creation. |
| Multiple Inheritance    | A **class can implement multiple interfaces**. So multiple inheritances are possible with Interfaces. | A **class can extend only one abstract class**. So multiple inheritances are not possible with abstract classes. |
| Example                 | Servlet                                                      | GenericServlet , HttpServlet                                 |

---

Please write your thoughts in the comment section below.
