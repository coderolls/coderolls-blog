---
layout: post
title: "How To Iterate LinkedList In Java?"
author: gaurav
categories: [Collections, LinkedList]
toc: true

description: "In this tutorial, we will see how to iterate linkedList in java. There are multiple ways to iterate such as loops, using Iterator or using Java 8 syntax.Let's see this ways to iterate over LinkedList in Java."
---

In this tutorial, we will see how to iterate linkedList in java. There are multiple ways to iterate such as loops, using Iterator or using Java 8 syntax.Let's see this ways to iterate over LinkedList in Java.

## Introduction

LinkedList class is present in the `java.util` package.

[LinkedList](https:/coderolls.com/linkedlist-in-java/) internally uses a doubly linkedlist for storing the variables. That's why LinkedList is preferred when our frequent operation is insertion and deletion.

There are multiple ways to iterate over the LinkedList. We will see the following ways

1.  Iterate the LinkedList using basic for loop
2.  Iterate the LinkedList using Enhanced For Loop i.e. For-each loop
3.  Iterate the LinkedList using while loop
4.  Iterate the LinkedList using Iterator
5.  Iterate the LinkedList using Java 8 forEach() Method

So let's see all the options one by one.

## 1. Iterate the LinkedList using basic for loop

We can write a simple for loop for the LinkedList and access the elements of the LinkedList using the `get(int index)` method.

Please refer the following Java example to iterate over LinkedList using the basic for loop.

```java
import java.util.LinkedList;
import java.util.List;

/**
 * A java program to iterate over linkedList
 * using the basic for loop.
 * 
 * @author Gaurav Kukade at coderolls.com
 *
 */
public class LinkedListForLoop {

	public static void main(String[] args) {

		List<String> linkedList = new LinkedList<String>();

		linkedList.add("Mango");
		linkedList.add("Banana");
		linkedList.add("Grapes");
		linkedList.add("Watermelon");
		linkedList.add("Apple");
		linkedList.add("Avocado");

		System.out.println("Iterating through LinkedList using the basic for loop!\n");
		
		int len = linkedList.size();
		
		// iterate over linkedList using basic for loop
		for (int i = 0; i < len; i++) {
			
			// get String object from linkedList at index i
			String str = linkedList.get(i);
			System.out.println("Object form the LinkedList at " + i + " is " + str);
		}
	}
}
```

Output:

```
Iterating through LinkedList using the basic for loop.......

Object form the LinkedList at 0 is Mango
Object form the LinkedList at 1 is Banana
Object form the LinkedList at 2 is Grapes
Object form the LinkedList at 3 is Watermelon
Object form the LinkedList at 4 is Apple
Object form the LinkedList at 5 is Avocado
```



## 2. Iterate the LinkedList using Enhanced For Loop i.e. For-each loop

