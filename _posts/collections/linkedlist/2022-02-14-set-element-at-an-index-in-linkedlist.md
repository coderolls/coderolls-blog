---
layout: post
title: "How To Set An Element At A Particular Index In LinkedList?"
author: gaurav
categories: [Collections, LinkedList]
toc: true

description: "In this short tutorial, we will see how to set an element at a particular index in linkedList."
---

In this short tutorial, we will see how to set an element at a particular index in linkedList.

## Introduction

LinkedList class is present in the `java.util` package.

[LinkedList](https:/coderolls.com/linkedlist-in-java/) internally uses a doubly linkedlist for storing the variables. That's why LinkedList is preferred when our frequent operation is insertion and deletion.

Whenever we want to set an element at a particular index in the LinkedList, we can use the `set(int index, E element)` method.

## Set An Element Using `set(int index, E element)` Method

LinkedList class provides the `set(int index, E element)` method to set an element at a particular index in the LinkedList. This method replaces the existing element with the specified element (`element`) at the specified index (`index`).

The method signature is as given below.

```java
public E set(int index,E element)
```

This method accepts two parameters as given below.

**Parameters:**

`index` - index of the element to replace

`element` - element to be stored at the specified position

This method returns **the element previously at the specified position.**

I have given a java program to set an element at a particular index in LinkedList.

```java
import java.util.LinkedList;

/**
 * A java program to set an element at specified index
 * using the set(int index, E element) method.
 * 
 * @author coderolls.com
 */
public class LinkedListSet {

	public static void main(String[] args) {
		LinkedList<String> linkedList = new LinkedList<String>();
		
		linkedList.add("IN");
		linkedList.add("US");
		linkedList.add("FR");
		linkedList.add("JP");
		linkedList.add("CN");
		linkedList.add("RU");
		
		System.out.println("LinkedList before setting an element at index 4:");
		System.out.println(linkedList);
		
		// replaces CN with BR 
		// returns the previously present element at index 4 i.e CN
		String previousElement = linkedList.set(4, "BR");
		
		System.out.println("\nLinkedList after setting an element BR at index 4:");
		System.out.println(linkedList);
		
		System.out.println("\nPreviously present element at index 4:");
		System.out.println(previousElement);
	}
}
```

Output:

```
LinkedList before setting an element at index 4:
[IN, US, FR, JP, CN, RU]

LinkedList after setting an element BR at index 4:
[IN, US, FR, JP, BR, RU]

Previously present element at index 4:
CN
```

## Conclusion

```java
public E set(int index,E element)
```

We can use the `set(int index, E element)` method to set an element at a particular index in the LinkedList.

```java
// replaces the element at index 4 with "BR"
// returns the previously present element at index 4
linkedList.set(4, "BR");
```

This method **replaces the element at the specified position in this list with the specified element.**

---

The example java programs given in the above tutorial can be found at [this GitHub Repository](https://github.com/coderolls/blogpost-coding-examples/tree/main/collections/LinkedList/set-element-at-an-index-in-linkedlist).

Let me know you thoughts or suggestions on the topic discussed above in comment section below.