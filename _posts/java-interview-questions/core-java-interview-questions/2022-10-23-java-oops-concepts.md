---
layout: post  
title: "Java OOPs Concepts"  
author: gaurav  
categories: [Java, Java Interview Questions]   
toc: true
description: "In this tutorial, we will see the basic object-oriented programming concepts."
---

In this tutorial, we will see the basic object-oriented programming concepts.

## Introduction

Object-oriented programming (OOP) is *a computer programming model that organizes software design around data, or objects, rather than functions and logic*.

There are many opps concepts but here we will see the most important 4. I.e Abstraction, Encapsulation, Inheritance and Polymorphism.

## Java OOPs Concepts

### 1. Abstraction

**Hiding internal implementation** and just **hightailing the functionalities offered** is known as abstraction.

**Example:** ATM functions are a practical example of abstraction. They just highlight the functionality i.e. withdrawing money, checking balance or printing the mini statement. It does not show the internal implementation of those functions.

**Method in a Java class** is an example of Abstraction.

### 2. Encapsulation

The **process of grouping the data members and corresponding methods in a single unit** is called encapsulation.

**Every Java class is an example of encapsulation.** Java bean is the fully encapsulated class because all the data members are private here.

**Example:**

```java
public class Student {
	
  private int id;
  
  private String name;
  
  public int getId() {
    return id;
  }
  
  public void setId(int id) {
    this.id = id;
  }
  
  public String getName() {
    return name;
  }
  
  public void setName(String name) {
    this.name = name;
  }

}
```

In the above code, the data members like `id`, `name` and corresponding methods such as `setId()`, `getId` etc. are grouped together in a java class `Student`. So Java class is a good example of *Encapsulation*.

### 3. Inheritance

***When a child object acquires all the properties and behaviours of a parent object***, it is known as inheritance. It provides code re-usability. It is an `IS-A ` relationship.

```java
public class Animal {
	
  private String name;
  
  public void run() {
  
  }
  
  public void feed() {
  
  }

}

class Dog extends Animal{
	
  private String breed;
  
  public void bark() {
  
  }
}
```

In the above example, the `Animal` class is a Parent class and the `Dog` class is a `child` class.

The animal can have a name, it can run.

We have created a child class `Dog` which `extends` the `Animal` class. That means the `Dog` class inherits the properties and behaviours of the parent class `Animal`.

A dog can have a name, it can run and in addition, it can have its own property like `breed` and behaviours like `bark()`.

### 4. Polymorphism

If *one task is performed in different ways*, it is known as polymorphism.

The word ***poly*** means ***many*** and ***morphs*** means ***forms or ways***.

In Java, we use [method overloading](/method-overloading-in-java/) and [method overriding](/method-overriding-in-java/) to achieve polymorphism.

There are two types of polymorphism in Java: 

1. Compile-time Polymorphism
2. Runtime Polymorphism.

Compile-time polymorphism can be achieved by [**overloading the static method**](/method-overloading-in-java/). While Runtime Polymorphism can be achieved by [**overriding the parent class method in the child class**](/method-overriding-in-java/).

## Conclusion

 Abstraction, Encapsulation, Inheritance and Polymorphism are the most important oops concepts in Java.

1. In Abstraction we **hide the internal implementation** and **highlight the functionalities offered**. Ex. method in Java

2. Encapsulation is the **process of grouping data members and corresponding methods in a single unit**. Ex. Java Class

3. In inheritance, **a child class inherits all the properties and behaviour of the parent class**. It can be done by extending the parent class. Ex. `class Dog extends Animal{...}`
4. **Doing one task in many ways** is called polymorphism. In Java, polymorphism can be done using [method overloading](/method-overloading-in-java/) and [method overriding](/method-overriding-in-java/).

---

Please write your thoughts in the comment section below.
