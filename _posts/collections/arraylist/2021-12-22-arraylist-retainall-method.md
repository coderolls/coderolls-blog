---  
layout: post  
title: "ArrayList retainAll() method"  
author: gaurav  
categories: [Collections, ArrayList]  
description: "Let's see the retainAll() method of the Arraylist class in Java."  
---

Let's see the `retainAll()` method of the [ArrayList class in Java](https://coderolls.com/arraylist-in-java/).
  
This method is used to retains all the elements in of the collection in the list.

## Introduction  
ArrayList is a widely used class to store and retrieve data in a collection framework.  

ArrayList is an ordered collection i.e. it maintains the insertion order of the elements. Also, it allows duplicate elements in the list.

Also, We have seen a few methods of the ArrayList class before like [`add()`](https://coderolls.com/add-element-in-arraylist/), [`addAll()`](http://https://coderolls.com/arraylist-addall-method-in-java/), [`remove()`](https://coderolls.com/remove-element-from-arraylist/), [`set()`](https://coderolls.com/change-element-in-arraylist/), [`iterate()`](https://coderolls.com/iterating-the-arraylist-in-java/), [`clear()`](https://coderolls.com/arraylist-clear-method-in-java/),  [`contains()`](https://coderolls.com/arraylist-contains-method), [`get()`](https://coderolls.com/arraylist-get-method) and [`removeRange()` ](https://coderolls.com/arraylist-removerange-method) method.  

Today we will see the `retainAll()` method.  
  

## ArrayList `retainAll(Collection c)` method  

The `retainAll()` method retains all the elements of the collections passed as a parameter in the list.

That means it will remove all elements from the list other than the ones which are present in the collection that is passed as parameter.

The method is signature is given below.

```java
public boolean retainAll(Collection<?> c)
```

As shown in the method signature, it accepts only one parameter i.e. `Collection c`. It is a collection of the objects that we have to retain in the list.

Also, the `retainAll()` method has a return type as a `boolean`. It returns `true` only if the list is changed as a result of the method call otherwise `false`. 

Let's see the java program for better understanding.

```java
import java.util.ArrayList;
import java.util.List;

/**
 * A java program to to eplain the retainAll() method of the Arraylist class.
 * 
 * @author Gaurav Kukade at coderolls.com
 *
 */
public class ArrayListRetainAllExample {

	public static void main(String[] args) {

		//create an empty arraylist of Integer to retain elements
		List<Integer> numbers1 = new ArrayList<Integer>();

		//add number to the list
		numbers1.add(4);
		numbers1.add(5);
		numbers1.add(6);
		
		//create an empty arraylist of Integer
		List<Integer> numbers2 = new ArrayList<Integer>();

		// add number to the list
		numbers2.add(1);
		numbers2.add(2);
		numbers2.add(3);
		numbers2.add(4);
		numbers2.add(5);
		numbers2.add(6);
		numbers2.add(7);
		numbers2.add(8);
		numbers2.add(9);

		System.out.println("Lists before the method call");
		System.out.println("numbers1: "+ numbers1);
		System.out.println("numbers2: "+ numbers2);
		
		//retain all the elements of numbers1 in the list numbers2
		numbers2.retainAll(numbers1);
		
		System.out.println("\nLists after the method call");
		System.out.println("numbers1: "+ numbers1);
		System.out.println("numbers2: "+ numbers2);	
	}
}
```  

Output:  

```
Lists before the method call
numbers1: [4, 5, 6]
numbers2: [1, 2, 3, 4, 5, 6, 7, 8, 9]

Lists after the method call
numbers1: [4, 5, 6]
numbers2: [4, 5, 6]
```
### Exceptions thrown by `retainAll()` Methods
This method may throw the `ClassCastException` and `NullPointerException`.

####  `ClassCastException` 
This method may throw the `ClassCastException`, if the class of an element of this list is incompatible with the specified collection. (optional)

#### `NullPointerException`
This method may throw the `NullPointerException`, if this list contains a null element and the specified collection does not permit null elements (optional) or if the specified collection is null.

The java example for the  `NullPointerException` is given below.

```java
import java.util.ArrayList;
import java.util.List;
/**
 * A java program to show the NullPointerException in retainAll() method
 * of the arrayList class.
 *  
 * @author gaurav
 *
 */
public class RetainAllNullPointerExceptionExample {

	public static void main(String[] args) {
		
		//create an empty arraylist of Integer to retain elements
		List<String> numbers1 = null;

		//create an empty arraylist of Integer
		List<Integer> numbers2 = new ArrayList<Integer>();

		// add number to the list
		numbers2.add(1);
		numbers2.add(2);
		numbers2.add(3);
		numbers2.add(4);

		System.out.println("Lists before the method call");
		System.out.println("numbers1: "+ numbers1);
		System.out.println("numbers2: "+ numbers2);
		
		//retain all the elements of numbers1 in the list numbers2
		numbers2.retainAll(numbers1);
		
		System.out.println("\nLists after the method call");
		System.out.println("numbers1: "+ numbers1);
		System.out.println("numbers2: "+ numbers2);	
	}
}
```

Output:
```
Lists before the method call
numbers1: null
numbers2: [1, 2, 3, 4]
Exception in thread "main" java.lang.NullPointerException
	at java.util.Objects.requireNonNull(Objects.java:203)
	at java.util.ArrayList.retainAll(ArrayList.java:714)
	at com.gaurav.ExProject.ArrayList.RetainAllClassCastExceptionExample.main(RetainAllClassCastExceptionExample.java:27)
```
## Conclusion  

The `retainAll(Collection c)` method retains all the elements of the collection passed as a parameter in the list.

```java
public boolean retainAll(Collection<?> c)
```

This method return `true` if the list is changed otherwise `false`.

---

The example java program used in the above article can be found at [this GitHub repository](https://github.com/coderolls/blogpost-coding-examples/tree/main/collections/arraylist/arraylist-retainall-method).  

Please write your thoughts in the comment section below.
