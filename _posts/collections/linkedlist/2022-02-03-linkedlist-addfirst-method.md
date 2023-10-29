---
layout: post
title: "How To Add Element At The Beginning Of LinkedList?"
author: gaurav
categories: [Collections, LinkedList]
toc: true
description: "In this short tutorial, we will see the addFirst() method of the LinkedList class in Java with an example."
---

In this article, we will see the addFirst() method of the LinkedList class in Java with an example.

## Introduction

[LinkedList](https:/coderolls.com/linkedlist-in-java/) internally uses doubly linkedlist for storing the variables. That's why LinkedList is preferred when our frequent operation is insertion and deletion.

To insert the elements with ease at the beginning of the LinkedList, the Language Developers have provided the `addFirst()` method.

## LinkedList `addFirst()` Method

The addFirst() method will insert the specified element at the beginning of this list.

The method signature for `addFirst()` method is given below.

```java
public void addFirst(E e)
```

Here, `e` is an element to be added at the beginning of the List.

The return type of this method is `void`, it means, this method do not return anything.

I have given a simple Java program for the `addFirst()` method below.

```java
import java.util.LinkedList;

public class LinkedListAddFirst {

  public static void main(String[] args) {
    LinkedList<String> linkedList = new LinkedList<String>();
    linkedList.add("Austin");
    linkedList.add("Boston");
    linkedList.add("Atlanta");
    linkedList.add("Madison");
    linkedList.add("Columbia");
    
    System.out.println(linkedList);
    
    //Add an element at the beginning
    linkedList.addFirst("Albany");
    System.out.println(linkedList);
  }

}
```

Output:

```
[Austin, Boston, Atlanta, Madison, Columbia]
[Albany, Austin, Boston, Atlanta, Madison, Columbia]
```

## Conclusion

```java
public void addFirst(E e)
```

The `addFirst()` method will insert the specified element at the beginning of this list.

---

The example Java programs given in the above tutorial can be found at [this GitHub Repository](https://github.com/coderolls/blogpost-coding-examples/tree/main/collections/linkedlist/linkedlist-addfirst-method).

Let me know your thoughts or suggestions on the topic discussed above in the comment section below.
