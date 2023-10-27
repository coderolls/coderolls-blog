---
layout: post
title: "How to convert ArrayList to Array In Java?"
author: gaurav
categories: [Collections, ArrayList]
toc: true
description: "In this article, we will see how to convert an ArrayList to an Array in Java."
---
In this article, we will see how to convert an ArrayList to an Array in Java.

## Introduction

[ArrayList in Java](https://coderolls.com/arraylist-in-java/) is an ordered collection. Also, ArrayList allows the duplicate elements.

We have see the ArrayList method like [`add()`](https://coderolls.com/add-element-in-arraylist/), [`addAll()`](http://https//coderolls.com/arraylist-addall-method-in-java/), [`remove()`](https://coderolls.com/remove-element-from-arraylist/), [`set()`](https://coderolls.com/change-element-in-arraylist/), [`iterate()`](http://coderolls.com/iterating-the-arraylist-in-java/), [`clear()`](http://coderolls.com/arraylist-clear-method-in-java/) and [`contains()`](http://coderolls.com/arraylist-contains-method).

ArrayList mostly provides all the regular operations that need to be performed on Array. So convert ArrayList to Array only when your use case requires it.

We can convert an ArrayList to an Array in Java using the `toArray()` method. 

There are two methods to convert an ArrayList to an Array. They are given below.

1. `public Object[] toArray()` method
2. `public <T> T[] toArray(T[] a)` method

Let's see both methods one by one.

## 1. `public Object[] toArray()` method

The `toArray()` method returns an array containing all of the elements in this ArrayList in proper sequence.

The method signature is given below.

```java
public Object[] toArray()
```

As shown in the above method signature, the return type of this method is `Object[]`. It returns an array that contains all the elements of the ArrayList in proper sequence.

I have given an example Java program to convert an ArrayList to an Array. It converts an ArrayList of String to Object Array i.e. `Object []`.

```java
/**
 * A Java program to convert an ArrayList to an array using
 * toArray method.
 * 
 * toArray() method returns Object[]
 * 
 * @author coderolls.com
 *
 */
public class ArrayListToArray {

  public static void main(String[] args) {
    ArrayList<String> arrayList = new ArrayList<String>();
    
    //adding elements to the ArrayList
    arrayList.add("Meta");
    arrayList.add("Apple");
    arrayList.add("Amazon");
    arrayList.add("Netflix");
    arrayList.add("Microsoft");
    arrayList.add("Google");
    
    System.out.println("ArrayList: \n"+ arrayList);
    
    // convert ArrayList to array
    Object[] objects = arrayList.toArray();
    
    System.out.println("\nArray:");
    
    //we will receive the object array, so iterate on it to print each element
    for(Object obj:objects) {
      System.out.println(obj);
    }
  }
}
```
Output:
```
ArrayList: 
[Meta, Apple, Amazon, Netflix, Microsoft, Google]

Array:
Meta
Apple
Amazon
Netflix
Microsoft
Google
```
## 2. `public <T> T[] toArray(T[] a)` method

This method also returns an array that contains all the elements of the ArrayList in proper sequence.

The method signature is as given below.

```java
public <T> T[] toArray(T[] a)
```

As shown in the method signature, this method accepts one parameter.

 - **`T[] a`:-** A new array of type T, into which the elements of the list are to be stored. If the specified array is not enough to store all the elements of the ArrayList, a new array of the same type will be created.

This method returns `T []` i.e. An array of the specified type can be returned.

I have given a sample Java program to convert an ArrayList to an array. Here, we will be converting an ArrayList of type String to String Array i.e. `String []`.

```java
import java.util.ArrayList;

/**
 * A Java program to convert an ArrayList to an array using
 * toArray method.
 * 
 * toArray(T[] a) method returns T[]
 * 
 * @author coderolls.com
 *
 */
public class ArrayListToArray2 {

  public static void main(String[] args) {
    ArrayList<String> arrayList = new ArrayList<String>();
    
    //adding elements to the ArrayList
    arrayList.add("Meta");
    arrayList.add("Apple");
    arrayList.add("Amazon");
    arrayList.add("Netflix");
    arrayList.add("Microsoft");
    arrayList.add("Google");
    
    System.out.println("ArrayList: \n"+ arrayList);
    
    // convert ArrayList to array
    // pass a new String array of the ArrayList size as a param to toArray
    //String[] elements = arrayList.toArray(new String[arrayList.size()]);
    
    //kindly read the 'Important Note' below
    String[] elements = arrayList.toArray(new String[0]);
    
    
    System.out.println("\nArray:");
    //we will receive the string array, so iterate on it to print each element
    for(String str:elements) {
      System.out.println(str);
    }
  }
}
```
Output:
```
ArrayList: 
[Meta, Apple, Amazon, Netflix, Microsoft, Google]

Array:
Meta
Apple
Amazon
Netflix
Microsoft
Google
```

### Important Note:

The code above used new String[arrayList.size()] as a parameter to a `toArray()` method. However, [this blogpost from Aleksey Shipilёv](https://shipilev.net/blog/2016/arrays-wisdom-ancients/) reveals that due to JVM optimizations, using new String[0] is better now. 


## Conclusion

We can convert an ArrayList to an Array in Java using the `toArray()` method.

There are two versions of the `toArray()` method.

1. `public Object[] toArray()` method
2. `public <T> T[] toArray(T[] a)` method

---

The example Java programs given in the above tutorial can be found at [this GitHub Repository](https://github.com/coderolls/blogpost-coding-examples/tree/main/collections/arraylist/convert-arraylist-to-array).

Please write your thoughts in the comment section below.
