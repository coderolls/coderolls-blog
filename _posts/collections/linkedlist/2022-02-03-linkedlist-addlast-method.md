---
layout: post
title: "LinkedList addLast() Method"
author: gaurav
categories: [Collections, LinkedList]
toc: true

description: "In this short tutorial, we will see the addLast() method of the LinkedList class in Java with example."
---

In this article, we will see the addLast() method of the LinkedList class in Java with example.

## Introduction

LinkedList class is present in the java.util package.

[LinkedList](https:/coderolls.com/linkedlist-in-java/) internally uses doubly linkedlist for storing the variables. That's why LinkedList is preferred when our frequeent operatioon is insertion and deletion.

To insert the elements at the end of the LinkedList, we can use the `addLast()` method.

## LinkedList `addLast()` Method

The `addLast()` method will inserts the specified element at the end of this list.

The `addLast()` method is equivalent to the add() method.

The method signature for `addLast()` method is gioven below.

```java
public void addLast(E e)
```

The parameter `e` is an element to be added at the end of the List.

The return type of this method is `void`, it means, this method do not return anything.

I have given a simple Java program for the `addLast()` method below.

```java
import java.util.LinkedList;

public class LinkedListAddLast {

	public static void main(String[] args) {
	
		LinkedList<String> linkedList = new LinkedList<String>();
		linkedList.add("Austin");
		linkedList.add("Boston");
		linkedList.add("Atlanta");
		linkedList.add("Madison");
		linkedList.add("Columbia");
		
		System.out.println(linkedList);
		
		// add element at the end
		linkedList.addLast("Albany");
		System.out.println(linkedList);

	}

}
```

Output:

```
[Austin, Boston, Atlanta, Madison, Columbia]
[Austin, Boston, Atlanta, Madison, Columbia, Albany]
```

## Conclusion

```java
public void addLast(E e)
```

The `addLast()` method will inserts the specified element at the end of this list. This method is equivalent to the `add()` method.

---

The example java programs given in the above tutorial can be found at [this GitHub Repository](https://github.com/coderolls/blogpost-coding-examples/tree/main/collections/linkedlist/linkedlist-addLast-method).

Let me know you thoughts or suggestions on the topic discussed above in comment section below.

 





