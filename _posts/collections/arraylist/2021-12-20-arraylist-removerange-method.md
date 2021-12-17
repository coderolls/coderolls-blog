---  
layout: post  
title: "ArrayList removeRange() method in Java"  
author: gaurav  
categories: [Collections, ArrayList]  
description: "In this article, we will see removeRange() method of ArrayList class in Java. This method is used to remove a range of elements from the ArrayList."  
---

In this article, we will see `removeRange()` method of [ArrayList class in Java](https://coderolls.com/arraylist-in-java/). ArrayList class in Java. This method is used to remove a range of elements from the ArrayList.
  

## Introduction  
ArrayList is a widely used class to store and retrieve data in a collection framework.  

ArrayList is an ordered collection i.e. it maintains the insertion order of the elements. Also, it allows duplicate elements in the list.

We have seen [how to remove elements from the ArrayList](https://coderolls.com/remove-element-from-arraylist/). Today, we will see how to remove a range of elements from the ArrayList.

Also, We have seen a few methods of the ArrayList class before like [`add()`](https://coderolls.com/add-element-in-arraylist/), [`addAll()`](http://https://coderolls.com/arraylist-addall-method-in-java/), [`remove()`](https://coderolls.com/remove-element-from-arraylist/), [`set()`](https://coderolls.com/change-element-in-arraylist/), [`iterate()`](https://coderolls.com/iterating-the-arraylist-in-java/), [`clear()`](https://coderolls.com/arraylist-clear-method-in-java/),  [`contains()`](https://coderolls.com/arraylist-contains-method) and [`get()`](https://coderolls.com/arraylist-get-method) method.  

Today we will see the `removeRange()` method.  
  

## ArrayList `removeRange(int fromIndex,int toIndex)` method  
  
The `removeRange(int fromIndex, int toIndex)` method is **protected method** in ArrayList. A protected method is accessed in class, subclasses and in a package, but not public.

The `removeRange(int fromIndex,int toIndex)` method is used **to remove the range of elements from the subclass of ArrayList**.  It remove all the elements from index  `fromIndex` , inclusive, to `toIndex` exclusive.

The method signature is as given below.  

```java  
protected void removeRange(int fromIndex, int toIndex)  
```
As shown in the above method signature, it accepts two parameter.

{:class="table table-bordered"}
|Parameter|Description|
|:------------|:-------|
|`fromIndex`|index of first element to be removed|
|`toIndex`|index after last element to be removed|
  
The method has return type as a `void`. It means it does not return anything.

I have given an example java program to remove a range of elements from the subclass that extends ArrayList in Java using the `removeRange()` method.

Before starting the example, please remember **the parameter `fromIndex` is inclusive**. It means, the method will start removing the elements from `fromIndex`th element.

And **the parameter `toIndex` is exclusive**. It means, the method will remove elements till the `toIndex`index. It will not remove the element at `toIndex`th index.

Let's see the java program for better understanding.

```java
package com.gaurav.ExProject.ArrayList;

import java.util.ArrayList;
import java.util.List;

/**
 * A java program to remove the range of elements from 
 * the MyArraylist (a class which extends the ArrayList)
 * using the removeRange() method.
 * 
 * The removeRange() method is protected and is accessed in class,
 * subclasses and in a package, but not public.
 * 
 * @author Gaurav Kukade at coderolls.com
 *
 */
public class MyArrayList extends ArrayList<String> {

	public static void main(String[] args) {
		
		MyArrayList myArrayList = new MyArrayList();
        
		myArrayList.add("Monday");
		myArrayList.add("Tuesday");
		myArrayList.add("Wednesday");
		myArrayList.add("Thursday");
		myArrayList.add("Friday");
		myArrayList.add("Saturday");
		myArrayList.add("Sunday");
        
        System.out.println("Arraylist before removing range of elments:\n"+ myArrayList);
  
        myArrayList.removeRange(2, 4);
        
        System.out.println("\nArraylist after removing range of elments:\n"+ myArrayList); 
	}
}
```  

Output:  

```
Arraylist before removing range of elments:
[Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday]

Arraylist after removing range of elments:
[Monday, Tuesday, Friday, Saturday, Sunday]
```
  
## Conclusion  

We can use the `removeRange(int fromIndex, int toIndex)` method **to remove the range of elements from the subclass of ArrayList.** This range will start from the element at index `fromIndex` to the element before `toIndex` index.
 
 **The parameter `fromIndex` is inclusive and `toIndex` is exclusive.**

---
### Important Note:
The `removeRange(int fromIndex, int toIndex)` method is **protected method** in ArrayList. A protected method is accessed in class, subclasses and in a package, but not public.

---

The example java program used in the above article can be found at [this GitHub repository](https://github.com/coderolls/blogpost-coding-examples/tree/main/collections/arraylist/arraylist-removerange-method).  

Please write your thoughts in the comment section below.
