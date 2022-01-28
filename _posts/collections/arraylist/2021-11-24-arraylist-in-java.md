---
layout: post
title: "ArrayList In Java"
author: gaurav
categories: [Collections, ArrayList]
toc: true
description: "In this article, we will see ArrayList in Java. How to create an ArrayList? Its various type of constructors for creating an ArrayList object. Also, some important features with an example."
---
In this article, we will see ArrayList in Java. How to create an ArrayList? Its various type of constructors for creating an ArrayList object. Also, some important features with an example.

## Introduction

ArrayList is a class in Collections Framework. It is present in `java.util` package.

The **ArrayList internally uses a dynamic array** for storing the elements. So ArrayList is more flexible than the array.

The `ArrayList` class inherits the `AbstractList `class and it implements the `List` Interface.

Unlike Array, we need not fix the length of ArrayList at the time of initialization. As we add or remove elements from the ArrayList, it can grow and shrink dynamically.

The load factor for the ArrayList is 0.75F.

The default initial capacity is 10. 

Load factor = 0.75 * 10 = 7

So when we try to add the 7th element to the ArrayList, it will create a new array double of the size of the old array i.e. 20 and copy the old array in the new array and then add the element in a new array.

## Constructors in the ArrayList

To create an ArrayList, we need to create an object of the ArrayList class. To create an object ArrayList provides three types of constructor

1. `ArrayList()`

2. `ArrayList(Collection<? extends E> c)`

3. `ArrayList(int initialCapacity)`

Let's see all one by one

### 1. ArrayList()

This is a simple constructor to create an ArrayList object with a default capacity of ten (10).

```java
ArrayList<String> arrayList = new ArrayList<String>();
```

Above creating an empty array list object. The default initial capacity is 10.

### 2. ArrayList(Collection<? extends E> c)

This constructor constructs a list containing the elements of the specified collection, in the order they are returned by the collection's iterator.

```java

ArrayList<String> anotherCollection = new ArrayList<String>();
anotherCollection.add("example");

// 2nd constructor exaqmple is the below line of code
ArrayList<String> arrayList = new ArrayList<String>(anotherCollection);
```

### 3. ArrayList(int initialCapacity)

This constructor constructs an empty list with the specified initial capacity.

```java
ArrayList<String> arrayList = new ArrayList<String>(20);
```

Above, I am creating an empty array list object with it's initial capacity as 20.

**Note:** 
```java
ArrayList<String> arrayList = new ArrayList<String>(20);
```
In the above code the `<String>` represents Generics and I am creating an `arrayList` object which will be storing String type of objects only. It will give us a compile-time error if we try to add any other type of object the `arrayList`.

By default, Collections are heterogeneous i.e. they can save all types of objects in one collection. By using Generics I am making it homogeneous i.e. it will store only specified types of objects in that particular collection.


## Methods in ArrayList

