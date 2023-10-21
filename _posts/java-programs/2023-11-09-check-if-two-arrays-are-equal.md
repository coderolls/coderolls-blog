---
layout: post  
title: "Java Program To Check Two Arrays Are Equal"  
author: gaurav  
categories: [Java Programs, Array]  
toc: true
description: "In this tutorial, we will see a Java program to check if two arrays are equal or not."
---

In this tutorial, we will see a Java program to check if two arrays are equal or not.

We have x ways to check if the two Arrays are equal or not.

1. Iterating over an array
2. Using `Arrays.equal()` method

## 1. Iterating over an array

To check if the two array are equal or not, we can use following strategy.

If the length of the two array are not same, these arrays are not equal.

If the length is same, we can iterate over an array and check if the elements are equal at the same indices. If yes, these arrays are equal.

Let's have a look at following java program for better understanding.

**Java Program**

```java
/**
 * Java program to check if the two arrays are equal or not
 * by iterating over array
 * By coderolls.com
 */
public class ArrayEqual {

    public static void main(String[] args) {
        int[] arr = {2, 3, 5, 6};
        int[] arr2 = {2, 3, 5, 6};
        int[] arr3 = {2, 3, 1, 4};
        int[] arr4 = {2, 3, 5, 6, 7, 4};

        System.out.println("Comparing arr and arr2: ");
        checkIfArraysAreEqual(arr, arr2);

        System.out.println("\nComparing arr and arr3: ");
        checkIfArraysAreEqual(arr, arr3);

        System.out.println("\nComparing arr and arr4: ");
        checkIfArraysAreEqual(arr, arr4);
    }

    private static void checkIfArraysAreEqual(int[] arr, int[] arr2) {
        boolean isEqual = true;
        if (arr.length == arr2.length) {
          for (int i=0; i<arr.length; i++){
              if (arr[i] != arr2[i]) {
                  isEqual = false;
                  break;
              }
          }
        } else {
            isEqual = false;
        }
        // print if arrays are equal or not
        if (isEqual) {
            System.out.println("The arrays are equal");
        } else {
            System.out.println("The arrays are not equal");
        }
    }
}
```

**Output**

```
Comparing arr and arr2: 
The arrays are equal

Comparing arr and arr3: 
The arrays are not equal

Comparing arr and arr4: 
The arrays are not equal
```



## 2. Using `Arrays.equals()` method

To check if the two array are equal or not, we are using the ready made Arrays.equals() method.

**Java Program**

```java
import java.util.Arrays;

/**
 * Java program to check if the two arrays are equal or not
 * by Arrays.equals() method
 * By coderolls.com
 */
public class ArrayEquals2 {

    public static void main(String[] args) {
        int[] arr = {2, 3, 5, 6};
        int[] arr2 = {2, 3, 5, 6};

        System.out.println("Comparing arr and arr2 using Arrays.equals() method: ");
        boolean result1 = Arrays.equals(arr, arr2);

        if (result1) {
            System.out.println("The arrays are equal");
        } else {
            System.out.println("The arrays are not equal");
        }
    }
}
```

**Output**

```
Comparing arr and arr2 usig Arrays.equal() method: 
The arrays are equal
```

