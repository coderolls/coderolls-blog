---
layout: post  
title: "Java Program To Check If The Given Number is Binary Or Not"  
author: gaurav  
categories: [Java Programs, Core Java]  
toc: true
description: "In this tutorial, we will see a Java program to check if the given number is binary or not."
---

In this tutorial, we will see a Java program to check if the given number is binary or not.

We can check if the given number is binary or not by the following ways

1. Checking if the number contains a `1` or `0` digits by the reminder and divide method
2. Convert the number to String

## 1. Java program to check if the given number is binary or not by checking if the number contains `1` or `0` digit by the reminder and divide method

In the below program, we are getting each digit of the given input number one by one using the reminder method.

If the digit is any other than the `0` and `1`,  i.e. number is not Binary and it returns `false`. Otherwise, it will return `true`.

**Java Program**

```java
public class BinaryChecker {

    public static void main(String[] args) {
        long input = 101110001; // Change this to the number you want to check.
        boolean isBinary = isBinaryNumber(input);

        if (isBinary) {
            System.out.println(input + " is a binary number.");
        } else {
            System.out.println(input + " is not a binary number.");
        }
    }

    public static boolean isBinaryNumber(long num) {
        while (num > 0) {
            long digit = num % 10;
            if (digit != 0 && digit != 1) {
                return false; // The number contains a non-binary digit.
            }
            num /= 10;
        }
        return true; // All digits are 0 or 1, so it's a binary number.
    }
}
```

**Output**

```
101110001 is a binary number.
```

## 2.  Java program to check if the given number is binary or not by converting the number to a String

In the below program, we have used the regex expression to check if the number has only `0` or `1` digits.

We can do it as follows

1. We are converting the given input number to a string

2. Using the regex pattern matcher to check whether the number string i.e. `inputStr` contains only `0` or `1` digits.
3. If we find any `0` or `1` in the number, the number is binary and it returns `true`, Otherwise it returns `false`

**Java Program**

```java
import java.util.regex.Pattern;
import java.util.regex.Matcher;

public class BinaryChecker2 {

    public static void main(String[] args) {
        long input = 10110101;
        String inputStr = String.valueOf(input);
        boolean isBinary = isBinary(inputStr);

        if (isBinary) {
            System.out.println(inputStr + " is a binary number.");
        } else {
            System.out.println(inputStr + " is not a binary number.");
        }
    }

    public static boolean isBinary(String num) {
        // Define a regular expression pattern to match binary numbers (0 or 1).
        String binaryPattern = "^[01]+$";

        // Create a Pattern object.
        Pattern pattern = Pattern.compile(binaryPattern);

        // Use a Matcher to match the input string with the pattern.
        Matcher matcher = pattern.matcher(num);

        // Return true if the input string is a binary number; otherwise, return false.
        return matcher.matches();
    }
}
```

**Output**

```
10110101 is a binary number.
```
