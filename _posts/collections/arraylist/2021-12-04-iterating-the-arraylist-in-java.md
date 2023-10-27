---
layout: post
title: "Iterating the ArrayList In Java"
author: gaurav
categories: [Collections, ArrayList]
toc: true
description: "In this article, we will see how to iterate through an ArrayList in Java. We will see the various to iterate like for loop, Iterator Interface, For-Each method with Lambda expression etc"
---
In this article, we will see how to iterate through an [ArrayList In Java](https://coderolls.com/arraylist-in-java/). We will see the various to iterate like for loop, Iterator Interface, For-Each method with Lambda expression etc

## Introduction
ArrayList is a very common class from the Collections framework for storing elements.

When we store objects in ArrayList, they preserve the insertion order. Also, ArrayList allows us to add duplicate elements too.

As we use ArrayList to store and retrieve the objects, sometimes we need to iterate over them. And today, we will see how we can iterate through ArrayList in Java.

There are multiple ways to iterate over the ArrayList. We will see the following ways
1.  Iterating the ArrayList using basic for loop
2. Iterating the ArrayList using Enhanced For Loop i.e. For-each loop
3. Iterating the ArrayList using while loop
4. Iterating the ArrayList using Iterator
5. Iterating the ArrayList using Java 8 forEach() Method

So let's see all the options one by one.

## 1.  Iterating the ArrayList using basic for loop

We can write a simple for loop for the ArrayList and access the elements of the ArrayList using the get() method.

I will write a simple java program to show how we can iterate through ArrayList using the basic for loop.

```java
import java.util.ArrayList;
import java.util.List;

/**
 * A Java program to iterate through ArrayList 
 * using the basic for loop.
 * 
 * @author coderolls.com
 *
 */
public class ArrayListIterateExample1 {
    
  public static void main (String[] args) {
  
    List<String> list = new ArrayList<String>();
    
    list.add("Monday");
    list.add("Tuesday");
    list.add("Wednesday");
    list.add("Thursday");
    list.add("Friday");
    list.add("Saturday");
    list.add("Sunday");
    
    System.out.println("Iterating through ArrayList using the basic for loop.......\n");
    
    for(int i =0; i <list.size(); i++){
      System.out.println("The object from the ArrayList at "+ i + " is " + list.get(i));
    }
  }
}
```
Output:
```
Iterating through ArrayList using the basic for loop.......

The object from the ArrayList at 0 is Monday
The object from the ArrayList at 1 is Tuesday
The object from the ArrayList at 2 is Wednesday
The object from the ArrayList at 3 is Thursday
The object from the ArrayList at 4 is Friday
The object from the ArrayList at 5 is Saturday
The object from the ArrayList at 6 is Sunday
```
### Explanation
1. I have created an empty ArrayList of String.
2. I have added a few String objects to the ArrayList i.e `list`
3. I have written a simple for loop from 0 i.e. `i=0` to the length of the list i.e. `list.size()`, so we will be iterating over ArrayList in ascending order.
4. We are using a `get(int index)` method to get an object from the ArrayList at index `i`.


## 2. Iterating the ArrayList using Enhanced For Loop i.e. For-each loop

Here we will use the [foreach loop i.e. Enhanced For Loop](https://coderolls.com/for-each-loop/) to iterate through ArrayList.

Let us understand the syntax for the Enhanced For Loop.

```java
for(DataType item:Array | Collection){
// operate on the item here
}
```
Below I have given a Java program to iterate over an ArrayList using the Enhanced For Loop i.e. For-each loop

```java
import java.util.ArrayList;
import java.util.List;

/**
 * A Java program to iterate through an ArrayList 
 * using enhanced for loop i.e. For-each loop.
 * 
 * @author coderolls.com
 *
 */
public class ArrayListIterateExample2 {
    
  public static void main (String[] args) {
  
    List<String> list = new ArrayList<String>();
    
    list.add("Monday");
    list.add("Tuesday");
    list.add("Wednesday");
    list.add("Thursday");
    list.add("Friday");
    list.add("Saturday");
    list.add("Sunday");
    
    System.out.println("Iterating through ArrayList using enhanced for loop i.e. For-each loop.......\n");
    
    for(String str:list){
      //we got an item 'str' in the loop
      System.out.println("Object form the ArrayList is " + str);
    }
  }
}
```

Output:
```
Iterating through ArrayList using enhanced for loop i.e. For-each loop.......

The object from the ArrayList is Monday
The object from the ArrayList is Tuesday
The object from the ArrayList is Wednesday
The object from the ArrayList is Thursday
The object from the ArrayList is Friday
The object from the ArrayList is Saturday
The object from the ArrayList is Sunday
```
### Explanation

1. In the above Java program, I have created an empty ArrayList of String.
2. I have added a few String objects to the ArrayList. i.e `list`
3. I have written an enhanced for loop i.e. for each loop for the `list`.
4. Using the for-each loop, we can operate over each object of the `list`, as shown in the above program, we got `str` in the loop.
5. Finally, I have simply printed the `str` objects.

## 3. Iterating the ArrayList using a while loop

We can iterate over an ArrayList using the while loop.

The program to iterate over an ArrayList using the while loop is given below.

```java
import java.util.ArrayList;
import java.util.List;

/**
 * A Java program to iterate through an ArrayList 
 * using a while loop.
 * 
 * @author coderolls.com
 *
 */
public class ArrayListIterateExample3 {
    
  public static void main (String[] args) {
  
    List<String> list = new ArrayList<String>();
    
    list.add("Monday");
    list.add("Tuesday");
    list.add("Wednesday");
    list.add("Thursday");
    list.add("Friday");
    list.add("Saturday");
    list.add("Sunday");
    
    System.out.println("Iterating through ArrayList using while loop.......\n");
    
    int i=0;
    // while loop condition will be true till i is less the the list size
    while (list.size()>i) {
      System.out.println("Object form the ArrayList at "+ i + " is " + list.get(i));
      i++;
    }
  }
}
```
Output:

```
Iterating through ArrayList using while loop.......

The object from the ArrayList at 0 is Monday
The Object from the ArrayList at 1 is Tuesday
The object from the ArrayList at 2 is Wednesday
The object from the ArrayList at 3 is Thursday
The object from the ArrayList at 4 is Friday
The object from the ArrayList at 5 is Saturday
The object from the ArrayList at 6 is Sunday
```
### Explanation
1. In the above Java program, I have created an empty ArrayList of String.
2. I have added a few String objects to the ArrayList i.e `list`
3. Before starting the for loop, I have initialized a variable `i` with a value as `0`.
4. I have written a simple while to loop to check the condition for `i` is less than the size of the list i.e. `list.size()`
5. If the above condition is true, we will enter in the loop, and we can access the particular object of the list using the `get(int index)` method.
6. After accessing/operating on the object, we are incrementing the variable `i` by one i.e. `i++`
7. Once the value of `i` becomes greater than or equal to the list size, the condition will be false and we will not be able to enter in the loop.

## 4. Iterating the ArrayList using Iterator

Iterator is an interface in Java. We can use an Iterator to iterate over a collection.

It is present in the `java.util` package.

If we want to iterate over an ArrayList using an iterator, we should invoke the iterator() method on the ArrayList object to get the iterator reference as given below
```java
// list is an ArrayList object
Iterator iterator = list.iterator();
```
Iterator has three important methods. They are given below.

`hasNext()` - This method checks if the collection has any object available next, if found it will return true else false

`next()` - This method returns the next object from the ArrayList.

`remove()` - This method removes the object from the ArrayList

I have given a Java program below to iterate over an ArrayList using the iterator interface. We will be using the `hasNext()` and `next()` methods in the program.

```java
import java.util.Iterator;
import java.util.ArrayList;
import java.util.List;
/**
 * A Java program to iterate through an ArrayList 
 * using the Iterator interface.
 * 
 * @author coderolls.com
 *
 */
public class ArrayListIterateExample4 {
    
  public static void main (String[] args) {
  
    List<String> list = new ArrayList<String>();
    
    list.add("Monday");
    list.add("Tuesday");
    list.add("Wednesday");
    list.add("Thursday");
    list.add("Friday");
    list.add("Saturday");
    list.add("Sunday");
    
    System.out.println("Iterating through ArrayList using Iterator interface........\n");
    
    // getting an iterator
    Iterator iterator = list.iterator();
    
    // hasNext() returns true only if the object is available at the next call
    while (iterator.hasNext()) {
      //next() returns an object, we can cast it to the required type
      String str = (String) iterator.next();
      System.out.println("Object form the ArrayList is " + str);
    }
  }
}
```
Output:
```
Iterating through ArrayList using Iterator interface........

The object from the ArrayList is Monday
The object from the ArrayList is Tuesday
The object from the ArrayList is Wednesday
The object from the ArrayList is Thursday
The object from the ArrayList is Friday
The object from the ArrayList is Saturday
The object from the ArrayList is Sunday
```
### Explanation

1. In the above Java program, I have created an empty ArrayList of String.
2. I have added a few String objects to the ArrayList i.e `list`
3. I have invoked the `iterator()` method on the `list` to get an iterator.
4. I have written a simple while loop with the condition `iterator.hasNext()`. It returns true only if the object is available.
5. Once we enter the loop, we can use the `iterator.next()` method to get the object.
6. We can cast it to the required datatype and use it in the loop.
7. The `hasNext()` method returns true till the list has the object i.e. till the last object of the list and after that, it will return false. And we will not enter in the loop.

### Note :
It is always recommended to use the  `Iterator.remove()` method for removing an element from a list while iterating on it. Also, we have the `remove()` method in the ArrayList class, if you use the `ArrayList.remove()` method to remove an element while iterating over the list, you will get the `ConcurrentModificationException`.


## 5. Iterating the ArrayList using Java 8 forEach() Method

In Java 8, we got the new `forEach()` method to iterator over collections.

Inside the `forEach()` method, we can write the lambda expression for the Consumer functional interface.

I have given a sample Java program below to iterate over the ArrayList using the `forEach()` method.

```java

import java.util.ArrayList;
import java.util.List;

/**
 * A Java program to iterate through an ArrayList 
 * using forEach method and lambda expression.
 * 
 * @author coderolls.com
 *
 */
public class ArrayListIterateExample4 {
    
  public static void main (String[] args) {
  
    List<String> list = new ArrayList<String>();
    
    list.add("Monday");
    list.add("Tuesday");
    list.add("Wednesday");
    list.add("Thursday");
    list.add("Friday");
    list.add("Saturday");
    list.add("Sunday");
    
    System.out.println("Iterating through ArrayList using forEach method and lambda expression........\n");
    
    // add lambda expression in the foreach method
    list.forEach(s -> System.out.println("Object form the ArrayList is "+ s));
  }
}
```
Output:
```
Iterating through ArrayList using forEach method and lambda expression........

The object from the ArrayList is Monday
The object from the ArrayList is Tuesday
The object from the ArrayList is Wednesday
The object from the ArrayList is Thursday
The object from the ArrayList is Friday
The object from the ArrayList is Saturday
The object from the ArrayList is Sunday
```
### Explanation

1. In the above Java program, I have created an empty ArrayList of String.
2. I have added a few String objects to the ArrayList. i.e `list`
3. I have invoked the `forEach()` method on the `list`, and added the following lambda expression to simply print the string objects `
s -> System.out.println("Object form the ArrayList is "+ s)`.

## Conclusion

We can iterate over ArrayList using the following ways.

1.  Iterating the ArrayList using basic for loop
2. Iterating the ArrayList using Enhanced For Loop i.e. For-each loop
3. Iterating the ArrayList using a while loop
4. Iterating the ArrayList using Iterator
5. Iterating the ArrayList using Java 8 forEach() Method

---

The example Java programs given in the above tutorial can be found at [this GitHub Repository](https://github.com/coderolls/blogpost-coding-examples/tree/main/collections/arraylist/iterating-the-arraylist-in-java).

If you know any other way to iterate through ArrayList, please write it down in the comment section below.
