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

LinkedList class is present in the `java.util` package. LinkedList implements the **List** and **Deque** interfaces and extends the **AbstractSequentialList** class from the Collections.

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

| Methods                                                      | Description                                                  |
| :----------------------------------------------------------- | ------------------------------------------------------------ |
| [`add(Object o)`](https://coderolls.com/add-element-in-linkedlist/) | Appends the specified element to the end of a list.          |
| [`add(int index, Object element)`](https://coderolls.com/add-element-in-linkedlist/) | Inserts the specified element at the specified position index in a list. |
| [`addFirst(E e)`](https://coderolls.com/linkedlist-addfirst-method/) | Inserts the specified element at the beginning of this list. |
| [`addLast(E e)`](https://coderolls.com/linkedlist-addlast-method/) | Inserts the specified element to the end of this list.       |
| `size()`                                                     | Returns the number of elements in a list                     |
| `contains(Object o)`                                         | Return `true` if the list contains a specified element, else `false`. |
| [`remove()`](https://coderolls.com/remove-element-from-linkedlist/#1-remove) | Retrieves and removes the head (first element) of this list. |
| [`remove(Object o)`](https://coderolls.com/remove-element-from-linkedlist/#2-removeobject-o) | Removes the first occurence of the specified element in a list. |
| [`remove(int index)`](https://coderolls.com/remove-element-from-linkedlist/#3-removeint-index) | Removes the element at the specified position in this list.  |
| [`removeFirst()`](https://coderolls.com/remove-element-from-linkedlist/#4-removefirst) | Removes and returns the first element from this list.        |
| [`removeLast()`](https://coderolls.com/remove-element-from-linkedlist/#5-removelast) | Removes and returns the last element from this list.         |
| `getFirst()`                                                 | Returns the first element in this list.                      |
| `getLast()`                                                  | Returns the last element in this list.                       |
| `indexOf(Object o)`                                          | Returns the index in a list of the first occurrence of the specified element, or -1 if the list does not contain specified element. |
| `lastIndexOf(Object o)`                                      | Returns the index in a list of the last occurrence of the specified element, or -1 if the list does not contain specified element. |
| `iterator()`                                                 | Returns an iterator over the elements in this list in proper sequence. |
| [`toArray()`](https://coderolls.com/convert-linkedlist-to-array) | Returns an array containing all of the elements in this list in proper sequence. |
| `subList(int fromIndex, int toIndex)`                        | Returns a view of the portion of this list between the specified `fromIndex` (inclusive) and `toIndex` (exclusive). |

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
