---  
layout: post  
title: "ArrayList removeIf() method"  
author: gaurav  
categories: [Collections, ArrayList]  
description: "In this tutorial, we will see the removeIf(Predicate filter) method of the Arraylist class in Java."  
---
In this tutorial, we will see the `removeIf(Predicate filter)` method of the  [ArrayList class in Java](https://coderolls.com/arraylist-in-java/). This method removes all of the elements of this collection that satisfy the given predicate.

## Introduction  
ArrayList is a widely used class to store and retrieve data in a collection framework.

We have seen [how to remove elements from the ArrayList](https://coderolls.com/remove-element-from-arraylist/). Today, we will see how to remove elements from the ArrayList only if it satisfy the given predicate.

Predicate is a predefined functional interface in from Java 8. It has a single abstract method `test()` which is used to test the given condition.

Also, we have seen a few methods of the ArrayList class before like [`add()`](https://coderolls.com/add-element-in-arraylist/), [`addAll()`](http://https://coderolls.com/arraylist-addall-method-in-java/), [`remove()`](https://coderolls.com/remove-element-from-arraylist/), [`set()`](https://coderolls.com/change-element-in-arraylist/), [`iterate()`](https://coderolls.com/iterating-the-arraylist-in-java/), [`clear()`](https://coderolls.com/arraylist-clear-method-in-java/),  [`contains()`](https://coderolls.com/arraylist-contains-method), [`get()`](https://coderolls.com/arraylist-get-method), [`removeRange()`](https://coderolls.com/arraylist-removerange-method), [`retainAll()`](https://coderolls.com/arraylist-retainall-method),  [`trimToSize()`](https://coderolls.com/arraylist-trimtosize-method), [`indexOf()`](https://coderolls.com/arraylist-indexof-method) and  [`lastIndexOf()`](https://coderolls.com/arraylist-lastindexof-method)  method. 

Today we will see the `removeIf(Predicate filter)` method.  
  

## ArrayList `removeIf(Predicate filter)` method  

The `removeIf(Predicate filter)` method removes all of the elements of this collection that satisfy the given predicate.

The method signature is given below

```java
public boolean removeIf(Predicate<? super E> filter)
```

As shown in the method signature, this method accepts only one parameter `filter`. It is an instance of the Predicate Functional Interface. 

Predicate is a predefined functional Interface and used to test the conditions.

This method returns a `boolean` value. This method returns `true`, if any elements from the ArrayList is removed. Otherwise it returns `false`. 

Let's see an example java program for the ArrayList `removeIf()` method.

```java
import java.util.ArrayList;
import java.util.List;
import java.util.function.Predicate;

/**
 * A java program showing an example for the removeIf()
 * method of the ArrayList class in Java.
 * 
 * @author gaurav
 */
public class ArrayListRemoveIfExample {

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

		System.out.println("The states list before the removeIf() call: \n" + states);

		// a predicate for the condition
		Predicate p = s -> s.equals("Florida");
		states.removeIf(p); // removes all elements which satisfy the predicate p

		System.out.println("\nThe states list after the removeIf() call: \n" + states);
	}
}
```

Output:  
```
The states list before the removeIf() call: 
[California, Texas, Florida, Florida, New Jersey, Washington, Florida]

The states list after the removeIf() call: 
[California, Texas, New Jersey, Washington]
```

## Conclusion  

The `removeIf(Predicate filter)` method removes all of the elements of the ArrayList that satisfy the given predicate.

```java
public boolean removeIf(Predicate<? super E> filter)
```
---

The example java program used in the above article can be found at [this GitHub repository](https://github.com/coderolls/blogpost-coding-examples/tree/main/collections/arraylist/arraylist-removeif-method).  

Please write your thoughts in the comment section below.
