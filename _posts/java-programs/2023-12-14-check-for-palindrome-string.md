---
layout: post  
title: "Java Program To Check If the given String Is Palindrome or Not"  
author: gaurav  
categories: [Java Programs, Core Java]  
toc: true
description: "In this tutorial, we will see a Java program to check if the given String is palindrome or not."
---

In this tutorial, we will see a Java program to check if the given String is palindrome or not.

## Java Program To Check If the given String Is Palindrome or Not

```java
/**
 * A Java program to check if the given string is palindrome or not.
 * @author coderolls.com
 */
public class PalindromeString {

    public static void main(String[] args) {
        String str1 = "racecar";
        checkIfPalindrome(str1);
    }

    private static void checkIfPalindrome(String str) {
        String reversedString = "";
        int len = str.length();
        for (int i = (len - 1); i >= 0; --i) {
            reversedString = reversedString + str.charAt(i);
        }
        if (str.equalsIgnoreCase(reversedString)) {
            System.out.println("The String '" + str + "' is a Palindrome String.");
        } else {
            System.out.println("The String '" + str + "' is not a Palindrome String.");
        }
    }
}
```

Output

```
The String 'racecar' is a Palindrome String.
```
