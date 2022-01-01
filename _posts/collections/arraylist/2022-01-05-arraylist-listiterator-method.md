---

layout: post  
title: "ArrayList listIterator() method in Java"  
author: gaurav  
categories: [Collections, ArrayList]  

description: "In this short tutorial, we will see the listIterator() method of the Arraylist class in Java."  
---

In this tutorial, we will see the `listIterator()` method of the  [ArrayList class in Java](https://coderolls.com/arraylist-in-java/). 

## Introduction  

ArrayList is a widely used class to store and retrieve data in a collection framework.

In previous articles, we have various methods to perform operations on the ArrayList.

A few methods of ArrayList class are [`add()`](https://coderolls.com/add-element-in-arraylist/), [`addAll()`](http://https://coderolls.com/arraylist-addall-method-in-java/), [`remove()`](https://coderolls.com/remove-element-from-arraylist/), [`set()`](https://coderolls.com/change-element-in-arraylist/), [`iterate()`](https://coderolls.com/iterating-the-arraylist-in-java/), [`clear()`](https://coderolls.com/arraylist-clear-method-in-java/),  [`contains()`](https://coderolls.com/arraylist-contains-method), [`get()`](https://coderolls.com/arraylist-get-method), [`removeRange()`](https://coderolls.com/arraylist-removerange-method), [`retainAll()`](https://coderolls.com/arraylist-retainall-method),  [`trimToSize()`](https://coderolls.com/arraylist-trimtosize-method), [`indexOf()`](https://coderolls.com/arraylist-indexof-method) and  [`lastIndexOf()`](https://coderolls.com/arraylist-lastindexof-method),  [`removeIf()`](https://coderolls.com/arraylist-removeIf-method),   [`removeAll()`](https://coderolls.com/arraylist-removeall-method), [`isEmpty`](https://coderolls.com/arraylist-isempty-method) and [`ensureCapacity()`](https://coderolls.com/arraylist-ensurecapacity-method) method. 

Today we will see the `listIterator()` method. This method provides the fail-fast iterator over thelements of the list.

There are two variations of the `listIterator()` method.

1. `listIterator()` 
2. `listIterator(int index)`

## 1. ArrayList `listIterator()` method  

The `listIterator()` method returns a list iterator over the elements in this list (in proper sequence).

The returned list iterator is [*fail-fast*](https://docs.oracle.com/javase/8/docs/api/java/util/ArrayList.html#fail-fast). i.e When multiple threads try to uodate the list at a time, it will throw the `ConcurrentModificationExaception`.

The method signature is as given below.

```java
public ListIterator<E> listIterator()
```

This method do not accept any parameter.

It returns a `ListIterator` object instance. It will be a fail-fast iterator.

Let's see an example java program for the `listIterator()` method of the ArrayList.

```java
import java.util.ArrayList;
import java.util.ListIterator;
/**
 * An example java program about the listIterator()
 * method of the arrayList.
 * 
 * @author coderolls.com
 */
public class ArrayListListIteratorExample {

	public static void main(String[] args) {
		
		ArrayList<String> states = new ArrayList<>();

		// add state in the arraylist
		states.add("California");
		states.add("Texas");
		states.add("Montana");
		states.add("Arizona");
		states.add("Florida");
		states.add("Michigan");
		states.add("New Jersey");
		states.add("Washington");
		states.add("Ohio");
		
		ListIterator<String> itr = states.listIterator();
		
		while(itr.hasNext()) {
			String state = itr.next();
			System.out.println("The state :"+ state);
		}
	}
}
```

Output:  

```
The state :California
The state :Texas
The state :Montana
The state :Arizona
The state :Florida
The state :Michigan
The state :New Jersey
The state :Washington
The state :Ohio
```

## 2. ArrayList `listIterator(int index)` method

This listIterator method returns a fail-fast ListIterator object instance over the elements of this arraylist (in proper sequence), starting from the position specified i.e `index`.

The specified index indicates the first element that would be returned by an initial call to [`next`](https://docs.oracle.com/javase/8/docs/api/java/util/ListIterator.html#next--). An initial call to [`previous`](https://docs.oracle.com/javase/8/docs/api/java/util/ListIterator.html#previous--) would return the element with the specified index minus one.

The method signature is given below.

```java
public ListIterator<E> listIterator(int index)
```

This method accepts only one parameter i.e `index`of type `int`

- **`index`**- index of the first element to be returned from the list iterator (by a call to [`next`](https://docs.oracle.com/javase/8/docs/api/java/util/ListIterator.html#next--))

Let's see an example java program for the `listIterator()` method of the ArrayList.

```java
import java.util.ArrayList;
import java.util.ListIterator;
/**
 * An example java program about the listIterator()
 * method of the arrayList.
 * 
 * @author coderolls.com
 */
public class ArrayListListIteratorExample2 {

	public static void main(String[] args) {
		
		ArrayList<String> states = new ArrayList<>();

		// add state in the arraylist
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
The state :Arizona
The state :Florida
The state :Michigan
The state :New Jersey
The state :Washington
The state :Ohio
```

### Exception

If the entered index is not within the range of ArrayList, we will get `IndexOutOfBoundsException`

I have given a java program below which show the case for the

```java
import java.util.ArrayList;
import java.util.ListIterator;
/**
 * An example java program about the listIterator()
 * method of the arrayList.
 * 
 * @author coderolls.com
 */
public class ArrayListListIteratorException {

	public static void main(String[] args) {
		
		ArrayList<String> states = new ArrayList<>();

		// add state in the arraylist
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
Exception in thread "main" java.lang.IndexOutOfBoundsException: Index: 120
	at java.util.ArrayList.listIterator(ArrayList.java:816)
	at com.gaurav.ExProject.ArrayList.ArrayListListIteratorException.main(ArrayListListIteratorException.java:27)
```



## Conclusion

We have seen a `listIterator()` method of the ArrayList class. This method returns an iterator over the elments of the ArrayList in proper sequence.

```java
public ListIterator<E> listIterator()
```

The overloaded version of this method  `listIterator(int index)` returns the iterator over elements of the ArrayList, starting from the position specified. i.e `index`

Both metho returns the fail-fast iterator. 

```java
public ListIterator<E> listIterator(int index)
```

---

The example java program used in the above article can be found at [this GitHub repository](https://github.com/coderolls/blogpost-coding-examples/tree/main/collections/arraylist/arraylist-listiterator-method).  

Please write your thoughts in the comment section below.