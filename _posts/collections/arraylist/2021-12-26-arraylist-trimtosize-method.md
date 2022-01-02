---  
layout: post  
title: "ArrayList trimToSize() method"  
author: gaurav  
categories: [Collections, ArrayList] 
toc: true 
description: "In this tutorial, we will see the trimToSize() method of the Arraylist class in Java."  
---
In this tutorial, we will see the `trimToSize()` method of the  [ArrayList class in Java](https://coderolls.com/arraylist-in-java/). 

## Introduction  

In last few tutorials, we are looking at various methods of the ArrayList class in Java.

We have seen a few methods of the ArrayList class before like [`add()`](https://coderolls.com/add-element-in-arraylist/), [`addAll()`](http://https://coderolls.com/arraylist-addall-method-in-java/), [`remove()`](https://coderolls.com/remove-element-from-arraylist/), [`set()`](https://coderolls.com/change-element-in-arraylist/), [`iterate()`](https://coderolls.com/iterating-the-arraylist-in-java/), [`clear()`](https://coderolls.com/arraylist-clear-method-in-java/),  [`contains()`](https://coderolls.com/arraylist-contains-method), [`get()`](https://coderolls.com/arraylist-get-method), [`removeRange()`](https://coderolls.com/arraylist-removerange-method), [`retainAll()`](https://coderolls.com/arraylist-retainall-method) and [`subList()`](https://coderolls.com/sublist-method-in-arraylist) method. 

ArrayList is a widely used class to store and retrieve data in a collection framework.  

ArrayList is an ordered collection i.e. it maintains the insertion order of the elements. Also, it allows duplicate elements in the list.

Today we will see the `trimToSize()` method. 

This method trims the capacity of this ArrayList instance to be the list's current size.

## ArrayList `trimToSize()` method  

When we create a new ArrayList instance, it will get created with **the default initial capacity of 10**.

```java
List<String> states = new ArrayList<String>();
```

That means it reserves the 10 block in the memory to store the `arraylist` elements. So , if we add the 10 elements to the `arrayList`, the `arrayList` can potentially accommodate without reallocating its internal structures.

But, if we just added two elements to the `arrayList`, the remaining blocks will remain empty and not used.

```java
states.add("California");
states.add("Texas");
```

Here, we can use the `trimToSize()` method to trim the capacity of this `arrayList` instance to be the list's current size.

```java
states.trimToSize();
```
So, if there are only two elements got added to the list and we invoke `trimToSize()` on it, the capacity will be two only. It frees the remaining reserved blocks from the memory.

The method is signature is given below.
```java
public void trimToSize()
```
This method does not accept any parameter and has a return type as a `void` i.e. it do not return anything.

Also, no exception occurs while invoking this method.

## Conclusion  

The `trimToSize()` method trims the capacity of this ArrayList instance to be the list's current size.

---

Please write your thoughts in the comment section below.
