---
layout: post  
title: "Java Program To Find Duplicate Elements in Array."  
author: gaurav  
categories: [Java Programs, Array]  
toc: true
description: "In this tutorial, we will see a Java program to find duplicate elements in an array."
---

In this tutorial, we will see a Java program to find duplicate elements in an array.

## Introduction

We will find duplicate elements from an input array as follows:

1. Using the iterative method
2. Using the sorting method
3. Using the HashSet method
4. Using the Java 8 Streams method



## 1. Find duplicate elements in an array using the iterative method

In this method we are iterating over an input array to compare each elements with the remaining input array. 

```java
private static void printDuplicatesByIterating(int[] arr) {
        System.out.println("\nFinding duplicate elements using the iterative method.");
        Set<Integer> duplicateElements = new HashSet<>();

        for (int i=0; i<arr.length; i++) {
            for (int j=i+1; j<arr.length; j++) {
                if (arr[i] == arr[j]){
                    duplicateElements.add(arr[i]);
                }
            }
        }
        System.out.println("Duplicate elements in array are :" + duplicateElements);
    }
```



## 2. Find duplicate elements in an array using the sorting method

In this method we are sorting the first using the Arrays.sort() method.  And then, we are iterating over an array to check if the next adjacent element is duplicate or not.

```java
private static void printDuplicatesBySorting(int[] arr) {
        System.out.println("\nFinding duplicate elements using the sorting method.");

        Set<Integer> duplicateElements = new HashSet<>();
        Arrays.sort(arr);

        for (int i=0; i<arr.length-1; i++) {
            if (arr[i] == arr[i+1]){
                duplicateElements.add(arr[i]);
            }
        }
        System.out.println("Duplicate elements in array are :" + duplicateElements);
    }
```



## 3. Find duplicate elements in an array using the HashSet method

In this method, we are adding the elements of the input array one by one into HashSet using the set.add() method. 

The Set always contains the unique elements. The `set.add() `method returns `true` if the element is successfully added to the set, and `false` if the element already exist.

```java
private static void printDuplicatesByHashSet(int[] arr) {
        System.out.println("\nFinding duplicate elements using the HashSet method.");

        Set<Integer> duplicateElements = new HashSet<>();
        Set<Integer> hashSet = new HashSet<>();

        for (int i : arr) {
            if (!hashSet.add(i)) {
                duplicateElements.add(i);
            }
        }
        System.out.println("Duplicate elements in array are :" + duplicateElements);

    }
```

## 4. Find duplicate elements in an array using the Java 8 Streams method

In this method, we are using the Java 8 Streams method to find the duplicate elements from the input array.

We have created a stream of an array. The `filter()` method accepts an expression and returns a boolean result.

As we know, the Set always contains unique elements. The `set.add()` method returns true if the element is successfully added to the set, and false if the element already exists.

We are filtering out the duplicate elements using the above logic and collecting them in another set.

```java
private static void printDuplicatesByJava8Streams(int[] arr) {
        System.out.println("\nFinding duplicate elements using the Java 8 Streams method.");
        Set<Integer> hashSet = new HashSet<>();

        Set<Integer> duplicateElements = Arrays.stream(arr).filter(i -> !hashSet.add(i)).boxed().collect(Collectors.toSet());
        System.out.println("Duplicate elements in array are :" + duplicateElements);
    }
```



## Java Program to find duplicate elements in an array

**Java Program**

```java
import java.util.*;
import java.util.stream.Collectors;

/**
 * Java Program to find duplicate elements in an Array
 * By coderolls.com
 */

public class DuplicatesInArray {

    public static void main(String[] args) {
        int[] arr = {1, 5, 6, 9, 2, 6, 9, 6, 3, 2, 1};
        System.out.print("The input array is as given: ");
        System.out.println(Arrays.toString(arr));

        printDuplicatesByIterating(arr);

        printDuplicatesBySorting(arr);

        printDuplicatesByHashSet(arr);

        printDuplicatesByJava8Streams(arr);
    }


    private static void printDuplicatesByIterating(int[] arr) {
        System.out.println("\nFinding duplicate elements using the iterative method.");
        Set<Integer> duplicateElements = new HashSet<>();

        for (int i=0; i<arr.length; i++) {
            for (int j=i+1; j<arr.length; j++) {
                if (arr[i] == arr[j]){
                    duplicateElements.add(arr[i]);
                }
            }
        }
        System.out.println("Duplicate elements in array are :" + duplicateElements);
    }

    private static void printDuplicatesBySorting(int[] arr) {
        System.out.println("\nFinding duplicate elements using the sorting method.");

        Set<Integer> duplicateElements = new HashSet<>();
        Arrays.sort(arr);

        for (int i=0; i<arr.length-1; i++) {
            if (arr[i] == arr[i+1]){
                duplicateElements.add(arr[i]);
            }
        }
        System.out.println("Duplicate elements in array are :" + duplicateElements);
    }

    private static void printDuplicatesByHashSet(int[] arr) {
        System.out.println("\nFinding duplicate elements using the HashSet method.");

        Set<Integer> duplicateElements = new HashSet<>();
        Set<Integer> hashSet = new HashSet<>();

        for (int i : arr) {
            if (!hashSet.add(i)) {
                duplicateElements.add(i);
            }
        }
        System.out.println("Duplicate elements in array are :" + duplicateElements);

    }

    private static void printDuplicatesByJava8Streams(int[] arr) {
        System.out.println("\nFinding duplicate elements using the Java 8 Streams method.");
        Set<Integer> hashSet = new HashSet<>();

        Set<Integer> duplicateElements = Arrays.stream(arr).filter(i -> !hashSet.add(i)).boxed().collect(Collectors.toSet());
        System.out.println("Duplicate elements in array are :" + duplicateElements);
    }
}
```

**Output**

```
The input array is as given: [1, 5, 6, 9, 2, 6, 9, 6, 3, 2, 1]

Finding duplicate elements using the iterative method.
Duplicate elements in array are :[1, 2, 6, 9]

Finding duplicate elements using the sorting method.
Duplicate elements in array are :[1, 2, 6, 9]

Finding duplicate elements using the HashSet method.
Duplicate elements in array are :[1, 2, 6, 9]

Finding duplicate elements using the Java 8 Streams method.
Duplicate elements in array are :[1, 2, 6, 9]
```

