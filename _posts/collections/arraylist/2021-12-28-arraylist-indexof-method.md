---  
layout: post  
title: "ArrayList indexOf() method"  
author: gaurav  
categories: [Collections, ArrayList]  
description: "In this tutorial, we will see the  indexOf() method of the Arraylist class in Java."  
---
In this tutorial, we will see the `indexOf()` method of the  [ArrayList class in Java](https://coderolls.com/arraylist-in-java/). This method returns the index of the first occurrence of the specified element in this list.

## Introduction  
ArrayList is a widely used class to store and retrieve data in a collection framework.

Also, we have seen a few methods of the ArrayList class before like [`add()`](https://coderolls.com/add-element-in-arraylist/), [`addAll()`](http://https://coderolls.com/arraylist-addall-method-in-java/), [`remove()`](https://coderolls.com/remove-element-from-arraylist/), [`set()`](https://coderolls.com/change-element-in-arraylist/), [`iterate()`](https://coderolls.com/iterating-the-arraylist-in-java/), [`clear()`](https://coderolls.com/arraylist-clear-method-in-java/),  [`contains()`](https://coderolls.com/arraylist-contains-method), [`get()`](https://coderolls.com/arraylist-get-method), [`removeRange()`](https://coderolls.com/arraylist-removerange-method), [`retainAll()`](https://coderolls.com/arraylist-retainall-method) and [`trimToSize()`](https://coderolls.com/arraylist-trimtosize-method) method. 

Today we will see the `indexOf(Object o)` method.  
  

## ArrayList `indexOf(Object o)` method  

We know the important features of the list that it maintains the insertion order of the elements. Also, it allows duplicate elements in the list.

So, when we try to find any elements , there are chances that the same elements may present in the list multiple times at multiple index.

The `indexOf(Object o)` method **returns the index of the first occurrences of the object specified**. It **returns -1 if the specified object `o` is not present** in the list.

The method is signature is given below.

```java
public int indexOf(Object o)
```
The `indexOf()` method accepts only one parameter, the `Object o` whose index of the first occurrence will be returned.

The method has a return type as a `int`. It returns the index of the first occurrences of the object specified as an `int` . If the specified object `o` is not present in the list, it will return -1.

Let's see the java program for better understanding.

```java
/**
 * A java program to explain the indexOf() method
 * of the arrayList class in java.
 * 
 * @author Gaurav Kukade
 */
public class ArrayListIndexOfExample {

	public static void main(String[] args) {
		
		// create an empty arraylist object 'states'
		List<String> states = new ArrayList<String>();

		// add state in the arraylist, Florida multiple times
		states.add("California");
		states.add("Texas");
		states.add("Florida");
		states.add("Florida");
		states.add("New Jersey");
		states.add("Washington");
		states.add("Florida");
		
		int index = states.indexOf("Florida");
		
		//prints index of the first occurrences of Florida i.e. 2
		System.out.println("The index of the Florida: "+ index);
		
		//trying get the index of element, which is not present
		int index2 = states.indexOf("Alaska");
		
		System.out.println("The index of the Alaska: " + index2);
	}
}
```  

Output:  
```
The index of the Florida: 2
The index of the Alaska: -1
```

## Conclusion  

```java
public int indexOf(Object o)
```
The `indexOf(Object o)` method **returns the index of the first occurrences of the object specified**. If the specified object `o` is not present in the list, it returns the -1.

---

The example java program used in the above article can be found at [this GitHub repository](https://github.com/coderolls/blogpost-coding-examples/tree/main/collections/arraylist/arraylist-indexof-method).  

Please write your thoughts in the comment section below.
