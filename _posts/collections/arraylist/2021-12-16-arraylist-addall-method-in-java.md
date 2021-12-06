---
layout: post
title: "ArrayList addAll() method in Java"
author: gaurav
categories: [Collections, ArrayList]
description: "In this article, we will see how to add another collections elements in the ArrayList. Also, we will see how to add another collections elements from any particular index in ArrayList."
---
In this article, we will see how to add another collections elements in the ArrayList. Also, we will see how to add another collections elements from any particular index in ArrayList.

## Introduction

 [ArrayList](https://coderolls.com/arraylist-in-java/) is a widely used class from the Collection framework in Java. ArrayList used a dynamic array internally to store the elements.

When we add objects to [ArrayList](https://coderolls.com/arraylist-in-java/), it maintains the insertion order. So, ArrayList is an ordered collection.

Also, duplicate objects are allowed in ArrayList.

Sometimes we need to add the elements of another collection to the ArrayList. ArrayList call provides the `addAll()` method to add the elements of the collection.

The `addAll()` method has two overload type 
1. `addAll(Collection c)`
2. `addAll(int index, Collection c)`

The first ArrayList method adds the elements of the specified collection to the end of the ArrayList.

The second ArrayList method adds the elements of the specified collection at the specified index.

Let's see both the method one by one.

## 1. Add a collection in ArrayList using `addAll(Collection c)` method

The `addAll(Collection c)` method adds all the elements of the specified collection to the end of the ArrayList.

The method signature for this method is as given below.
```java
public boolean addAll(Collection c)
``` 
The method signature shows that this method accepts one parameter of type Collection.

- **`c` : -** any collection obejct

It has a return type as `boolean` i.e. this method returns `true` if the ArrayList as a result of the call (if elements from other collections are added to the ArrayList), otherwise it returns false.

This method may throw [NullPointerException](https://docs.oracle.com/javase/8/docs/api/java/lang/NullPointerException.html "class in java.lang") if the specified collection is empty

I have given a java program to add elements of a collection to ArrayList using the `addAll(Collection c)` method.

```java
import java.util.ArrayList;
import java.util.List;

/**
 * A Java program to add all elements of the specified collection
 * to the end of the ArrayList
 * 
 * @author Gaurav Kukade at coderolls.com
 *
 */
public class ArrayListAddAllExample {

	public static void main(String[] args) {
		
		// ArrayList contains actresses
		List<String> actresses1 = new ArrayList<String>();
		
		actresses1.add("Natalie Portman");
		actresses1.add("Abigail Anderson");
		actresses1.add("Jennifer Lawrence");
		
		System.out.println("Actresses collection 1: \n"+ actresses1 );
		
		// ArrayList contains actresses
		List<String> actresses2 = new ArrayList<String>();
		
		
		
		actresses2.add("Angelina Jolie");
		actresses2.add("Scarlett Johansson");
		
		System.out.println("Actresses collection 2: \n"+ actresses2);
		
		// Add actresses2 collections all elements to actresses1 collection using addAll()method
		actresses1.addAll(actresses2);
		
		System.out.println("Actresses : \n"+ actresses1);
	}
}
```
Output:
```
Actresses collection 1: 
[Natalie Portman, Abigail Anderson, Jennifer Lawrence]
Actresses collection 2: 
[Angelina Jolie, Scarlett Johansson]
Actresses : 
[Natalie Portman, Abigail Anderson, Jennifer Lawrence, Angelina Jolie, Scarlett Johansson]
```

## 2. Add a collection in ArrayList at particular index using `addAll(int index, Collection c)` method

The `addAll(int index, Collection c)` method adds all the elements of the specified collection to the ArrayList from the specified `index`.

The method signature for this method is as given below.
```java
public boolean addAll(int index, Collection c)
``` 

This method accepts two parameters, 
- **`c`  : -**  a collection `c`  whose elements need to be added to the arraylist
- **`index` : -** an`index` of type  `int` , it specifies the position in ArrayList from collection `c`'s elements will be added.

It returns `true` if the ArrayList got changed, otherwise `false`

This method may throw the following exceptipons
- [IndexOutOfBoundsException](https://docs.oracle.com/javase/8/docs/api/java/lang/IndexOutOfBoundsException.html "class in java.lang")  - if the index is out of range (index < 0 || index > arraList.size())
-  [NullPointerException](https://docs.oracle.com/javase/8/docs/api/java/lang/NullPointerException.html "class in java.lang"), if the specified collection is empty

I have given a java program to add elements of a collection to ArrayList at a particular index using the `addAll(Collection c)` method.
```java
import java.util.ArrayList;
import java.util.List;

/**
 * A Java program to add all elements of the specified collection
 * to the ArrayList from a particular index 
 * 
 * @author Gaurav Kukade at coderolls.com
 *
 */
public class ArrayListAddAllExample2 {

	public static void main(String[] args) {
		
		// ArrayList containing entrepreneurs
		List<String> entrepreneurs1 = new ArrayList<String>();
		
		entrepreneurs1.add("Bill Gates");
		entrepreneurs1.add("Steve Jobs");
		entrepreneurs1.add("Jeff Bezos");
		entrepreneurs1.add("Richard Branson");
		entrepreneurs1.add("Mark Cuban");
		
		System.out.println("Entrepreneurs collection 1: \n"+ entrepreneurs1 );
		
		// ArrayList containing entrepreneurs
		List<String> entrepreneurs2 = new ArrayList<String>();
		
		entrepreneurs2.add("Mark Zuckerberg");
		entrepreneurs2.add("Larry Page");
		entrepreneurs2.add("Larry Ellison");
		
		System.out.println("Entrepreneurs collection 2: \n"+ entrepreneurs2);
		
		// Add entrepreneurs2 collections all elements to entrepreneurs1 collection
		// starting from index 2
		entrepreneurs1.addAll(2, entrepreneurs2);
		
		System.out.println("Entrepreneurs : \n"+ entrepreneurs1);
	}
}
```
Output:
```
Entrepreneurs collection 1: 
[Bill Gates, Steve Jobs, Jeff Bezos, Richard Branson, Mark Cuban]
Entrepreneurs collection 2: 
[Mark Zuckerberg, Larry Page, Larry Ellison]
Entrepreneurs : 
[Bill Gates, Steve Jobs, Mark Zuckerberg, Larry Page, Larry Ellison, Jeff Bezos, Richard Branson, Mark Cuban]
```

## Conclusion

We can add elements of a collection to the ArrayList using the `addAll()` method in two ways.

1. `addAll(Collection c)` - it adds elements of the specified collection to the end of ArrayList
2. `addAll(int index, Collection c)` - it adds elements of the specified collection to the ArrayList from the specified position (index)

Please write your thoughts in the commend section below.