Here we will use the [foreach loop i.e. Enhanced For Loop](https://coderolls.com/for-each-loop/) to iterate through ArrayList.

Let us understand the syntax for the Enhanced For Loop.

```java
for(DataType item:Array | Collection){
// operate on the item here
}
```

Please refer the following Java program to iterate over LinkedList using the [foreach loop](https://coderolls.com/for-each-loop/).

```java
import java.util.LinkedList;
import java.util.List;

/**
 * A java program to iterate over linkedList
 * using the foreach loop.
 * 
 * @author Gaurav Kukade at coderolls.com
 *
 */
public class LinkedListForeachLoop {

	public static void main(String[] args) {

		List<String> linkedList = new LinkedList<String>();

		linkedList.add("Mango");
		linkedList.add("Banana");
		linkedList.add("Grapes");
		linkedList.add("Watermelon");
		linkedList.add("Apple");
		linkedList.add("Avocado");

		System.out.println("Iterating through LinkedList using the foreach loop!\n");
				
		// iterate over linkedList using foreach loop
		for (String str: linkedList) {
			System.out.println("Object form the LinkedList is "+str);
		}
	}
}
```

Output:

```
Iterating through LinkedList using the foreach loop!

Object form the LinkedList is Mango
Object form the LinkedList is Banana
Object form the LinkedList is Grapes
Object form the LinkedList is Watermelon
Object form the LinkedList is Apple
Object form the LinkedList is Avocado
```

## 3. Iterate the LinkedList using while loop

Similar to for and foreach loop, we can also use the while loop to iterate over LinkedList.

I have given a java program below to iterate over LinkedList using the while loop. 

```java
/**
 * A java program to iterate over linkedList
 * using the while loop.
 * 
 * @author Gaurav Kukade at coderolls.com
 *
 */
public class LinkedListWhileLoop {

	public static void main(String[] args) {

		List<String> linkedList = new LinkedList<String>();

		linkedList.add("Mango");
		linkedList.add("Banana");
		linkedList.add("Grapes");
		linkedList.add("Watermelon");
		linkedList.add("Apple");
		linkedList.add("Avocado");

		System.out.println("Iterating through LinkedList using the while loop!\n");
		
		int len = linkedList.size();
		
		// iterate over linkedList using while loop
		int i =0;
		
		while(i<len) {
			
			// get String object from linkedList at index i
			String str = linkedList.get(i);
			
			System.out.println("Object form the LinkedList is "+str);
			
			//increment index after getting the object
			i++;
		}
	}
}
```

Output:

```
Iterating through LinkedList using the while loop!

Object form the LinkedList is Mango
Object form the LinkedList is Banana
Object form the LinkedList is Grapes
Object form the LinkedList is Watermelon
Object form the LinkedList is Apple
Object form the LinkedList is Avocado
```

## 4. Iterate the LinkedList using Iterator

Iterator is an interface in java. We can use an Iterator to iterate over a collection.

It is present in the `java.util` package.

If we want to iterate over an LinkedList using an iterator, we should invoke the iterator() method on the LinkedList object to get the iterator reference as given below

```java
// linkedList is an LinkedList object
Iterator iterator = linkedList.iterator();
```

Iterator has three important methods. They are as given below.

**`hasNext()`** - This method checks if the collection has any object available next, if found it will return true else false

**`next()`** - This method return the next object from the LinkedList .

**`remove()`** - This method removes the object from the LinkedList

I have given a java program below to iterate over an LinkedList using the iterator interface. We will be using the `hasNext()` and `next()` method in the program.

```java
import java.util.Iterator;
import java.util.LinkedList;
import java.util.List;

/**
 * A java program to iterate through LinkedList using Iterator interface.
 * 
 * @author coderolls.com
 *
 */
public class LinkedListIterator {

	public static void main(String[] args) {
		List<String> linkedList = new LinkedList<String>();

		linkedList.add("Mango");
		linkedList.add("Banana");
		linkedList.add("Grapes");
		linkedList.add("Watermelon");
		linkedList.add("Apple");
		linkedList.add("Avocado");
		System.out.println("Iterating through LinkedList using Iterator interface........\n");

		// getting iterator
		Iterator<String> iterator = linkedList.iterator();

		// hasNext() returns true only if object is available at next call
		while (iterator.hasNext()) {

			// next() returns obejct, we can cast it to reuqired type
			String str = iterator.next();
			System.out.println("Object form the LinkedList is " + str);
		}
	}
}
```

Output:

```
Iterating through LinkedList using Iterator interface........

Object form the LinkedList is Mango
Object form the LinkedList is Banana
Object form the LinkedList is Grapes
Object form the LinkedList is Watermelon
Object form the LinkedList is Apple
Object form the LinkedList is Avocado
```

**Note:** It is always recommended to use the  `Iterator.remove()` method for removing an element from a list while iterating on it. Also, we have `remove()` method in the LinkedList class, if you used the `LinkedList.remove()` method to remove an element while iterating over the list, you will get the `ConcurrentModificationException`.

## 5. Iterate the LinkedList using ListIterator

I will be wrting a seperate tutorial for the ListIterator method.

## 6. Iterate the LinkedList using Java 8 forEach() Method

In java 8, we got the new `forEach()` method to iterator over collections.

Inside the `forEach()` method, we can write the lambda expression for the Consumer functional interface.

I have given a sample java program below to iterate over the LinkedList using the `forEach()` method.

```java
import java.util.LinkedList;
import java.util.List;

/**
 * A java program to iterate over linkedList
 * using the java 8 foreach method.
 * 
 * @author coderolls.com
 */
public class LinkedListForEachMethod {

	public static void main(String[] args) {

		List<String> linkedList = new LinkedList<String>();

		linkedList.add("Mango");
		linkedList.add("Banana");
		linkedList.add("Grapes");
		linkedList.add("Watermelon");
		linkedList.add("Apple");
		linkedList.add("Avocado");

		System.out.println("Iterating through LinkedList using forEach method and lamda expression........\n");

		// add lambda expression in the foreach method
		linkedList.forEach(s -> System.out.println("Object form the LinkedList is " + s));
	}
}
```

Output:

```
Iterating through LinkedList using forEach method and lamda expression........

Object form the LinkedList is Mango
Object form the LinkedList is Banana
Object form the LinkedList is Grapes
Object form the LinkedList is Watermelon
Object form the LinkedList is Apple
Object form the LinkedList is Avocado
```



## Conclusion

We can iterate over ArrayList using the following ways.

1. Iterating the ArrayList using basic for loop

   ```java
   int len = linkedList.size();
   for (int i = 0; i < len; i++) {
       String str = linkedList.get(i);
       System.out.println("Object form the LinkedList at " + i + " is " + str);
   }
   ```

2. Iterating the ArrayList using Enhanced For Loop i.e. For-each loop

   ```java
   for (String str: linkedList) {
       System.out.println("Object form the LinkedList is "+str);
   }
   ```

3. Iterating the ArrayList using while loop

   ```java
   int len = linkedList.size();
   int i =0;
   
   while(i<len) {
       String str = linkedList.get(i);
       System.out.println("Object form the LinkedList is "+str);
       i++;
   }
   ```

4. Iterating the ArrayList using Iterator

   ```java
   Iterator<String> iterator = linkedList.iterator();
   
   while (iterator.hasNext()) {
       String str = iterator.next();
       System.out.println("Object form the LinkedList is " + str);
   }
   ```

5. Iterating the ArrayList using ListIterator- A Seperate Article Coming Soon

6. Iterating the ArrayList using Java 8 forEach() Method

   ```java
   linkedList.forEach(s -> System.out.println("Object form the LinkedList is " + s));
   ```

---

The example java programs given in the above tutorial can be found at [this GitHub Repository](https://github.com/coderolls/blogpost-coding-examples/tree/main/collections/LinkedList/iterate-linkedlist-in-java).

Let me know you thoughts or suggestions on the topic discussed above in comment section below.
