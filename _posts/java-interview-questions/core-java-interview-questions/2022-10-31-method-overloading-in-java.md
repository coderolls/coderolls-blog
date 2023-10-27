---
layout: post  
title: "Method Overloading In Java"  
author: gaurav
categories: [Java, Java Interview Questions]
toc: true
description: "In this tutorial, we will see the method overloading in Java."
---

In this tutorial, we will see the method overloading in Java.

## Introduction

It is known as **Method Overloading** when a class has the same name but a different method signature.

For example, when we have a method `add()`,  we can have it in multiple forms.

For example `add(int a, int b)` or `add(int a, int b, int c)` or `add(double a, double b)`

---

> **What Is Method Signature In Java?**
>
> In Java, the method signature contains the method name and type of arguments.
>
> method-name(argument-type-1, argument-type-2...)
>
> Ex. `getData(int, String)`
>
> **Note:** In Java, the method signature does not include the name of the parameter, it only includes its datatype.

---

Compile-time polymorphism can be achieved by Method overloading.

In Java, there are two ways to overload the method.

1. By changing the number of arguments
2. By changing the data type of arguments

## 1. By changing the number of arguments

We can overload a method **by changing the number of arguments i.e parameters it receives**.

As shown in the example from the introduction, we can overload the method `add(int a, int b)`  by making the parameters three. i.e `add(int a, int b, int c)`

```java
public class Operation{
    
  public static int add(int a, int b){
    return a+b;
  }
  
  public static int add(int a, int b, int c){
    return a+b+c;
  }
    
}
```

## 2. By changing the data type of arguments

We can overload a method **by changing the data type of the arguments i.e parameters it receives**.

As shown in the example from the introduction, we can overload the method `add(int a, int b)`  by changing the data type of the parameters. i.e `add(double a, double b)`

```java
public class Operation{
    
  public static int add(int a, int b){
    return a+b;
  }
  
  public static double add(double a, double b){
    return a+b;
  }
    
}
```

Method overloading improves the readability of the code.

## Conclusion

It is known as **Method Overloading** when a class has the same name but a different method signature.

We can overload the method by changing the number of arguments or changing the data type of arguments.

---

Please write your thoughts in the comment section below.
