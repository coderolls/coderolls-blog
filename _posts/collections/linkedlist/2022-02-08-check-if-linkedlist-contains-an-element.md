---
layout: post
title: "How To Check If LinkedList Contains The ELement?"
author: gaurav
categories: [Collections, LinkedList]
toc: true
description: "In this short tutorial, we will see, how to check if a LinkedList contains a particular element. LinkedList class provide a method to check if the specified element is present in the LinkedList or not. Let's see this method with an example."
---

In this short tutorial, we will see how to check if a LinkedList contains a particular element. LinkedList class provides a method to check if the specified element is present in the LinkedList or not. Let's see this method with an example.

## Introduction

The LinkedList class is present in the `java.util` package.

[LinkedList](https:/coderolls.com/linkedlist-in-java/) internally uses a doubly linkedlist for storing the variables. That's why LinkedList is preferred when our frequent operation is insertion and deletion.

Sometimes we need to check if the element is present in the LinkedList or not.

LinkedList provides the `contains(Object o)` method to check if the specified element is present in the LinkedList.

## Check If LinkedList Contains The Elelement Using `contains(Object o)` Method

The `contains(Object o)` method **returns true, if the list contains the specified element `o`.**

It will use the `equals()` method to check if the element from the list and the specified object are the same or not.

The method signature for the `contains()` method is given below.

```java
public boolean contains(Object o)
```

I have given a Java program to check if the element is present in the LinkedList or not.

```java
import java.util.LinkedList;

/**
 * A Java program to check if the element is present 
 * in the linkedList using the contains(Object o) method.
 * 
 * @author coderolls.com
 *
 */
public class LinkedListContains {

  public static void main(String[] args) {
    LinkedList<String> linkedList = new LinkedList<String>();
    linkedList.add("Uber");
    linkedList.add("Ola");
    linkedList.add("Didi");
    linkedList.add("Lyft");
    linkedList.add("Yandex");
    
    System.out.println("LinkedList is as follows: \n"+ linkedList);
    
    //Checks if the linkedList contains "Ola"
    //Returns true if present
    boolean isOlaPresnet = linkedList.contains("Ola"); // true
    
    System.out.println("\nCheck if linkedList contains Ola: "+ isOlaPresnet);
    
    //Checks if the linkedList contains "Grab"
    //Returns true if present
    boolean isGrabPresnet = linkedList.contains("Grab"); // false
    
    System.out.println("\nCheck if linkedList contains Grab: "+ isGrabPresnet);
  
  }
}
```

Output:

```
LinkedList is as follows: 
[Uber, Ola, Didi, Lyft, Yandex]

Check if LinkedList contains Ola: true

Check if LinkedList contains Grab: false
```

## Conclusion

```java
public boolean contains(Object o)
```

We can use the `contains(Object o)` method to check if the specified element is present in the list or not.

```java
// checks if the linkedList contains "Grab"
// returns true if present
boolean isGrabPresnet = linkedList.contains("Grab");
```

---

The example Java programs given in the above tutorial can be found at [this GitHub Repository](https://github.com/coderolls/blogpost-coding-examples/tree/main/collections/LinkedList/remove-element-from-linkedlist).

Let me know your thoughts or suggestions on the topic discussed above in the comment section below.
