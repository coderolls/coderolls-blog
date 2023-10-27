---
layout: post
title: "ArrayList get() method in Java"
author: gaurav
categories: [Collections, ArrayList]
toc: true
description: "In this article, we will see the `get()` method of the ArrayList class in Java. This method is used to get an ArrayList element by its index."
---

In this article, we will see the `get()` method of [ArrayList class in Java](https://coderolls.com/arraylist-in-java/). This method is used to get an ArrayList element by its index.

## Introduction

ArrayList is a widely used class to store and retrieve data in a collection framework.

ArrayList is an ordered collection i.e. it maintains the insertion order of the elements. Also, it allows duplicate elements in the list.

When we [iterate over an ArrayList](https://coderolls.com/iterating-the-arraylist-in-java/) using a for loop, the variable `i` will be the current index of the list. We can use the variable `i` in the `get(int index)` method to get the element at index `i`.

We have seen a few methods of the ArrayList class before like [`add()`](https://coderolls.com/add-element-in-arraylist/), [`addAll()`](http://https://coderolls.com/arraylist-addall-method-in-java/), [`remove()`](https://coderolls.com/remove-element-from-arraylist/), [`set()`](https://coderolls.com/change-element-in-arraylist/), [`iterate()`](https://coderolls.com/iterating-the-arraylist-in-java/), [`clear()`](https://coderolls.com/arraylist-clear-method-in-java/) and [`contains()`](https://coderolls.com/arraylist-contains-method).

Today we will see the `get()` method.

## ArrayList `get(int index)` method

The `get()` method is used to get the ArrayList element by its index.

The method signature is given below.
```java
public E get(int index)
```

As shown in the above method signature, it returns the element `E` from the ArrayList.

It accepts the single parameter `index` of type `int`.

I have given an example Java program to get an ArrayList element by its index using the `get()` method.

```java
import java.util.ArrayList;
import java.util.List;

/**
 * A Java program to get the element by 
 * its index using the get() method
 * 
 * @author Gaurav Kukade at coderolls.com
 */
public class ArrayListGetExample {

  public static void main(String[] args) {
    List<String> list = new ArrayList<String>();
    
    list.add("Monday");
    list.add("Tuesday");
    list.add("Wednesday");
    list.add("Thursday");
    list.add("Friday");
    list.add("Saturday");
    list.add("Sunday");
    
    System.out.println("Arraylist:"+ list);
    
    // get element at index 3
    String element = list.get(3);
    System.out.println("\nThe element at index 3 is "+ element);
    
    System.out.println("\nUsing the get() method in for loop: \n");
    
    // using the get(0 method in for loop
    for(int i=0; i<list.size(); i++) {
      System.out.println("The element at index "+i+" is "+ list.get(i));
    }
  }
}
```
Output:
```
Arraylist:[Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday]

The element at index 3 is Thursday

Using the get() method in for loop: 

The element at index 0 is Monday
The element at index 1 is Tuesday
The element at index 2 is Wednesday
The element at index 3 is Thursday
The element at index 4 is Friday
The element at index 5 is Saturday
The element at index 6 is Sunday
```

# Conclusion
We can use the get(int index) method to get an Arraylist element by its index.

The element from an `arrayList` at index `i` can be obtained as 
```java
arrayList.get(i);
```

---

The example java program used in the above article can be found at [this GitHub repository](https://github.com/coderolls/blogpost-coding-examples/tree/main/collections/arraylist/arraylist-get-method).

Please write your thoughts in the comment section below.
