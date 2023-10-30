---
layout: post  
title: "Java Program To Find Largest Element In An Array (3 Ways)"  
author: gaurav  
categories: [Java Programs, Array]  
toc: true
description: "In this tutorial, we will see a Java program to find the largest element in an array."
---

In this tutorial, we will see how to find the largest element in an array.

## Introduction

We will take an array of integers `arr` and write a program to find the largest number from `arr`. Please note that `arr` is not a sorted array.  ex. `{2, 5, 9, 8, 11}`

## Java Program to find the largest element in an array

### 1. Using for loop iteration

In this way, we are iterating over an array using a for loop to find the largest number.

```java
/**
 * A Java program to find the largest number in an array 
 * using for loop iteration.
 * 
 * @author coderolls.com
 *
 */
public class LargestElementInArray {
  
  public static void main(String[] args) {
    int[] arr = {2, 5, 9, 8, 11};
    
    int largestElement = getLargest(arr);
    System.out.println("The largest element in an array 'arr' is: "+ largestElement);
  }
  
  private static int getLargest(int[] arr) {
    int n = arr.length;
    int largest = arr[0];
    
    for(int i=0; i<n; i++) {
      //If the number at  index i is bigger than the current largest number,
      // copy it to 'largest' int variable
      if(arr[i]>arr[0]) {
        largest = arr[i];
      }
    }
    return largest;
  }
}
```

Output:

```
The largest element in an array 'arr' is: 11
```

#### Explanation:

1. In the main method, we have taken a sample array `arr = {2, 5, 9, 8, 11};` and passed it as a parameter to the `getLargest()` method to return the largest number in an array `arr`.
2. In the `getLargest()` method we have stored the length of an array `aar` into int variable n using the `arr.length` method and also we have assigned the number at index `0` as the current largest number. So we have stored `arr[0]` to int variable `largest`. 
3. In a for loop, we are iterating over the array arr and checking if there is a larger number at index `i` than the current largest number. ( We had assigned `arr[0]` as the current most significant number to start with in step 2.) 
4. If the number at index `i` is larger than the current largest number i.e. `largest`, we will copy it to largest and continue iterating. OR if the number at index i is smaller or equal to the current largest number i.e `largest` we will ignore and continue iterating.
5. At the last, we will return the largest, which has the largest number in an array.

### 2. Using `Arrays.sort()`

As the array is not sorted, we can sort it using the `Arrays.sort()` method. So the last element of an array will be the largest element of an array.

```java
import java.util.Arrays;

/**
 * A Java program to find the largest number in an array 
 * using Arrays.sort().
 * 
 * Arrays.sort() sort the array in natural sorting order
 * 
 * @author coderolls.com
 *
 */
public class LargestElementInArrayUsingArrays {

  public static void main(String[] args) {
    int[] arr = {2, 5, 9, 8, 11};
    
    int largestElement = getLargest(arr);
    System.out.println("The largest element in an array 'arr' "
    + "using Array.sort() is: "+ largestElement);
  }
  
  private static int getLargest(int[] arr) {
    Arrays.sort(arr);
    return arr[arr.length-1];
  }
}
```

Output:

```
The largest element in an array 'arr' using Array.sort() is:11
```

#### Explanation:

1. In the main method, we have taken a sample array `arr = {2, 5, 9, 8, 11};` and passed it as a parameter to the `getLargest()` method to return the largest number in an array `arr`.
2. In the `getLargest()` method, we have sorted an array `arr` in natural sorting order using the `Arrays.sort()` method.
3. Once we sort the array in natural sorting order, we will have the largest number at the end of the array. We can get the last number of an array as `arr[arr.length-1]` to return it.

### 3. Using Java 8 Streams API

Java 8 Streams API provides various methods to perform data processing operations on data sources. We can create a stream of an array and the `max()`  method will return the maximum element of this stream.

```java
import java.util.Arrays;
/**
 * A Java program to find the largest number in an array 
 * using Java 8 Streams API.
 * 
 * max() returns the maximum element of this stream
 * 
 * @author coderolls.com
 *
 */
public class LargestElementInArrayUsingStream {

  public static void main(String[] args) {
    int[] arr = {2, 5, 9, 8, 11};
    
    int largestElement = getLargest(arr);
    System.out.println("The largest element in an array 'arr'"
    + "using Java 8 Streams API is: "+ largestElement);
  }
  
  private static int getLargest(int[] arr) {
    int largest = Arrays.stream(arr).max().getAsInt();
    return largest;
  }
}
```

Output:

```
The largest element in an array 'arr' using Java 8 Streams API is: 11
```

#### Explanation:

1. In the main method, we have taken a sample array `arr = {2, 5, 9, 8, 11};` and passed it as a parameter to the `getLargest()` method to return the largest number in an array `arr`.
2. In the `getLargest()` method, we have created a Stream of array `arr`. The `max()` returns the maximum element of this stream. We are using the `getAsInt()` method to get the result as `int` and store it in the int variable `largest`.
3. Return the `largest`.

## Conclusion:

We have seen a few Java programs to find the largest element in an array.

1. We can find the largest element in an array by iterating over an array and comparing each element.
2. The second way to find the largest element in an array is by sorting an array in a natural sorting order and returning the last element.
3. The third way to find the largest element in an array is by using the Java 8 Streams API's max method.

---

The example Java programs used in the above article can be found at this GitHub repository, [blogpost-coding-examples/java-programs/largest-element-in-an-array/](https://github.com/coderolls/blogpost-coding-examples/tree/main/java-programs/largest-element-in-an-array).  

Please write your thoughts in the comment section below.
