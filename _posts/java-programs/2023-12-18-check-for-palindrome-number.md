---
layout: post  
title: "Java Program To Check If the given Number Is Palindrome or Not"  
author: gaurav  
categories: [Java Programs, Core Java]  
toc: true
description: "In this tutorial, we will see a Java program to check if the given Number is palindrome or not."
---

In this tutorial, we will see a Java program to check if the given Number is palindrome or not.

## Java Program To Check If the given Number Is Palindrome or Not

```java
/**
 * A Java program to check if the given number is a palindrome or not.
 * @author coderolls.com
 */
public class PalindromeNumber {

    public static void main(String[] args) {
        int num = 125521;
        checkIfPalindrome(num);
    }

    private static void checkIfPalindrome(int num) {
        int numCopy = num;
        int reversedNumber = 0;
        int reminder;

        while(numCopy != 0){
            reminder = numCopy % 10;
            reversedNumber = reversedNumber *10 + reminder;
            numCopy /=10;
        }
        if (reversedNumber == num) {
            System.out.println("The Number '" + num + "' is a Palindrome Number.");
        } else {
            System.out.println("The Number '" + num + "' is not a Palindrome Number.");
        }
    }
}
```

Output

```
The Number '125521' is a Palindrome Number.
```
