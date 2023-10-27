---
layout: post  
title: "Java Program To Print An Array."  
author: gaurav  
categories: [Java Programs, Array]  
toc: true
description: "In this tutorial, we will see how to print an array In Java."
---

In this tutorial, we will see how to print an array In Java.

We can print an array using the following 3 ways

1. Print an array using for loop
2. Print an array using `Arrays.toString()`
3. Print a multi-dimensional array using ` Arrays.deepToString()`
4. Print an array using Java 8 Streams 

## 1. Print an array using for loop

Here, we are iterating over an array and printing each element.

**Java Program**

```java
/**
 * Java program to print an array using for loop
 * By coderolls.com
 */
public class PrintArray {

  public static void main(String[] args) {
    int[] arr = {1, 5, 6, 9, 2, 6, 9, 6, 3, 2, 1};
    
    System.out.println("Elements of the array are given below: ");
    for (int i: arr) {
      System.out.println(i);
    }
  }
}
```

**Output**

```
Elements of the array are as give below: 
1
5
6
9
2
6
9
6
3
2
1
```

## 2. Print an array using `Arrays.toString()`

We have a ready-made method to print an array in Java.

`Arrays.toString()` method expects an array to be printed as an input parameter and returns a string of array elements.

Input param - array to be  print

Returns - array string

**Java Program**

```java
/**
 * Java program to print an array using Arrays.toString()
 * By coderolls.com
 */
public class PrintArray2 {

  public static void main(String[] args) {
    int[] arr = {1, 5, 6, 9, 2, 6, 9, 6, 3, 2, 1};
    
    System.out.println("Elements of the array are given below: ");
    String srrString = Arrays.toString(arr);
    System.out.println(srrString);
  }
}
```

**Output**

```
Elements of the array are given below: 
[1, 5, 6, 9, 2, 6, 9, 6, 3, 2, 1]
```



## 3. Print a multi-dimensional array using `Arrays.deepToString()`

To print a multi-dimensional array we can use the ready-made `Arrays.deepToString()` method.

**Java Program**

{% raw %}

```java
import java.util.Arrays;

/**
 * Java program to print a multi-dimensional array using Arrays.deepToString()
 * By coderolls.com
 */
public class PrintArray3 {

  public static void main(String[] args) {
    int[][] arr = {{1, 5, 8, 7}, {2, 6, 9, 6,}};
    
    System.out.println("Elements of the multi-dimensional array are given below: ");
    String srrString = Arrays.deepToString(arr);
    System.out.println(srrString);
  }
}
```
{% endraw %}

**Output**

```
Elements of the multi-dimensional array are given below: 
[[1, 5, 8, 7], [2, 6, 9, 6]]
```

## 4. Print an array using Java 8 Streams 

In Java 8 Streams, we can use the `foreach()` method to print each element of an array.

**Java Program**

```java
import java.util.Arrays;

/**
 * Java program to print an array using Java 8 Streams foreach method
 * By coderolls.com
 */
public class PrintArray4 {

  public static void main(String[] args) {
    int[] arr = {1, 5, 8, 7, 2, 6, 9, 6};
    
    System.out.println("Elements of the array are as given below: ");
    Arrays.stream(arr).forEach(System.out::println);
  }
}
```

**Output**

```
Elements of the array are as given below: 
1
5
8
7
2
6
9
6
```

