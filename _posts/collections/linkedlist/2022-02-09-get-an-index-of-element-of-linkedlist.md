---
layout: post
title: "How To Get An Index of the Element Of LinkedList?"
author: gaurav
categories: [Collections, LinkedList]
toc: true
description: "In this tutorial, we will see how to get an index of the element of the LinkedList. LinkedList class provides various methods to get an index of the element of the LinkedList. Let's see this method with an example."
---

In this tutorial, we will see how to get an index of the element from the LinkedList. LinkedList class provides various methods to get an index of the element of the LinkedList. Let's see this method as an example.

## Introduction

The LinkedList class is present in the `java.util` package.

[LinkedList](https:/coderolls.com/linkedlist-in-java/) internally uses a doubly LinkedList for storing the variables. That's why LinkedList is preferred when our frequent operation is insertion and deletion.

The LinkedList class provides the following method to an element from the list.

1. `indexOf(Object o)`
2. `lastIndexOf(Object o)`

## 1. `indexOf(Object o)`

The `indexOf(Object o)` method returns the index of the first occurrence of the specified element in this list, or -1 if this list does not contain the element.

The method signature is given below.

```java
public int indexOf(Object o)
```

This method uses the `equals()` method to check the equality of the element from linkedList and the specified element as a parameter.

I have given a Java program to get an index of the element of the LinkedList below.

```java
import java.util.LinkedList;

/**
 * A Java program to get the first index of the element from
 * the linkedlist using indexOf(Object o) method.
 * 
 * @author coderolls.com
 */
public class LinkedListIndexOf {

  public static void main(String[] args) {
    LinkedList<String> linkedList = new LinkedList<String>();
    linkedList.add("PepsiCo");
    linkedList.add("DrPepper");
    linkedList.add("GoldSpot");
    linkedList.add("GoldSpot");
    linkedList.add("CocaCola");
    linkedList.add("Moxie");
    linkedList.add("GoldSpot");
    linkedList.add("Moxie");
    
    System.out.println("LinkedList: ");
    System.out.println(linkedList);
    
    //Get the first index of GoldSpot
    int index = linkedList.indexOf("DrPepper"); // 1
    
    System.out.println("\nThe index of the DrPepper in linkedList is: "+ index);
    
    // get first index of GoldSpot
    int indexGS = linkedList.indexOf("GoldSpot"); // 2
    
    System.out.println("\nThe index of the GoldSpot in linkedList is: "+ indexGS);
    
    //Get the first index of Moxie
    int indexMoxie = linkedList.indexOf("Moxie"); // 5
    
    System.out.println("\nThe index of the Moxie in linkedList is: "+ indexMoxie);
  }
}
```

Output:

```
LinkedList: 
[PepsiCo, DrPepper, GoldSpot, GoldSpot, CocaCola, Moxie, GoldSpot, Moxie]

The index of the DrPepper in linkedList is: 1

The index of the GoldSpot in linkedList is: 2

The index of the Moxie in linkedList is: 5
```

## 2. `lastIndexOf(Object o)`

The `lastIndexOf(Object o)` method returns the index of the last occurrence of the specified element in this list, or -1 if this list does not contain the element.

The method signature for the `lastIndexOf(Object o)` method is given below.

```java
public int lastIndexOf(Object o)
```

This method uses the `equals()` method to check the equality of the element from linkedList and the specified element as a parameter.

I have given a Java program to get the last index of the element of the LinkedList below.

```java
import java.util.LinkedList;

/**
 * A Java program to get the last index of the element from
 * the linkedlist using lastIndexOf(Object o) method.
 * 
 * @author coderolls.com
 */
public class LinkedListLastIndexOf {

  public static void main(String[] args) {
    LinkedList<String> linkedList = new LinkedList<String>();
    linkedList.add("PepsiCo");
    linkedList.add("DrPepper");
    linkedList.add("GoldSpot");
    linkedList.add("GoldSpot");
    linkedList.add("CocaCola");
    linkedList.add("Moxie");
    linkedList.add("GoldSpot");
    linkedList.add("Moxie");
    
    System.out.println("LinkedList: ");
    System.out.println(linkedList);
    
    //Get the last index of GoldSpot
    int index = linkedList.lastIndexOf("DrPepper"); // 1
    
    System.out.println("\nThe last index of the DrPepper in linkedList is: "+ index);
    
    //Get the last index of GoldSpot
    int indexGS = linkedList.lastIndexOf("GoldSpot"); // 6
    
    System.out.println("\nThe last index of the GoldSpot in linkedList is: "+ indexGS);
    
    //Get the last index of Moxie
    int indexMoxie = linkedList.lastIndexOf("Moxie"); // 7
    
    System.out.println("\nThe last index of the Moxie in linkedList is: "+ indexMoxie);
  }
}
```
Output:
```
LinkedList: 
[PepsiCo, DrPepper, GoldSpot, GoldSpot, CocaCola, Moxie, GoldSpot, Moxie]

The last index of the DrPepper in linkedList is: 1

The last index of the GoldSpot in linkedList is: 6

The last index of the Moxie in linkedList is: 7
```

## Conclusion

We can use the method to get an index of the elements from the LinkedList.

1. `indexOf(Object o)`  - returns the index of the first occurrence of the specified element in this list

   ```java
   //Get the first index of GoldSpot from the LinkedList
   int index = linkedList.indexOf("GoldSpot");
   ```

2. `lastIndexOf(Object o)` - returns the index of the last occurrence of the specified element in this list

   ```java
   //Get the last index of GoldSpot from the LinkedList
   int index = linkedList.lastIndexOf("GoldSpot");
   ```

Both method returns -1 if the specified element is not present in the LinkedList.

---

The example Java programs given in the above tutorial can be found at [this GitHub Repository](https://github.com/coderolls/blogpost-coding-examples/tree/main/collections/LinkedList/get-an-index-of-element-of-linkedlist).

Let me know your thoughts or suggestions on the topic discussed above in the comment section below.
