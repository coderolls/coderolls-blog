---  
layout: post  
title: "ArrayList isEmpty() method in Java"  
author: gaurav  
categories: [Collections, ArrayList]
toc: true  
description: "In this short tutorial, we will see the isEmpty() method of the ArrayList class in Java. This method is used to check if the ArrayList is empty or not."  
---
In this tutorial, we will see the `isEmpty()` method of the  [ArrayList class in Java](https://coderolls.com/arraylist-in-java/). This method is used to check if the ArrayList is empty or not.

## Introduction  
ArrayList is a widely used class to store and retrieve data in a collection framework.

In previous articles, we have various methods to perform operations on the ArrayList.

A few methods of ArrayList class are [`add()`](https://coderolls.com/add-element-in-arraylist/), [`addAll()`](http://https://coderolls.com/arraylist-addall-method-in-java/), [`remove()`](https://coderolls.com/remove-element-from-arraylist/), [`set()`](https://coderolls.com/change-element-in-arraylist/), [`iterate()`](https://coderolls.com/iterating-the-arraylist-in-java/), [`clear()`](https://coderolls.com/arraylist-clear-method-in-java/),  [`contains()`](https://coderolls.com/arraylist-contains-method), [`get()`](https://coderolls.com/arraylist-get-method), [`removeRange()`](https://coderolls.com/arraylist-removerange-method), [`retainAll()`](https://coderolls.com/arraylist-retainall-method),  [`trimToSize()`](https://coderolls.com/arraylist-trimtosize-method), [`indexOf()`](https://coderolls.com/arraylist-indexof-method) and  [`lastIndexOf()`](https://coderolls.com/arraylist-lastindexof-method),  [`removeIf()`](https://coderolls.com/arraylist-removeIf-method) and   [`removeAll()`](https://coderolls.com/arraylist-removeall-method)  method. 

Today we will see the `isEmpty()` method. 

## ArrayList `removeIf(Predicate filter)` method  

The `isEmpty()` method returns true if this list contains no elements.

The `isEmpty()` method checks if the ArrayList is empty or not. If it does not find any elements in the ArrayList, it will return `true`, otherwise `false`.

The method signature is given below

```java
public boolean isEmpty()
```

This method does not accept any parameter.

This method  has a return type as a `boolean`.  It returns true if ArrayList is empty.

Let's see an example Java program for the ArrayList `isEmpty()` method.

```java
import java.util.ArrayList;

/**
 * An example Java program for an isEmpty method 
 * of the ArrayList class in Java.
 * 
 * @author Gaurav Kukade at coderolls
 */
public class ArrayListIsEmptyExample {

  public static void main(String[] args) {
    //Create an ArrayList teams
    ArrayList<String> teams = new ArrayList<String>();
    
    //Add elements to the ArrayList teams
    teams.add("LA Galaxy");
    teams.add("Orlando City FC");
    teams.add("Portland Timbers");
    teams.add("Columbus Crew");
    
    boolean isTeamsEmpty = teams.isEmpty();
    if(isTeamsEmpty) {
      System.out.println("Teams ArrayList is empty.");
    }
    else {
      System.out.println("Teams ArrayList is not empty.");
    }
    
    // create an ArrayList players
    ArrayList<String> players = new ArrayList<String>();
    
    boolean isPlayersEmpty = players.isEmpty();
    if(isPlayersEmpty) {
      System.out.println("Players ArrayList is empty.");
    }
    else {
      System.out.println("Players ArrayList is not empty.");
    }
  }
}
```

Output:  
```
Teams ArrayList is not empty.
Players ArrayList is empty.
```

## Conclusion  

The `isEmpty()` method returns true if this list contains no elements.

```java
public boolean isEmpty()
```
---

The example Java program used in the above article can be found at [this GitHub repository](https://github.com/coderolls/blogpost-coding-examples/tree/main/collections/arraylist/arraylist-isempty-method).  

Please write your thoughts in the comment section below.
