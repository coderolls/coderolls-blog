---
layout: post  
title: "Java Program To Calculate Sum Of All Digits Of A Number"  
author: gaurav  
categories: [Java Programs, Core Java]  
toc: false
description: "In this tutorial, we will see a Java program to get the sum of all digits of a number in Java."
---

To calculate the sum of all digits of a number

1. First, we will get a reminder of the input number by the modulo operator (%) and add it to the `sum` variable.
2. Second, we will divide the input number by 10 and assign it again to an input number variable.
3. We will repeat the above process until the input number is not equal to zero.
4. At the end we will have the sum of all the digits of a number in the `sum` variable.

Let's a Java program to calculate the sum of all digits of a number.

**Java Program**

```java
/**
 * A Java program to calculate the sum of all digits of a given number
 * By coderolls.com
 */
public class SumOfAllDigits {

    public static void main(String[] args) {
        int number = 1256;
        int sum = sumOfAllDigits(number);
        System.out.println("The sum of all digits of " + number + " is: "+ sum);
    }

    private static int sumOfAllDigits(int number) {
        int sum =0;
        while(number!=0){
            int reminder = number%10;
            sum = sum + reminder;
            number = number/10;
        }
        return sum;
    }
}
```

**Output**

```
The sum of all digits of 1256 is: 14
```

