---
layout: post
title: "How To Remove An Element From An ArrayList?"
author: gaurav
categories: [Collections, ArrayList]
description: "In this article, we will see how to remove an element from an ArrayList."
---
In this article, we will see how to remove an element from an [ArrayList In Java](https://coderolls.com/arraylist-in-java/).
## Introduction

We have seen [how we can add an element to an ArrayList](http://coderolls.com/add-element-in-arraylist/) and  [how we can change the elements of an ArrayList](https://coderolls.com/change-element-in-arraylist/), now we will see how we can remove an element from an ArrayList.

To remove an element from an ArrayList, we use the `remove()` method.

Using the`remove(Object o)` method, we can remove the specified object from an ArrayList.

Using the `remove(int index)` method, we can remove the object at the specified index from an ArrayList.

Let's see both the method one by one.

## 1. Remove an element from an ArrayList using the `remove(Object o)` method

`remove(Object o)` method removes the first occurrences  of the specified object from the ArrayList.

If the specified object `o` is not present in the ArrayList, the ArrayList remains unchanged.

The method signature is as `public boolean remove(Object o)`

The `remove(Object o)` method has a return type as a `boolean`. It returns `true` if it found an occurrence of the specified object and if it removes. Otherwise, it returns `false`.

We will see a java program to remove an element from the ArrayList using the `remove(Object o)` method.

```java
import java.util.ArrayList;

/**
 * A Java program to remove an element from ArrayList
 * using the remove(Object o) method.
 * 
 * @author Gaurav Kuakde at coderolls.com
 *
 */
public class ArrayListRemoveExample {

	public static void main(String[] args) {
		
		ArrayList<String> arrayList = new ArrayList<String>();
		
		//adding elements to the arrayList using normal add method
		arrayList.add("Red");
		arrayList.add("Green");
		arrayList.add("Pink");
		
		System.out.println("ArrayList before removing an element"+ arrayList); // ArrayList before removing an element[Red, Green, Pink]
		
		//Remove "Pink" from the arrayList
		arrayList.remove("Pink");
		
		System.out.println("ArrayList after removing an element"+ arrayList);// ArrayList after removing an element[Red, Green]
	}
}
```
Output:
```
ArrayList before removing an element[Red, Green, Pink]
ArrayList after removing an element[Red, Green]
```
## 2. Remove an element from an ArrayList using the `remove(int index)` method

`remove(int index)` remove an element at the specified position from the ArrayList.

The method signature is as `public E remove(int index)`

Once we remove an element from the ArrayList using the `remove(int index)` method, the remaining elements from after the specified index get shifted left.

The return type is a `E`. It returns the element that was removed from the list.

We will see a java program to remove an element from the ArrayList by passing its index as an argument to `remove(int index)` method.

```java
import java.util.ArrayList;

/**
 * A Java program to remove an element from ArrayList
 * using the remove(int index) method.
 * 
 * @author Gaurav Kukade at coderolls.com
 *
 */
public class ArrayListRemoveExample2 {

	public static void main(String[] args) {
		
		ArrayList<String> arrayList = new ArrayList<String>();
		
		//adding elements to the arrayList using normal add method
		arrayList.add("Apple");
		arrayList.add("Orange");
		arrayList.add("Guava");
		arrayList.add("Banana");
		
		System.out.println("ArrayList before removing an element"+ arrayList);
		// ArrayList before removing an element[Apple, Orange, Guava, Banana]
		
		//Remove the element at the specified index i.e. 2
		//Remove "Guava" from the arrayList
		arrayList.remove(2);
		
		System.out.println("ArrayList after removing an element"+ arrayList);
		// ArrayList after removing an element[Apple, Orange, Banana]
	}
}
```
Output:
```
ArrayList before removing an element[Apple, Orange, Guava, Banana]
ArrayList after removing an element[Apple, Orange, Banana]
```

## Conclusion

We can remove an element from the ArrayList in two ways.

1. `remove(Object o)` - we can remove the specified object from the ArrayList
2. `remove(int index)` - We can remove an element at the position (index) specified

If you know any other way, please comment below.

### Related articles

- [ArrayList In Java](https://coderolls.com/arraylist-in-java/)
- [How To Add An Element To ArrayList In Java?](https://coderolls.com/add-element-in-arraylist/)
- [How To Change An Element In ArrayList](https://coderolls.com/change-element-in-arraylist/)
