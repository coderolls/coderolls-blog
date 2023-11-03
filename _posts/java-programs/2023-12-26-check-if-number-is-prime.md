---
layout: post  
title: "Java Program To Check If The Given Number is Prime or Not"  
author: gaurav  
categories: [Java Programs, Core Java]  
toc: true
description: "In this tutorial, we will see a Java program to check if the given number is Prime or Not."
---

In this tutorial, we will see a Java program to check if the given number is prime or not.

## What is Prime Number?

A number that can be divided exactly only by itself and 1.

For example 7, 17 and 41.

## Java Program To Check If The Given Number is Binary Or Not

```java
public class PrimeNumber {

    public static void main(String[] args) {
        int num = 41;
        boolean isPrimeNumber = isPrime(num);
        if (isPrimeNumber) {
            System.out.println(num + " is a prime number.");
        } else {
            System.out.println(num + " is not a prime number.");
        }
    }

    public static boolean isPrime(int num) {
        if (num <= 1) {
            return false;
        }
        for (int i = 2; i <= Math.sqrt(num); i++) {
            if (num % i == 0) {
                return false;
            }
        }
        return true;
    }
}
```

Output

```
41 is a prime number.
```

