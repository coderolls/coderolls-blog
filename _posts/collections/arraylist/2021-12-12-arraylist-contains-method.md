---
layout: post
title: "ArrayList contains() method in Java"
author: gaurav
categories: [Collections, ArrayList]
toc: true
description: "In this article, we will see the contains() method of ArrayList in Java. This method is used to check if the list contains the specified element."
---
In this article, we will see the `contains()` method of [ArrayList class in Java](https://coderolls.com/arraylist-in-java/). This method is used to check if the list contains the element.

## Introduction

[ArrayList](https://coderolls.com/arraylist-in-java/)  is an ordered collection and it allows duplicate elements. It is widely used to store and retrieve data.

We have seen a few methods of the ArrayList class before like [`add()`](https://coderolls.com/add-element-in-arraylist/), [`addAll()`](http://https://coderolls.com/arraylist-addall-method-in-java/), [`remove()`](https://coderolls.com/remove-element-from-arraylist/), [`set()`](https://coderolls.com/change-element-in-arraylist/), [`iterate()`](http://coderolls.com/iterating-the-arraylist-in-java/) and [`clear()`](http://coderolls.com/arraylist-clear-method-in-java/). Today we will see the `contains()` method.

If we need to check if any element is present in the list or not, we can use the `contains()` method from the ArrayList class in Java.

## ArrayList `contains()` method

It has a method signature as given below.
```java
public boolean contains(Object o)
```

This method is used to check if the ArrayList contains the specified element.

This method accepts a single parameter of type `Object`

- **`o`: -** an Object `o` whose presence in this list is to be tested

This method has a return type as a `boolean`. It returns `true` if the list contains the specified element. Otherwise, it returns `false`.

I have given a Java program to check if the list contains the specified element using the ArrayList `contains()` method.

```java
import java.util.ArrayList;
import java.util.List;
/**
 * A Java program to check if the ArrayList 
 * contains the specified element.
 * 
 * @author Gaurav Kukade a coderolls.com
 *
 */
public class ArrayListContainsMethodExample {

  public static void main(String[] args) {
  
    //create an empty ArrayList object 'states'
    List<String> states = new ArrayList<String>();
    
    //add state in the ArrayList 
    states.add("California");
    states.add("Texas");
    states.add("Florida");
    states.add("New Jersey");
    states.add("Washington");
    
    //check if states contain Florida
    boolean isPresent1 = states.contains("Florida");
    System.out.println("Is Florida present in the list: "+ isPresent1);
    
    //check if states contain Alaska
    boolean isPresent2 =states.contains("Alaska");
    System.out.println("\nIs Alaska present in the list: "+ isPresent2);
  }
}
```
Output:
```
Is Florida present in the list: true

Is Alaska present in the list: false
```
### Explanation
1. I have created an ArrayList object `states`.
2. I have added a few String objects in the `states`.
3. I have checked if the list `states` contains the `Florida` string object using the `contains()` method. Since `Florida` is present in the `states` list, it returns `true`.
4. I have captured the return value for the first `contains()` method in the `isPresent1` boolean variable. When we print the `isPresent1`, it has a value `true`.
5. Next time, I checked if the `states` list contains the `Alaska` using the `contains()` method. Since `Alaska` is not present in the `states` list, it returns `false`
6.  I have captured the return value for the second `contains()` method in the `isPresent2` boolean variable. When we print the `isPresent2`, it has a value `false`. 


## Conclusion

The ArrayList `contains()` method is used to check if the list contains the specified element.

This method returns `true` if the specified element is present in the list. Otherwise, it  returns `false`

---

The example Java program used in the above article can be found at [this GitHub repository](https://github.com/coderolls/blogpost-coding-examples/tree/main/collections/arraylist/arraylist-contains-method).

If you know anything other than this, kindly write in the comment section below.
