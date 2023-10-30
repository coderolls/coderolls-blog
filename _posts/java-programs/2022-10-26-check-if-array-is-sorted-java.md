---
layout: post  
title: "Check If An Array Is Sorted In Java"  
author: gaurav  
categories: [Java Programs, Array]  
toc: true
description: "In this tutorial, we will see a Java program to check if an array is sorted in Java."
---

In this tutorial, we will see a Java program to check if an array is sorted in Java.

## Introduction

We will write a Java program to check if the array is sorted or not.

We will take a sample integer array `arr = {1, 3 , 5, 9};` We will return `true` if the array is sorted or `false` if the array is not sorted.

## Check if an array is sorted or not in Java

```java
/**
 * A Java program to check if the array of integers is sorted
 * or not using for loop iteration.
 * 
 * @author coderolls.com
 *
 */
public class SortedArrayTester {

  public static void main(String[] args) {
    int[] arr = {2, 5, 9, 8, 11, 18, 13};
    
    boolean isSorted = isArraySorted(arr);
    
    //Use this to check the sorted case
    
    /*
    * int[] arr2 = {2, 5, 9, 11, 18};
    * boolean isSorted = isArraySorted(arr2);
    */
    if(isSorted) {
      System.out.println("The array is sorted.");
    }
    else {
      System.out.println("The array is not sorted.");
    }
  }
  
  private static boolean isArraySorted(int[] arr) {
    int n = arr.length;
    
    for(int i=0; i<n-1; i++) {
      //in a sorted array current number should be 
      //always less than the next number in the array
      if(arr[i]>arr[i+1]) {
        return false;
      }
    }
    return true;
  }
}
```

Output:

```
The array is not sorted.
```

### Explanation:

1. In the `main` method we are taking a sample array `arr` and passing it to the `isArraySorted()` method to check if the array is sorted or not. This method returns a `boolean` value. `true` - if an array is sorted, `false` - if an array is not sorted
2. In the `isArraySorted()` method, we are iterating over an array from index `0` to `n-1`, (`n`-length of the array) and we will check if the current number (number at index `i`) is greater than the next number ( number at index `i+1`).
3. If the current number (number at index `i`) is greater than the next number ( number at index `i+1`), that means the array is not sorted, and we will return `false`.
4. If the control came out of the for loop, that means the array is sorted and we will return `true`.
5. When we receive the `boolean` result `isSorted` we will print the output.

## Conclusion

 we can check if the primitive arrays are sorted or not by comparing the adjacent array elements.

---

The example Java programs used in the above article can be found at this GitHub repository, [blogpost-coding-examples/java-programs/second-largest-element-in-an-array/](https://github.com/coderolls/blogpost-coding-examples/tree/main/java-programs/second-largest-element-in-an-array).  

Please write your thoughts in the comment section below.