{:class="table table-bordered"}
|Method | Description |
|:------| :---------- |
|[`add(E e)`](https://coderolls.com/add-element-in-arraylist/)|This method adds an element to the end of the list.|
|[`add(int index, E element)`](https://coderolls.com/add-element-in-arraylist/)|This method adds an element to the list at the specifed `index`.|
|[`addAll(Collection c)`](https://coderolls.com/arraylist-addall-method-in-java/)|This method adds the elements of the specified collection to the end of the ArrayList.|
|[`addAll(int index, Collection c)`](https://coderolls.com/arraylist-addall-method-in-java/)|This method adds the elements of the specified collection at the specified index `index`.|
|[`get(int index)`](https://coderolls.com/arraylist-get-method/)|This method is used to get the ArrayList element by it’s index `index`.|
|[`set(int index, E element)`](https://coderolls.com/change-element-in-arraylist/)|This method sets the sepecified element at the specifed `index`.|
|[`remove(Object o)`](https://coderolls.com/remove-element-from-arraylist/)|This method removes the specified object from the ArrayList.|
|[`remove(int index)`](https://coderolls.com/remove-element-from-arraylist/)|This method removes the object at specified index from the ArrayList.|
|[`removeIf(Predicate filter)`](http://coderolls.com/arraylist-removeif-method/)|This method removes all of the elements of the ArrayList that satisfy the given predicate.|
|[`removeAll(Collection c)`](http://coderolls.com/arraylist-removeall-method/)|This method removes from this list all of its elements that are contained in the specified collection.|
|[`iterator()`](https://coderolls.com/remove-element-from-arraylist/)|This method provides the Iterator to iterate over an ArrayList.|
|[`clear()`](http://coderolls.com/arraylist-clear-method-in-java/)|This method removes all the elements from the list and makes it empty.|
|[`isEmpty()`](http://coderolls.com/arraylist-isempty-method/)|This method returns true if this list contains no elements.|
|[`contains()`](http://coderolls.com/arraylist-contains-method/)|This method is used for checking if the specified element exists in the given list or not.|
|[`toArray()`](http://coderolls.com/convert-arraylist-to-array/)|This method returns an array containing all of the elements in this ArrayList in proper sequence.|
|[`toArray(T[] a)`](http://coderolls.com/convert-arraylist-to-array/)|This method returns `T []` i.e. An array of the specified type `T` can be returned.|
|[`removeRange(int fromIndex, int toIndex)`](http://coderolls.com/arraylist-removerange-method/)|This method is used for removing the range of ekements from the subclasses of the ArrayList class. The [`removeRange(int fromIndex, int toIndex)` method](http://coderolls.com/arraylist-removerange-method/) is a protected method.|
|[`retainAll(Collection c)`](http://coderolls.com/arraylist-retainall-method/)|This method method retains all the elements of the collection passed as a parameter in the list.|
|[`trimToSize()`](http://coderolls.com/arraylist-trimtosize-method/)|This method trims the capacity of this ArrayList instance to be the list's current size.|
|[`indexOf(Object o)`](http://coderolls.com/arraylist-indexof-method/)|This method returns the index of the first occurrences of the object specified. It returns -1 if the specified object `o` is not present in the list.|
|[`lastIndexOf(Object o)`](http://coderolls.com/arraylist-lastIndexof-method/)|This method returns the index of the last occurrences of the object specified. It returns -1 if the specified object `o` is not present in the list.|
|[`ensureCapacity()`](http://coderolls.com/arraylist-ensurecapacity-method/)|This method increases the capacity of this  ArrayList instance, if necessary, to ensure that it can hold at least the number of elements specified by the minimum capacity argument.|
|[`listIterator()`](http://coderolls.com/arraylist-listiterator-method/)|This method returns a *fail-fast* list iterator over the elements in this list (in proper sequence).|



## Features

### 1. ArrayList maintains the insertion order.

I have given a simple java program below that shows, ArrayList maintains the insertion order.

```java
import java.util.ArrayList;

/**
 * A Java program showing arraylist maintains the insertion order.
 * 
 * @author gaurav
 *
 */
public class ArrayListExample {

	public static void main(String[] args) {
		
		ArrayList<String> arrayList = new ArrayList<String>();
		
		arrayList.add("Gaurav");
		arrayList.add("Shyam");
		arrayList.add("Saurav");
		arrayList.add("Samiksha");
		arrayList.add("Rina");
		
		System.out.println(arrayList);
	}
}
```
**Output**
```
[Gaurav, Shyam, Saurav, Samiksha, Rina]
```

#### Explanation

1. In the above program, I have created an `arrayList` object with a type one constructor. So default initial capacity of arrayList is 10.
2. I have added 5 string objects using the `add()` method one by one.
3. I have printed the `arrayList` object using a sysout statement. Here we can observe that all the strings are in the same order that they are inserted in the code. So we can say that the `ArrayList` maintains the insertion order. 

### 2. ArrayList allow the duplicate elements.

I have given a simple java program below that shows, ArrayList allow the duplicate elements.

```java
import java.util.ArrayList;

public class ArrayListDuplicate {

	public static void main(String[] args) {
		ArrayList<String> arrayList = new ArrayList<String>();
		
		arrayList.add("Gaurav");
		arrayList.add("Shyam");
		arrayList.add("Saurav");
		arrayList.add("Samiksha");
		arrayList.add("Rina");
		arrayList.add("Rina"); //adding a duplicate string object 
		
		System.out.println(arrayList);

	}
}
```
**Output**

```
[Gaurav, Shyam, Saurav, Samiksha, Rina, Rina]
```
#### Explanation

1. In the above program, I have created an `arrayList` object with a type one constructor. So default initial capacity of arrayList is 10.
2. I have added 6 string objects using the `add()` method one by one. You can observe the 5th and 6th String objects are the same. i.e duplicate (`"Rina"` ) 
3. On printing the `arrayList`, we can see the 5th as well as 6th String object (`"Rina"` ) on the console. That means `ArrayList` will allow the duplicate elements.

## Comon Operations on ArrayList

### 1. Adding an element in the ArrayList

When we create an ArrayList Object, we can add an element to the ArrayList using the `add(Object o)` method and `add(int index, Object o)` method.

Read more and check example Java programs about adding an element to the ArrayList in this blog: [How To Add An Element To ArrayList In Java?](https://coderolls.com/add-element-in-arraylist/)

### 2. Changing an element of the ArrayList

When you create an ArrayList objects and add elements to it, some you need to change the element at particular index. You can do it using the `set(int index, E element)`.

Read more and check example Java programs about changing the element of ArrayList in this blogpost: [How To Change An Element In ArrayList?](https://coderolls.com/change-element-in-arraylist/)

### 3. Removing an element of the ArrayList

If you want to remove the element from the ArrayList, you can use the remove(Object o) method or remove(int index) method.

Read more and check example Java program about removing an element from the ArrayList on this blogpost: [How To Remove An Element From An ArrayList?](http://coderolls.com/remove-element-from-arraylist/)

### 4. Iterating over an ArrayList

There are multiple ways to iterate over an ArrayList. You can use the traditional for loop or for-each loop or Iterator.

I have covered all the ways of iterating the ArrayList in Java with all the examples at [Iterating the ArrayList In Java](http://coderolls.com/iterating-the-arraylist-in-java/)

---

The example java programs given in the above tutorial can be found at [this GitHub Repository](https://github.com/coderolls/blogpost-coding-examples/tree/main/collections/arraylist/arraylist-in-java).

Let me know you thoughts or suggestions in comment section below.
