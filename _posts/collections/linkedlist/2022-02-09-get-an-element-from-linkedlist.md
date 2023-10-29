---
layout: post
title: "How To Get An Element From LinkedList?"
author: gaurav
categories: [Collections, LinkedList]
toc: true
description: "In this tutorial, we will see how to get an element from the LinkedList. LinkedList class provides various methods to get an element from the LinkedList. Let's see this method with an example."
---

In this tutorial, we will see how to get an element from the LinkedList. LinkedList class provides various methods to get an element from the LinkedList. Let's see this method as an example.

## Introduction

The LinkedList class is present in the `java.util` package.

[LinkedList](https:/coderolls.com/linkedlist-in-java/) internally uses a doubly linkedlist for storing the variables. That's why LinkedList is preferred when our frequent operation is insertion and deletion.

LinkedList class provides the following method to an element from the list.

1. `get(int index)`
2. `getFirst()`
3. `getLast()`

## 1. `get(int index)`

The `get(int index)` method **returns the element at the specified position (`index`) in this list.**

The method signature is given below.

```java
public E get(int index)
```

This method accepts a parameter `index` of type int, an index of the element that needs to be returned.

I have given a Java program below to get an element from the LinkedList using the `get(int index) `method.

```java
import java.util.LinkedList;

/**
 * A Java program to get an element from
 * the LinkedList by its index.
 * 
 * @author coderolls.com
 */
public class LinkedListGetElement {

  public static void main(String[] args) {
    LinkedList<String> linkedList = new LinkedList<String>();
    linkedList.add("Adidas");
    linkedList.add("Air");
    linkedList.add("Nike");
    linkedList.add("Puma");
    linkedList.add("Reebok");
    
    System.out.println("LinkedList: ");
    System.out.println(linkedList);
    
    // get element at index 3
    String element = linkedList.get(3); // Puma
    
    System.out.println("\nElement at index 3 is "+ element);
  }
}
```

Output:

```
LinkedList: 
[Adidas, Air, Nike, Puma, Reebok]

Element at index 3 is Puma
```

## 2. `getFirst()`

This method **returns the first element in this list.**

The method signature is given below.

```java
public E getFirst()
```

This method does not accept a parameter.

I have given a Java program to get an element from the LinkedList using the `getFirst()` method.

```java
import java.util.LinkedList;

/**
 * A Java program to get the first element from
 * the linkedlist using getFirst() method.
 * 
 * @author coderolls.com
 */
public class LinkedListGetFirst {

  public static void main(String[] args) {
    LinkedList<String> linkedList = new LinkedList<String>();
    linkedList.add("Adidas");
    linkedList.add("Air");
    linkedList.add("Nike");
    linkedList.add("Puma");
    linkedList.add("Reebok");
    
    System.out.println("LinkedList: ");
    System.out.println(linkedList);
    
    //Get the first element
    String element = linkedList.getFirst(); // Adidas
    
    System.out.println("\nFirst element of the linkedList is: "+ element);
  }
}
```

Output:

```
LinkedList: 
[Adidas, Air, Nike, Puma, Reebok]

The first element of the linkedList is: Adidas
```



## 3. `getLast()`

This method returns the last element in this list.

The method signature is given below.

```java
public E getLast()
```

This method does not accept a parameter.

I have given a Java program to get an element from the LinkedList using the `getFirst()` method.

```java
import java.util.LinkedList;

/**
 * A Java program to get the last element of
 * the linkedlist using getLast() method.
 * 
 * @author coderolls.com
 */
public class LinkedListGetLast {

  public static void main(String[] args) {
    LinkedList<String> linkedList = new LinkedList<String>();
    linkedList.add("Adidas");
    linkedList.add("Air");
    linkedList.add("Nike");
    linkedList.add("Puma");
    linkedList.add("Reebok");
    
    System.out.println("LinkedList: ");
    System.out.println(linkedList);
    
    //Get the first element
    String element = linkedList.getLast(); // Adidas
    
    System.out.println("\nThe last element of the linkedList is: "+ element);
  }
}
```

Output:

```
LinkedList: 
[Adidas, Air, Nike, Puma, Reebok]

The last element of the linkedList is: Reebok
```

## Conclusion

The LinkedList class provides the following method to get an element from the LinkedList.

1. `get(int index)`

   ```java
   //Get an element at index 3
   String element = linkedList.get(3);
   ```

2. `getFirst()`

   ```java
   //Get the first element
   String element = linkedList.getFirst();
   ```

3. `getLast()`

   ```java
   //Get the last element
   String element = linkedList.getLast();
   ```

---

The example Java programs given in the above tutorial can be found at [this GitHub Repository](https://github.com/coderolls/blogpost-coding-examples/tree/main/collections/LinkedList/get-an-element-from-linkedlist).

Let me know your thoughts or suggestions on the topic discussed above in the comment section below.
