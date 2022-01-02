---
layout: post
title: "How To Add An Element To ArrayList In Java?"
author: gaurav
categories: [Collections, ArrayList]
toc: true
description: "In this article, we will see how to add element in ArrayList. Also, we will see how can we add an element at particular index in ArrayList."
---

In this article, we will see how to add an element in [ArrayList](https://coderolls.com/arraylist-in-java/). Also, we will see how can we add an element at particular index in ArrayList.

## Introduction

We can add an element to the end of [ArrayList](https://coderolls.com/arraylist-in-java/) using the `add(E e)` method. 

To add an element to a particular index, we can use the `add(int index, E element)` method.

Let's see these two methods one by one.

## 1. `add(E e)`

This method has a signature as 
`public boolean add(E e)`.

This method adds an element to the end of the list.

This method returns `true` if the element is added to the list otherwise, it returns `false`.

Let's see a java program to add an element to the list using the above method.

```java

import java.util.ArrayList;

/**
 * A Java program to add an element to the list.
 * 
 * The add(E e) method will add an element to 
 * the end of the arrayList.
 * 
 * @author Guarav Kukade at coderolls.com
 *
 */
public class ArrayListExample {

	public static void main(String[] args) {
		
		ArrayList<String> arrayList = new ArrayList<String>();
		
		//adding elements to the arrayList
		arrayList.add("Gaurav");
		arrayList.add("Shyam");
		
		System.out.println(arrayList);// [Gaurav, Shyam]
		
		// adding an element to  the arrayList
		// element will be added to the end of the arrayList
		arrayList.add("Saurav");
		
		System.out.println(arrayList); // [Gaurav, Shyam, Saurav]

	}
}
```
Output:
```
[Gaurav, Shyam]
[Gaurav, Shyam, Saurav]
```

## 2. `add(int index, E element)`

This method has a method signature as `public void add(int index, E element)`.

This method adds an element at the specified `index`.

This method has a return type as `void` so, it will not return anything.

Below, we will see a java program to add an element at the specified index in ArrayList.

```java
import java.util.ArrayList;

/**
 * A Java program to add an element at the specific index.
 * 
 * The add(int index, E element) method will add 
 * an element at the specified index in ArrayList.
 * 
 * @author Guarav Kukade at coderolls.com
 *
 */
public class ArrayListAddExample {

	public static void main(String[] args) {
		
		ArrayList<String> arrayList = new ArrayList<String>();
		
		//adding elements to the arrayList using normal add method
		arrayList.add("Gaurav");
		arrayList.add("Shyam");
		
		System.out.println(arrayList);// [Gaurav, Shyam]
		
		// adding an element to  the arrayList at index 1
		arrayList.add(1, "Saurav");
		
		System.out.println(arrayList); // [Gaurav, Saurav, Shyam]
	}
}
```
Output:
```
[Gaurav, Shyam]
[Gaurav, Saurav, Shyam]
```

## Conclusion

We can add element to the [ArrayList](https://coderolls.com/arraylist-in-java/) using `add()` method in two ways.
1. `add(E e)` - It will add an element to the end of the ArrayList
2. `add(int index, E element)`- This method will add an element at the specified index

---

The example java programs given in the above tutorial can be found at [this GitHub Repository](https://github.com/coderolls/blogpost-coding-examples/tree/main/collections/arraylist/add-element-in-arraylist).

If you know any other ways, you a can write a comment below.
