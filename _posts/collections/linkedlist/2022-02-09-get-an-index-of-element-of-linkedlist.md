---
layout: post
title: "How To Get An Index of the Element Of LinkedList?"
author: gaurav
categories: [Collections, LinkedList]
toc: true

description: "In this tutorial, we will see how to get an index of the element of the LinkedList. LinkedList class provides various methods to get an index of the element of the LinkedList. Let's see this method with example."
---

In this tutorial, we will see how to get an index of the element from the LinkedList. LinkedList class provides various methods to get an index of the element of the LinkedList. Let's see this method with example.

## Introduction

LinkedList class is present in the `java.util` package.

[LinkedList](https:/coderolls.com/linkedlist-in-java/) internally uses a doubly linkedlist for storing the variables. That's why LinkedList is preferred when our frequent operation is insertion and deletion.

LinkedList class provides following method to an element from the list.

1. `indexOf(Object o)`
2. `lastIndexOf(Object o)`

## 1. `indexOf(Object o)`

The `indexOf(Object o)` method returns the index of the first occurrence of the specified element in this list, or -1 if this list does not contain the element.

The method signature is asgiven below.

```java
public int indexOf(Object o)
```

This method uses `equals()` method to check the equality of the element from linkedList and specifed element as a parameter.

I have given a java program to get an index of the element of the LinkedList below.

```java
import java.util.LinkedList;

/**
 * A Java program to get the first index of the element from
 * the linkedlist using indexOf(Object o) method.
 * 
 * @author coderolls.com
 */
public class LinkedListIndexOf {

	public static void main(String[] args) {
		
		LinkedList<String> linkedList = new LinkedList<String>();
		linkedList.add("PepsiCo");
		linkedList.add("DrPepper");
		linkedList.add("GoldSpot");
		linkedList.add("GoldSpot");
		linkedList.add("CocaCola");
		linkedList.add("Moxie");
		linkedList.add("GoldSpot");
		linkedList.add("Moxie");
		
		System.out.println("LinkedList: ");
		System.out.println(linkedList);
		
		// get first index of GoldSpot
		int index = linkedList.indexOf("DrPepper"); // 1
		
		System.out.println("\nIndex of the DrPepper in linkedList is: "+ index);
		
		// get first index of GoldSpot
		int indexGS = linkedList.indexOf("GoldSpot"); // 2
		
		System.out.println("\nIndex of the GoldSpot in linkedList is: "+ indexGS);
		
		// get first index of Moxie
		int indexMoxie = linkedList.indexOf("Moxie"); // 5
		
		System.out.println("\nIndex of the Moxie in linkedList is: "+ indexMoxie);
	}
}
```

Output:

```
LinkedList: 
[PepsiCo, DrPepper, GoldSpot, GoldSpot, CocaCola, Moxie, GoldSpot, Moxie]

Index of the DrPepper in linkedList is: 1

Index of the GoldSpot in linkedList is: 2

Index of the Moxie in linkedList is: 5
```

## 2. `lastIndexOf(Object o)`

The `lastIndexOf(Object o)` method returns the index of the last occurrence of the specified element in this list, or -1 if this list does not contain the element.

The method signature for the `lastIndexOf(Object o)` method is given below.

```java
public int lastIndexOf(Object o)
```

This method uses `equals()` method to check the equality of the element from linkedList and specifed element as a parameter.

I have given a java program to get the last index of the element of the LinkedList below.

```java
import java.util.LinkedList;

/**
 * A Java program to get the last index of the element from
 * the linkedlist using lastIndexOf(Object o) method.
 * 
 * @author coderolls.com
 */
public class LinkedListLastIndexOf {

	public static void main(String[] args) {
		
		LinkedList<String> linkedList = new LinkedList<String>();
		linkedList.add("PepsiCo");
		linkedList.add("DrPepper");
		linkedList.add("GoldSpot");
		linkedList.add("GoldSpot");
		linkedList.add("CocaCola");
		linkedList.add("Moxie");
		linkedList.add("GoldSpot");
		linkedList.add("Moxie");
		
		System.out.println("LinkedList: ");
		System.out.println(linkedList);
		
		// get last index of GoldSpot
		int index = linkedList.lastIndexOf("DrPepper"); // 1
		
		System.out.println("\nLast index of the DrPepper in linkedList is: "+ index);
		
		// get last index of GoldSpot
		int indexGS = linkedList.lastIndexOf("GoldSpot"); // 6
		
		System.out.println("\nLast index of the GoldSpot in linkedList is: "+ indexGS);
		
		// get last index of Moxie
		int indexMoxie = linkedList.lastIndexOf("Moxie"); // 7
		
		System.out.println("\nLast index of the Moxie in linkedList is: "+ indexMoxie);
	}
}
```

Output:

```
LinkedList: 
[PepsiCo, DrPepper, GoldSpot, GoldSpot, CocaCola, Moxie, GoldSpot, Moxie]

Last index of the DrPepper in linkedList is: 1

Last index of the GoldSpot in linkedList is: 6

Last index of the Moxie in linkedList is: 7
```



## Conclusion

We can use the and method to get index of the elements from the linkedlist.

1. `indexOf(Object o)`  - returns the index of the first occurrence of the specified element in this list

   ```java
   // get first index of GoldSpot from the linkedList
   int index = linkedList.indexOf("GoldSpot");
   ```

   

2. `lastIndexOf(Object o)` - returns the index of the last occurrence of the specified element in this list

   ```java
   // get last index of GoldSpot from the linkedList
   int index = linkedList.lastIndexOf("GoldSpot");
   ```

   

Both the method returns -1, if the specifed element is not present in the LinkedList.

---

The example java programs given in the above tutorial can be found at [this GitHub Repository](https://github.com/coderolls/blogpost-coding-examples/tree/main/collections/LinkedList/get-an-index-of-element-of-linkedlist).

Let me know you thoughts or suggestions on the topic discussed above in comment section below.