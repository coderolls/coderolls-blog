---
layout: post
title: "ArrayList clear() method in Java"
author: gaurav
categories: [Collections, ArrayList]
toc: true
description: "In this article, we will see clear() method of ArrayList in Java. This method is used to remove all the elements of the current ArrayList."
---

In this article, we will see the `clear()` method of [ArrayList in Java](https://coderolls.com/arraylist-in-java/). This method is used to remove all the elements of the ArrayList.

## Introduction

We use [ArrayList](https://coderolls.com/arraylist-in-java/) in day-to-day Java programming. ArrayList is an ordered collection and it allows duplicate elements.
 
 We have seen a few methods of the ArrayList class before like [`add()`](https://coderolls.com/add-element-in-arraylist/), [`addAll()`](http://127.0.0.1:4000/arraylist-addall-method-in-java/), [`remove()`](https://coderolls.com/remove-element-from-arraylist/), [`set()`](https://coderolls.com/change-element-in-arraylist/) and [`iterate()`](http://coderolls.com/iterating-the-arraylist-in-java/)

Today we will see the `clear()` method of the ArrayList class in java.

## ArrayList `clear()` method in java

It has a method signature as given below.
```java
public void clear()
```

When we invoke the clear() method on an ArrayList, it removes all of the elements from this list. 

So, the list will be empty after the successful invocation of the clear method on the list.

It has a return type as a `void`. It means this method does not return anything.

Also, it does not accept any parameter.

Let's see an example java program that uses the `clear()` method to remove all the elements of the list.

```java
import java.util.ArrayList;
import java.util.List;

/**
 * A java program to remove all the elements 
 * of ArrayList using the clear() method.
 * 
 * @author Gaurav Kukade at coderolls.com
 *
 */
public class ArrayListClearMethodExample {

	public static void main(String[] args) {
		
		// create an arraylist cities
		List<String> cities = new ArrayList<String>();
		
		// add string objects in 'cities'
		cities.add("New York City");
		cities.add("Los Angeles");
		cities.add("Mountain View");
		cities.add("Austin");
		cities.add("Atlanta");
		
		// printing the cities
		System.out.println("Before invoking the clear() method");
		System.out.println("Cities: "+ cities); //print the arraylist with elements
		System.out.println("cities size: "+ cities.size());
		
		//invoke the clear() method on arraylist
		cities.clear();
		System.out.println("\nAfter invoking the clear() method");
		System.out.println("Cities: "+ cities); // empty arraylist
		System.out.println("cities size: "+ cities.size());
	}
}
```
Output:
```
Before invoking the clear() method
Cities: [New York City, Los Angeles, Mountain View, Austin, Atlanta]
cities size: 5

After invoking the clear() method
Cities: []
cities size: 0
```
### Explanation:

1. I have created an ArrayList object `cities`
2. I have added a few String objects to the `cities`
3. I have printed the `cities` to see the String objects present in it. Also, I have printed the size of the `cities`. We can see its size is `5` since we have added the 5 String objects in it.
4. Invoke the `clear()` method on the `cities` to remove all its elements.
5. When we print the cities ArrayList again, we can not see any String objects present in it. Also, the size of `cities` is `0`, so we can say the `clear()` method made it empty.

## Conclusion

When we invoke the `clear()` method on the ArrayList, it removes all the elements from this Arraylist and makes it empty.
```
arrayList.clear()
```

---

The example java program used in the above article can be found at [this GitHub repository](https://github.com/coderolls/blogpost-coding-examples/tree/main/collections/arraylist/arraylist-clear-method-in-java).

If you know anything else about the `clear()` method of the [ArrayList class](https://coderolls.com/arraylist-in-java/), kindly write it in the comment section below.
