---
layout: post  
title: "Java Program To Find Second Largest Element In An Array"  
author: gaurav  
categories: [Java Programs, Array]  
toc: true
description: "In This tutorial, we will see a Java program to find the second largest element in an array."
---

In This tutorial, we will see a Java program to find the second largest element in an array.

## Introduction

In the previous article, [Java Program To Find Largest Element In An Array (3 Ways)](/largest-element-in-an-array/), we have seen a few programs to find the largest element in an array. Today, we will see a program to find the second largest element in an array.

Here we will take an array of integers `arr`  and please note that `arr` is not a sorted array.  ex. `{2, 5, 9, 8, 11, 18, 13}`

## Java Program to find second largest element in an array

### 1. Iterating over an array

We will iterate over an array using the `for` loop to find the second largest element in an array.

```java
/**
 * A Java program to find the second largest number in an array 
 * by iterating over an array using for loop.
 * 
 * @author coderolls.com
 */
public class SecondLargestElementInArray {

	public static void main(String[] args) {
		int[] arr = {2, 5, 9, 8, 11, 18, 13};
		
		int secondLargest = getSecondLargest(arr);
		System.out.println("The second largest element in "
				+ "an array 'arr'is :"+ secondLargest);
	}

	private static int getSecondLargest(int[] arr) {
		int n =arr.length;
		int largest =arr[0];
		int secondLargest = -1;
		
		for(int i=0; i<n; i++) {
			if(arr[i]>largest) {
				//if you found the new largest,
				//copy current largest to second largest and
				//copy current element arr[i] to largest
				secondLargest = largest;
				largest = arr[i];
			}else if(arr[i]!=largest) {
				// if the current element arr[i] is not the largest and 
				// still larger than the current secondLargest
				// then copy it to secondLargest
				if(arr[i]>secondLargest) {
					secondLargest = arr[i];
				}
			}
		}
		return secondLargest;
	}
}
```

Output:

```
The second largest element in an array 'arr' is :13
```

#### Explanation:

1. In the main method, we have taken a sample array `arr = {2, 5, 9, 8, 11, 18, 13};` and passed it as a parameter to `getSecondLargest()` method to return the largest number in an array `arr`.

2. In `getSecondLargest()` method we have stored the length of an array `arr` into int variable n using the `arr.length` method. To start the program we have assigned the number at index `0` i.e. `arr[0]` as the current largest number i.e `largest`. Also, we have assigned the value `-1` the current second largest number `secondLargest`.

   > If the array contains all the similar numbers, there will be no second largest number in an array. ex. `arr= {12,12,12,12}` So it will return -1 in that case.

3. Using the `if` statement we are checking if the current number at index `i`  i.e. `arr[i]` is larger than  the current largest number i.e `largest`, we will

   1. assign the current largest number `largest` to `secondLargest`
   2. store current number i.e. `arr[i]` as `largest`

4. Next, we will check if the current number `arr[i]` is not the current largest number `largest` but is still larger than the current second largest number, we will store it to the `secondLargest`.

5. Return `secondLargest`.

### 2. Using `Arrays.sort()`

As we know the array is not sorted, we can sort it using the `Arrays.sort()` method in natural sorting order. So the second last element of an array will be the second largest element of an array.

```java
import java.util.Arrays;

/**
 * A Java program to find the second largest number in an array 
 * using Arrays.sort() method.
 * 
 * @author coderolls.com
 */
public class SecondLargestElementInArrayUsingArrays {

	public static void main(String[] args) {
		int[] arr = {2, 5, 9, 8, 11, 18, 13};
		
		int secondLargest = getSecondLargest(arr);
		System.out.println("The second largest element in"
				+ "an array 'arr' is using Arrays.sort() :"+ secondLargest);
	}

	private static int getSecondLargest(int[] arr) {
		Arrays.sort(arr);
		// return second largest, so length-2
		return arr[arr.length-2];
	}
}
```

Output:

```
The second largest element in an array 'arr' is using Arrays.sort() :13
```

#### Explanation:

1. In the main method, we have taken a sample array `arr = {2, 5, 9, 8, 11, 18, 13};` and passed it as a parameter to `getSecondLargest()` method to return the largest number in an array `arr`.
2. In `getSecondLargest()` method, we have sorted an array `arr` in natural sorting order using the `Arrays.sort()` method.
3. Once we sort the array in natural sorting order, we will have the second largest number as the second last element of the array. We can get the second last number of an array as `arr[arr.length-2]` to return it.

> In this way ( 2. Using `Arrays.sort()`) even if all the numbers of an array are similar ex. `arr= {12,12,12,12}`, i.e. when there is no second largest element, it will return that same number.

## Conclusion

We can find the second largest element in an array in the following two ways,

1. By iterating over an array using for loop to compare the largest and second largest number.
2. By sorting an array in a natural sorting order and returning the second last element. i.e.  `arr[arr.length-2]`

---

The example java programs used in the above article can be found at this GitHub repository, [blogpost-coding-examples/java-programs/second-largest-element-in-an-array/](https://github.com/coderolls/blogpost-coding-examples/tree/main/java-programs/second-largest-element-in-an-array).  

Please write your thoughts in the comment section below.

