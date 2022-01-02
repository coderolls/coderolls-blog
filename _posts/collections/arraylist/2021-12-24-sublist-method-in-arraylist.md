---  
layout: post  
title: "subList() method of ArrayList class in java"  
author: gaurav  
categories: [Collections, ArrayList]
toc: true  
description: "In this tutorial, we will see the  subListt() method of the Arraylist class in Java."  
---
In this tutorial, we will see the `subList()` method of the  [ArrayList class in Java](https://coderolls.com/arraylist-in-java/). This method returns a view of the specified range within the list.

## Introduction  
ArrayList is a widely used class to store and retrieve data in a collection framework.  

ArrayList is an ordered collection i.e. it maintains the insertion order of the elements. Also, it allows duplicate elements in the list.

Also, we have seen a few methods of the ArrayList class before like [`add()`](https://coderolls.com/add-element-in-arraylist/), [`addAll()`](http://https://coderolls.com/arraylist-addall-method-in-java/), [`remove()`](https://coderolls.com/remove-element-from-arraylist/), [`set()`](https://coderolls.com/change-element-in-arraylist/), [`iterate()`](https://coderolls.com/iterating-the-arraylist-in-java/), [`clear()`](https://coderolls.com/arraylist-clear-method-in-java/),  [`contains()`](https://coderolls.com/arraylist-contains-method), [`get()`](https://coderolls.com/arraylist-get-method), [`removeRange()`](https://coderolls.com/arraylist-removerange-method) and [`retainAll()`](https://coderolls.com/arraylist-retainall-method) method. 

Today we will see the `subList(int fromIndex, int toIndex)` method.  
  

## ArrayList `subList(int fromIndex, int toIndex)` method  

The `subList(int fromIndex, int toIndex)` method returns the view of the portion of this list between the specified **`fromIndex`, inclusive and `toIndex` , exclusive.** 

The method is signature is given below.

```java
public List<E> subList(int fromIndex, int toIndex)
```
As shown in the method signature, the subList() method accepts two parameters of type `int` i.e `fromIndex` and `toIndex`

{:class="table table-bordered"}
|Parameter|Description|
|:-------|:----|
|`fromIndex`|low endpoint (inclusive) of the subList|
|`toIndex`|high endpoint (exclusive) of the subList|


Let's see the java program for better understanding.

```java
import java.util.ArrayList;
import java.util.List;

/**
 * A java program to explain the subList() method of the ArrayList class in Java
 * 
 * @author Gaurav Kukade at coderolls.com
 *
 */
public class ArrayListSubListExample {

	public static void main(String[] args) {

		// create an empty arraylist object 'states'
		List<String> states = new ArrayList<String>();

		// add state in the arraylist
		states.add("California");
		states.add("Texas");
		states.add("Florida");
		states.add("New Jersey");
		states.add("Washington");
		
		System.out.println("The states list: \n"+ states);
		
		// sublist the states list from 1 to 3 index
		List<String> statesSubList = states.subList(1, 3);
		
		System.out.println("\nThe states sublist from index 1 (inclusive) to 3 (exclusive): \n"+ statesSubList);
	}
}
```  

Output:  
```
The states list: 
[California, Texas, Florida, New Jersey, Washington]

The states sublist from index 1 (inclusive) to 3 (exclusive): 
[Texas, Florida]
```
### Exceptions thrown by `subList()` Methods
This method may throw the `ClassCastException` and `NullPointerException`.

####  `IndexOutOfBoundsException` 
This method may throw the `ClassCastException`, if an endpoint index value is out of range. i.e. if `fromIndex` is less than `0` (`fromIndex < 0 `) or `toIndex` is greater than the size of the ArrayList (`toIndex > size`).

The java example for the  `IndexOutOfBoundsException` is given below.

```java
/**
 * A java program to explain the subList() methods 
 * IndexOutOfBoundsException exception case.
 * 
 * @author Gaurav Kukade at coderolls.com
 */
public class SubListMethodExceptionExample1 {

	public static void main(String[] args) {
		// create an empty arraylist object 'states'
		List<String> states = new ArrayList<String>();

		// add state in the arraylist
		states.add("California");
		states.add("Texas");
		states.add("Florida");
		states.add("New Jersey");
		states.add("Washington");
		
		System.out.println("The states list: \n"+ states);
		
		// will throw IndexOutOfBoundsException
		List<String> statesSubList = states.subList(1, 7); // will throw exception
		
		System.out.println("\nThe states sublist from index 1 (inclusive) to 3 (exclusive): \n"+ statesSubList);
	}
}
```

Output:
```
The states list: 
[California, Texas, Florida, New Jersey, Washington]
Exception in thread "main" java.lang.IndexOutOfBoundsException: toIndex = 7
	at java.util.ArrayList.subListRangeCheck(ArrayList.java:1012)
	at java.util.ArrayList.subList(ArrayList.java:1004)
	at com.gaurav.ExProject.ArrayList.SubListMethodExceptionExample1.main(SubListMethodExceptionExample1.java:22)
```

#### `IllegalArgumentException`
This method may throw the `NullPointerException`, if the endpoint indices are out of order. i.e. if the `fromIndex` is greater than `toIndex`

The java example for the  `IllegalArgumentException` is given below.

```java
/**
 * A java program to explain the subList() methods 
 * IllegalArgumentException exception case.
 * 
 * @author Gaurav Kukade at coderolls.com
 */
public class SubListMethodExceptionExample2 {

	public static void main(String[] args) {
		// create an empty arraylist object 'states'
		List<String> states = new ArrayList<String>();

		// add state in the arraylist
		states.add("California");
		states.add("Texas");
		states.add("Florida");
		states.add("New Jersey");
		states.add("Washington");
		
		System.out.println("The states list: \n"+ states);
		
		// will throw IllegalArgumentException
		List<String> statesSubList = states.subList(3, 1); 
		
		System.out.println("\nThe states sublist from index 1 (inclusive) to 3 (exclusive): \n"+ statesSubList);
	}
}
```

Output:
```
The states list: 
[California, Texas, Florida, New Jersey, Washington]
Exception in thread "main" java.lang.IllegalArgumentException: fromIndex(3) > toIndex(1)
	at java.util.ArrayList.subListRangeCheck(ArrayList.java:1014)
	at java.util.ArrayList.subList(ArrayList.java:1004)
	at com.gaurav.ExProject.ArrayList.SubListMethodExceptionExample2.main(SubListMethodExceptionExample2.java:28)
```
## Conclusion  

```java
public List<E> subList(int fromIndex, int toIndex)
```
The `subList(int fromIndex, int toIndex)` method returns the view of the portion of this list between the specified **`fromIndex`, inclusive and `toIndex` , exclusive.** 


---

The example java program used in the above article can be found at [this GitHub repository](https://github.com/coderolls/blogpost-coding-examples/tree/main/collections/arraylist/sublist-method-in-arraylist).  

Please write your thoughts in the comment section below.
