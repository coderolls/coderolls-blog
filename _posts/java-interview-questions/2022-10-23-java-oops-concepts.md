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

**Example:** ATM functions are a practical example of abstraction. They just highlight the functionality i.e withdrawing a money, checking balance or printing the mini statement. It does not show the internal implementation of that functions.

**Method in a Java class** is an example of Abstraction.

### 2. Encapsulation

The **process of grouping the data members and corresponding methods in a single unit** is called encapsulation.

**Every java class is the example of encapsulation.** Java bean is the fully encapsulated class because all the data members are private here.

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

In the above code the data members like `id` , `name` and corresponding methods such as `setId()`, `getId` etc. are grouped together in a java class `Student`. So Java class is a good example of *Encapsulation*.

### 3. Inheritance

***When a child object acquires all the properties and behaviours of a parent object***, it is known as inheritance. It provides code re-usability. It is a `IS-A ` relationship.

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

In the above example `Animal` class is a Parent class and `Dog` class is `child` class.

Animal can have name, it can run.

We have created a child class `Dog` which `extends` the `Animal` class. That means `Dog` class inherits the properties and behaviours of the parent class `Animal`.

Dog can have a name, it can run and in addition it can have it's own property like `breed` and behaviours like `bark()`.

### 4. Polymorphism

If *one task is performed in different ways*, it is known as polymorphism.

The word ***poly*** means ***many*** and ***morphs*** means ***forms or ways***.

In Java, we use method overloading and method overriding to achieve polymorphism.

## Conclusion

 Abstraction, Encapsulation, Inheritance and Polymorphism are the most important oops concepts in java.

1. In Abstraction we **hide the internal implementation** and **highlight the functionalities offered**. Ex. method in java

2. Encapsulation is the **process of grouping data members and corresponding methods in a single unit**. Ex. Java Class

3. In inheritance, **a child class inherits all the properties and behaviour of parent class**. It can be done by extending the parent class. Ex. `class Dog extends Animal{...}`
4. **Doing one task in many ways** is called polymorphism. In java, polymorphism can be done using **method overloading and method overriding**.

---

Please write your thoughts in the comment section below.