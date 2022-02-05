---
layout: post
title: "How To Convert LinkedList To Array In Java?"
author: gaurav
categories: [Collections, LinkedList]
toc: true

description: "In this short tutorial, we will see how to convert linkedlist to an array."
---

In this tutorial, we will see how to convert linkedlist to an array.

## Introduction

LinkedList class is present in the java.util package.

[LinkedList](https:/coderolls.com/linkedlist-in-java/) internally uses doubly linkedlist for storing the variables. That's why LinkedList is preferred when our frequeent operatioon is insertion and deletion.

Sometimes, we need t convert linkedList to an array. 

The LinkedList class has a `toArray()` method. We can convert linkedlist to an array using the `toArray()` method.

**There are two versions of the `toArray()` method**

1. `public Object[] toArray()` method
2. `public <T> T[] toArray(T[] a)` method

Lets see both methods one by one.

## 1. Convert LinkedList To Array Using `public Object[] toArray()` Method

We can use the `toArray()` method to convert linkedlist to an array.

The method signature for the `toArray()` method is given below.

```java
public Object[] toArray()
```

**As we can see the method signature, this method return an `Object[]` containing all of the elements in this list in proper sequence**

When `toArray()` method returns an array, the list does maintain any refereences to the returned array. And thus elements of the array are free to modify.

This method acts as bridge between array-based and collection-based APIs.

I have given a java program to convert LinkedList to array using the `toArray()` method.

```java
import java.util.LinkedList;

/**
 * A java program to convert linkedlist to an array
 * using the toArray() method.
 * 
 * @author coderolls.com
 *
 */
public class LinkedListToArray {

	public static void main(String[] args) {

		LinkedList<String> linkedList = new LinkedList<String>();
		linkedList.add("Walmart");
		linkedList.add("Amazon");
		linkedList.add("Apple");
		linkedList.add("Microsoft");
		linkedList.add("Google");
		linkedList.add("Uber");
		linkedList.add("Tesla");
		
		System.out.println("Printing the linkedList: ");
		System.out.println(linkedList);
		
		// convert linkedList to Object[]
		Object[] arr = linkedList.toArray();
		
		System.out.println("\nPrinting the object array elements: ");
		for(Object obj:arr) {
			System.out.println(obj.toString());
		}
	}
}
```

Output:

```
Printing the linkedList: 
[Walmart, Amazon, Apple, Microsoft, Google, Uber, Tesla]

Printing the object array elements: 
Walmart
Amazon
Apple
Microsoft
Google
Uber
Tesla
```



## 2.Convert LinkedList To Array Using `public <T> T[] toArray(T[] a)` Method

Ifyou want your toArray() method to return a specific type of array, then you can use the `toArray(T[] a)` method.

The method signature for this method is as given below.

```java
public <T> T[] toArray(T[] a)
```

This method accepts a type T of array as an input paramter. And it returns an array of type T containing all of the elements in this list in proper sequence (from first to last element).

If list fits in the specified array, then it return the same. Otherwise, a new array is allocated with the runtime type of the specified array and the size of this list.

If the size of the array is greater than the total size ofthe list and `null` will be added after the last element of the list to the array.

Please note that `toArray(new Object[0])` is identical in function to `toArray()`.

I have given a simple java program to convert LinkedList to array using the `public <T> T[] toArray(T[] a)` method.

```java
import java.util.LinkedList;

/**
 * A java program to convert linkedlist to an array
 * using the toArray(T[] a) method.
 * 
 * @author coderolls.com
 *
 */
public class LinkedListToArray2 {

	public static void main(String[] args) {

		LinkedList<String> linkedList = new LinkedList<String>();
		linkedList.add("Walmart");
		linkedList.add("Amazon");
		linkedList.add("Apple");
		linkedList.add("Microsoft");
		linkedList.add("Google");
		linkedList.add("Uber");
		linkedList.add("Tesla");
		
		System.out.println("Printing the linkedList: ");
		System.out.println(linkedList);
		
		// convert linkedList to String array
		String[] arr = linkedList.toArray(new String[linkedList.size()]);
		
		System.out.println("\nPrinting the String array elements: ");
		for(String str:arr) {
			System.out.println(str);
		}
	}
}
```

Output:

```
Printing the linkedList: 
[Walmart, Amazon, Apple, Microsoft, Google, Uber, Tesla]

Printing the String array elements: 
Walmart
Amazon
Apple
Microsoft
Google
Uber
Tesla
```



## Conclusion

We can use the LinkedList `toArray()` method to convert LinkedList to an array.

There are two overloaded versions of this method

1. `public Object[] toArray()` method - Returns an Object array

```java
// convert linkedList to Object[]
Object[] arr = linkedList.toArray();
```

2. `public <T> T[] toArray(T[] a)` method - Retuns a specific type of array

```java
// convert linkedList to String array
String[] arr = linkedList.toArray(new String[linkedList.size()]);
```

---

The example java programs given in the above tutorial can be found at [this GitHub Repository](https://github.com/coderolls/blogpost-coding-examples/tree/main/collections/linkedlist/convert-linkedlist-to-array).

Let me know you thoughts or suggestions on the topic discussed above in comment section below.