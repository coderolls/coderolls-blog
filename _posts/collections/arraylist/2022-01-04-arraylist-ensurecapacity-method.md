---
layout: post  
title: "ArrayList ensureCapacity() method in Java"  
author: gaurav  
categories: [Collections, ArrayList]  
toc: true
description: "In this short tutorial, we will see the ensureCapacity(int minCapacity) method of the ArrayList class in Java." 
---

In this tutorial, we will see the `ensureCapacity(int minCapacity)` method of the  [ArrayList class in Java](https://coderolls.com/arraylist-in-java/). 

## Introduction  
ArrayList is a widely used class to store and retrieve data in a collection framework.

Unlike an array, ArrayList can dynamically grow in size.

In previous articles, we have various methods to perform operations on the ArrayList.

A few methods of ArrayList class are [`add()`](https://coderolls.com/add-element-in-arraylist/), [`addAll()`](http://https://coderolls.com/arraylist-addall-method-in-java/), [`remove()`](https://coderolls.com/remove-element-from-arraylist/), [`set()`](https://coderolls.com/change-element-in-arraylist/), [`iterate()`](https://coderolls.com/iterating-the-arraylist-in-java/), [`clear()`](https://coderolls.com/arraylist-clear-method-in-java/),  [`contains()`](https://coderolls.com/arraylist-contains-method), [`get()`](https://coderolls.com/arraylist-get-method), [`removeRange()`](https://coderolls.com/arraylist-removerange-method), [`retainAll()`](https://coderolls.com/arraylist-retainall-method),  [`trimToSize()`](https://coderolls.com/arraylist-trimtosize-method), [`indexOf()`](https://coderolls.com/arraylist-indexof-method) and  [`lastIndexOf()`](https://coderolls.com/arraylist-lastindexof-method),  [`removeIf()`](https://coderolls.com/arraylist-removeIf-method) and   [`removeAll()`](https://coderolls.com/arraylist-removeall-method)  method. 

Today we will see the `ensureCapacity(int minCapacity)` method. 

## ArrayList `ensureCapacity(int minCapacity)` method  

Before understanding the `ensureCapacity(int minCapacity)` method, we should know the [basics of the ArrayList class in Java](https://coderolls.com/arraylist-in-java/). 

ArrayList internally uses a dynamic array so it can grow dynamically.

The Initial default capacity for the ArrayList is 10. And load factor is 0.75F. So, while adding the 7th element, the new ArrayList with double capacity is created, and the remaining elements of the array get added to a new array.

When you have to ensure that your ArrayList should hold an `x` number of elements, you should invoke the `ensureCapacity(int x)` method on the ArrayList.

So, This method increases the capacity of this  ArrayList instance, if necessary, to ensure that it can hold at least the number of elements specified by the minimum capacity argument.

The method signature is as given below.
```java
public void ensureCapacity(int minCapacity)
```

This method accepts only one parameter, i.e. `minCapacity` of type `int`

- **`minCapacity`** - the desired minimum capacity

This method has a return type as a `void` which means it will not return anything.

Let's see a Java program where I will invoke the `ensureCapacity(int minCapacity)` method on the ArrayList object.

In ArrayList, class we do not have any method which gives us the current capacity, so I will be not able to show the increased capacity on the console, but since we are invoking the `ensureCapacity()` method, the capacity will be surely increased.

```java
/**
 * An example Java program for ensureCapacity(int MinCapacity) method 
 * of the ArrayList class in Java.
 * @author Gaurav at coderolls.com
 *
 */
public class ArrayListEnsureCapacityExample {

  public static void main(String[] args) {
    // create an empty ArrayList object 'states'
    ArrayList<String> states = new ArrayList<>();
    
    //Add state in the ArrayList
    states.add("California");
    states.add("Texas");
    states.add("Montana");
    states.add("Arizona");
    states.add("Florida");
    states.add("Michigan");
    states.add("New Jersey");
    states.add("Washington");
    states.add("Ohio");
    states.add("Minnesota");
    states.add("Colorado");
    states.add("Missouri");
    states.add("Nevada");
    System.out.println("ArrayList Elements are: \n"+ states);
    //We need to add more states, so we will ensure 
    //that ArrayList should hold 50 element
    states.ensureCapacity(50);
    
    System.out.println("\nWe ensured that the arraylist should hold 50 elements.");
  }
}
```

Output:  
```
ArrayList Elements are: 
[California, Texas, Montana, Arizona, Florida, Michigan, New Jersey, Washington, Ohio, Minnesota, Colorado, Missouri, Nevada]

We ensured that the ArrayList should hold 50 elements.
```

## Conclusion  

```java
public void ensureCapacity(int minCapacity)
```
This method increases the capacity of this  ArrayList  instance, if necessary, to ensure that it can hold at least the number of elements specified by the minimum capacity argument.

---
The example java program used in the above article can be found at [this GitHub repository](https://github.com/coderolls/blogpost-coding-examples/tree/main/collections/arraylist/arraylist-ensurecapacity-method).  

Please write your thoughts in the comment section below.
