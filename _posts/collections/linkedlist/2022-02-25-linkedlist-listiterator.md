---
layout: post  
title: "LinkedList listIterator() method in Java"  
author: gaurav  
categories: [Collections, LinkedList]  
toc: true
description: "In this short tutorial, we will see the listIterator() method of the Arraylist class in Java."  
---

In this tutorial, we will see the `listIterator()` method of the  [LinkedList class in Java](https://coderolls.com/linkedList-in-java/). 

## Introduction  

LinkedList class is present in the `java.util` package.

[LinkedList](https:/coderolls.com/linkedlist-in-java/) internally uses a doubly linkedlist for storing the variables. That's why LinkedList is preferred when our frequent operation is insertion and deletion.

Let's check the `listIterator(int index)` method in LinkedList.

## LinkedList `listIterator(int index)` method

This listIterator method returns a fail-fast ListIterator object instance over the elements of this linkedList (in proper sequence), starting from the position specified i.e `index`.

The specified index indicates the first element that would be returned by an initial call to [`next`](https://docs.oracle.com/javase/8/docs/api/java/util/ListIterator.html#next--). An initial call to [`previous`](https://docs.oracle.com/javase/8/docs/api/java/util/ListIterator.html#previous--) would return the element with the specified index minus one.

The method signature is given below.

```java
public ListIterator<E> listIterator(int index)
```

This method accepts only one parameter i.e `index`of type `int`

- **`index`**- index of the first element to be returned from the list iterator (by a call to [`next`](https://docs.oracle.com/javase/8/docs/api/java/util/ListIterator.html#next--))

Let's see an example java program for the `listIterator()` method of the LinkedList.

```java
import java.util.LinkedList;
import java.util.ListIterator;
/**
 * An example java program about the listIterator(int index)
 * method of the linkedList.
 * 
 * @author coderolls.com
 */
public class LinkedListListIteratorExample2 {

	public static void main(String[] args) {
		
		LinkedList<String> states = new LinkedList<>();

		// add state in the linkedList
		states.add("California");
		states.add("Texas");
		states.add("Montana");
		states.add("Arizona");
		states.add("Florida");
		states.add("Michigan");
		states.add("New Jersey");
		states.add("Washington");
		states.add("Ohio");
		
        //given index 3, iterator start from element with index 3
		ListIterator<String> itr = states.listIterator(3);
		
		while(itr.hasNext()) {
			String state = itr.next();
			System.out.println("The state :"+ state);
		}
	}
}
```

Output:

```
Iterating the list from index 3

The state :Arizona
The state :Florida
The state :Michigan
The state :New Jersey
The state :Washington
The state :Ohio
```

### Exception

If the entered index is not within the range of LinkedList, we will get `IndexOutOfBoundsException`

I have given a java program below which show the case for the

```java
import java.util.LinkedList;
import java.util.ListIterator;
/**
 * An example java program about the listIterator()
 * method of the linkedList.
 * 
 * @author coderolls.com
 */
public class LinkedListListIteratorException {

	public static void main(String[] args) {
		
		LinkedList<String> states = new LinkedList<>();

		// add state in the linkedList
		states.add("California");
		states.add("Texas");
		states.add("Montana");
		states.add("Arizona");
		states.add("Florida");
		states.add("Michigan");
		states.add("New Jersey");
		states.add("Washington");
		states.add("Ohio");
		
        //given index 120, it will  throw IndexOutOfBoundsException
		ListIterator<String> itr = states.listIterator(120);
		
		while(itr.hasNext()) {
			String state = itr.next();
			System.out.println("The state :"+ state);
		}
	}
}
```

Output:

```
Exception in thread "main" java.lang.IndexOutOfBoundsException: Index: 120, Size: 9
	at java.util.LinkedList.checkPositionIndex(LinkedList.java:560)
	at java.util.LinkedList.listIterator(LinkedList.java:867)
	at com.gaurav.ExProject.LinkedList.LinkedListListIteratorException.main(LinkedListListIteratorException.java:29)
```



## Conclusion

This method  `listIterator(int index)` returns the iterator over elements of the LinkedList, starting from the position specified. i.e `index`

Both metho returns the fail-fast iterator. 

```java
public ListIterator<E> listIterator(int index)
```

---

The example java program used in the above article can be found at [this GitHub repository](https://github.com/coderolls/blogpost-coding-examples/tree/main/collections/linkedlist/linkedlist-listiterator).  

Please write your thoughts in the comment section below.