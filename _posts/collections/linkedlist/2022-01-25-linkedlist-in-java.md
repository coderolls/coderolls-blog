---
layout: post
title: "LinkedList In Java"
author: gaurav
categories: [Collections, LinkedList]
toc: true

description: "In this article, we will see LinkedList in Java. How LinkedList are createed? Its various type of constructors for creating an LinkedList object. Also, some important features with their respective example."
---

In this article, we will see LinkedList in Java. How LinkedList are createed? Its various type of constructors for creating an LinkedList object. Also, some important features with their respective example.

## Introduction

LinkedList class is present in the `java.util` package. LinkedList implements the List interface from the Collections.

LinkedList allows duplicates and a null value. Also, it maintains the insertion order.

LinkedList implements the Serializable and Cloneable interface. it does not implement the RandomAccess interface.

LinkedList internally uses a doubly linked list data structure to store the objects.

Hence, the element stored in the LinkedList acts as a separate object, and every element is connected by its addresses. So inserting and deleting the elements is an easy and efficient operation. And that's why LinkedList is preferred over arrays if our frequent operations are insertions and deletions.

But as we discussed, every single element act as a separate object. And it is linked by their addresses.

We can not move directly to the desired element. First, we need to go to the head element, and then from the head element, we get the address of the next element, and so on till our desired element.

It makes retrieving operations very inefficient and time-consuming, and that's why LinkedList is not preferred for storing and retrieving operations.



## Constructors in the LinkedList

LinkedList provides two types of constructors to create a new LinkedList object.

1. LinkedList()
2. LinkedList(Collection c)

### 1. LinkedList()

This constructor constrcts an emeply List.

```java
LinkedList<String> list = new LinkedList<String>(); 
```

### 2.LinkedList(Collection<? extends E> c)

This constructor constructs a linkedList conatining the elements of the specified collection, in the order they are returned by the collection's iterator.

```java
List<String> arrayList = new ArrayList<String>();
arrayList.add("John");
arrayList.add("Mark");
arrayList.add("Ruby");
arrayList.add("Lucy");

// it constructs a linkedlist containting elements of the above arrayList
List<String> linkedList = new LinkedList<String>(arrayList);
```



## Methods of the LinkedList 

{:class="table table-bordered"}

| Methods       | Description                                                  |
| :------------ | ------------------------------------------------------------ |
| addFirst(E e) | Inserts the specified element at the beginning of this list. |
| addLast(E e)  | Inserts the specified element to the end of this list.       |
| getFirst()    | Returns the first element in this list.                      |
| getLast()     | Returns the last element in this list.                       |
| removeFirst() | Removes and returns the first element from this list.        |
| removeLast()  | Removes and returns the last element from this list.         |



## Features

### 1. LinkedList maintains the insertion order.

Let's see a simple java program to prove that LinkedList maintains the insertion order.

```java
import java.util.LinkedList;
/**
 * A Java program to prove that LinkedList maintains insertion order
 * @author coderolls.com
 *
 */
public class LinkedListInsertionOrder {

	public static void main(String[] args) {

		LinkedList<String> linkedList = new LinkedList<String>();
		linkedList.add("John");
		linkedList.add("Mark");
		linkedList.add("Ruby");
		linkedList.add("Lucy");
		linkedList.add("Vikram");
		
		System.out.println(linkedList);
	}
}
```

Output:

```te
[John, Mark, Ruby, Lucy, Vikram]
```

#### Explanation

1. I have created an empty LinkedList object `linkedList` of String.
2. I have added a few Strings to the `linkedList`
3. I have printed the `linkedList` object using the sysout statement. We can see the output strings are in the inserted order only.

### 2. LinkedList allows the duplicate elements.

I have given a simple java program to prove that LinkedList allows the duplicate elements.

```java
import java.util.LinkedList;
/**
 * A Java program to prove that LinkedList Allows Duplicates
 * @author coderolls.com
 *
 */
public class LinkedAllowDuplicates {

	public static void main(String[] args) {

		LinkedList<String> linkedList = new LinkedList<String>();
		linkedList.add("John");
		linkedList.add("Mark");
		linkedList.add("Mark");
		linkedList.add("Mark");
		linkedList.add("Ruby");
		linkedList.add("Lucy");
		linkedList.add("Vikram");
		linkedList.add("Vikram");
		
		System.out.println(linkedList);
	}
}
```

Output:

```
[John, Mark, Mark, Mark, Ruby, Lucy, Vikram, Vikram]
```

#### Explanation

1. I have created an empty LinkedList object `linkedList` of String.
2. I have added some Strings to the `linkedList`, a few of the String oobjects are duplicates.
3. I have printed the `linkedList` object using the sysout statement. We can see the output containsthe duplicate strings.

### 3. LinkedList allows the null values.

I have given a simple java program below to show that LinkedList allows the null values.

```java
import java.util.LinkedList;
/**
 * A Java program to prove that LinkedList Allows null values
 * @author coderolls.com
 *
 */
public class LinkedAllowDuplicates {

	public static void main(String[] args) {

		LinkedList<String> linkedList = new LinkedList<String>();
		linkedList.add("John");
		linkedList.add(null);
		linkedList.add("Mark");
		linkedList.add(null);
		linkedList.add("Ruby");
		linkedList.add("Lucy");
		linkedList.add("Vikram");
		linkedList.add(null);
		
		System.out.println(linkedList);
	}
}
```

Output:

```
[John, null, Mark, null, Ruby, Lucy, Vikram, null]
```

#### Explanation

1. I have created an empty LinkedList object `linkedList` of String.
2. I have added a few Strings to the `linkedList`. Also, I have added a few `null` values too.
3. I have printed the `linkedList` object using the sysout statement. We can see the output contains the null values.

---

The example java programs given in the above tutorial can be found at [this GitHub Repository](https://github.com/coderolls/blogpost-coding-examples/tree/main/collections/linkedlist/linkedlist-in-java).

Let me know you thoughts or suggestions on the topic discussed above in comment section below.
