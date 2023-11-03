---
layout: post  
title: "Java Program To Print The Fibonacci Series Up To A Given Number of terms"  
author: gaurav  
categories: [Java Programs, Core Java]  
toc: true
description: "In this tutorial, we will see a Java program to print the Fibonacci series up to a given number of terms."
---

In this tutorial, we will see a Java program to print the Fibonacci series up to a given number of terms.

## What is Fibonacci Series?

Fibonacci Series is the **sequence of numbers in which each number in the sequence is equal to the sum of two numbers before it**.

Fibonacci Series:

0, 1, 1, 2, 3, 5, 8, 13, 21.............

## Java Program To Print The Fibonacci Series Up To A Given Number of terms

```java
public class FibonacciSeries {
    
    public static void main(String[] args) {
        int terms = 15;
        System.out.println("Fibonacci Series:");
        printFibonacciSeries(terms);
    }

    public static void printFibonacciSeries(int num) {
        int a = 0, b = 1;
        for (int i = 0; i < num; i++) {
            System.out.print(a + " ");
            int temp = a + b;
            a = b;
            b = temp;
        }
    }
}
```

Output

```
Fibonacci Series:
0 1 1 2 3 5 8 13 21 34 55 89 144 233 377 
```

