---  
layout: post  
title: "ArrayList removeAll() method"  
author: gaurav  
categories: [Collections, ArrayList]
toc: true 
description: "In this tutorial, we will see the removeAll(Collection c) method of the ArrayList class in Java."  
---
In this tutorial, we will see the `removeAll(Collection c)` method of the  [ArrayList class in Java](https://coderolls.com/arraylist-in-java/). This method removes from this list all of its elements that are contained in the specified collection.

## Introduction  
ArrayList is a widely used class to store and retrieve data in a collection framework.

We have seen [how to remove elements from the ArrayList](https://coderolls.com/remove-element-from-arraylist/). Today, we will see how to remove all the elements from ArrayList specified in another collection.                                                                                                                                                                                       

Previously, we have seen a few methods of the ArrayList class before like [`add()`](https://coderolls.com/add-element-in-arraylist/), [`addAll()`](http://https://coderolls.com/arraylist-addall-method-in-java/), [`remove()`](https://coderolls.com/remove-element-from-arraylist/), [`set()`](https://coderolls.com/change-element-in-arraylist/), [`iterate()`](https://coderolls.com/iterating-the-arraylist-in-java/), [`clear()`](https://coderolls.com/arraylist-clear-method-in-java/),  [`contains()`](https://coderolls.com/arraylist-contains-method), [`get()`](https://coderolls.com/arraylist-get-method), [`removeRange()`](https://coderolls.com/arraylist-removerange-method), [`retainAll()`](https://coderolls.com/arraylist-retainall-method),  [`trimToSize()`](https://coderolls.com/arraylist-trimtosize-method), [`indexOf()`](https://coderolls.com/arraylist-indexof-method),   [`lastIndexOf()`](https://coderolls.com/arraylist-lastindexof-method)  and [`removeIf()`](https://coderolls.com/arraylist-removeIf-method) method. 

Today we will see the ` removeAll(Collection c)` method.
  

## ArrayList ` removeAll(Collection c)` method  

The ` removeAll(Collection c)` method removes from this list all of its elements that are contained in the specified collection.

The method signature is given below

```java
public boolean removeAll(Collection<?> c)
```

As shown in the method signature, this method accepts only one parameter i.e. Collection `c`. 

This method returns a `boolean` value. This method returns `true` if the ArrayList got changed as a method call. Otherwise, it returns `false`. 

Let's see an example Java program for the ArrayList `removeAll()` method.

```java
import java.util.ArrayList;
import java.util.List;
import java.util.function.Predicate;

/**
 * A Java program showing an example for the removeAll()
 * method of the ArrayList class in Java.
 * 
 * @author coderolls.com
 */
public class ArrayListRemoveAllExample {

  public static void main(String[] args) {
    // create an empty ArrayList object 'states'
    List<String> states = new ArrayList<String>();
    
    // add state in the ArrayList, Florida multiple times
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
    
    //Create another ArrayList for items to be removed
    List<String> statesToBeRemoved = new ArrayList<String>();
    statesToBeRemoved.add("Minnesota");
    statesToBeRemoved.add("Missouri");
    statesToBeRemoved.add("Montana");
    statesToBeRemoved.add("Michigan");
    
    System.out.println("The states list before the removeAll() method call: \n" + states);
    
    // removes all elements specified in the ArrayList statesToBeRemoved 
    states.removeAll(statesToBeRemoved); 
    
    System.out.println("\nThe states list after the removeAll() method call: \n" + states);
  }
}
```

Output:  
```
The states list before the removeAll() method call: 
[California, Texas, Montana, Arizona, Florida, Michigan, New Jersey, Washington, Ohio, Minnesota, Colorado, Missouri, Nevada]

The states list after the removeAll() method call: 
[California, Texas, Arizona, Florida, New Jersey, Washington, Ohio, Colorado, Nevada]
```

### Exceptions
We can get the following exceptions while invoking the `removeAll(Collection c)` method

1. `ClassCastException` 
2. `NullPointerException`

#### `ClassCastException`
If the class of an element of this list is incompatible with the specified collection, we can get the `ClassCastException`. This is an option restriction. (Read more about [optional](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html#optional-restrictions))

#### `NullPointerException` 
If this list contains a null element and the specified collection does not permit null elements, we can get the `NullPointerException`. This is an option restriction. (Read more about [optional](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html#optional-restrictions)). 

Or if the specified collection is null, we will surely get the `NullPointerException`.

Let's see an example Java program to show the case of `NullPointerException` while invoking the `removeAll()` method.

```java
import java.util.ArrayList;
import java.util.List;
import java.util.function.Predicate;

/**
 * A Java program showing a NullPointerException case 
 * for the removeAll() method of the ArrayList class in Java.
 * 
 * @author coderolls.com
 */
public class ArrayListRemoveAllNullPointerException {

  public static void main(String[] args) {
    // create an empty ArrayList object 'states'
    List<String> states = new ArrayList<String>();
    
    // add state in the ArrayList, Florida multiple times
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
    
    //Create another ArrayList with a null value, 
    //so that removeAll will throw NullPointerException
    List<String> statesToBeRemoved =null;
    
    System.out.println("The states list before the removeAll() method call: \n" + states);
    
    // removes all elements specified in the ArrayList statesToBeRemoved 
    states.removeAll(statesToBeRemoved); 
    
    System.out.println("\nThe states list after the removeAll() method call: \n" + states);
  }
}
```
Output:
```
The states list before the removeAll() method call: 
[California, Texas, Montana, Arizona, Florida, Michigan, New Jersey, Washington, Ohio, Minnesota, Colorado, Missouri, Nevada]
Exception in thread "main" java.lang.NullPointerException
	at java.util.Objects.requireNonNull(Objects.java:203)
	at java.util.ArrayList.removeAll(ArrayList.java:693)
	at com.gaurav.ExProject.ArrayList.ArrayListRemoveAllNullPointerException.main(ArrayListRemoveAllNullPointerException.java:43)
```

## Conclusion  

The `removeAll(Collection c)` method removes from this list all of its elements that are contained in the specified collection.
```java
public boolean removeAll(Collection<?> c)
```
---

The example Java program used in the above article can be found at [this GitHub repository](https://github.com/coderolls/blogpost-coding-examples/tree/main/collections/arraylist/arraylist-removeall-method).  

Please write your thoughts in the comment section below.
