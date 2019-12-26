---
layout: post
title: Learn About Java String Pool And intern() Method
author: gaurav
categories: [ Java, Core Java, String]
description: String is an important class in Java. In this article I am explaining one of the most important concepts of String class i.e. the concept of Java String Pool and the `intern()` method. Read this article to understand this concept completely. 

---

The string is an important class in Java. In this article I am explaining one of the most important concepts of String class i.e. the concept of Java String Pool and the `intern()` method. Read this article to understand this concept completely. I have given two code examples to make this concept easy to understand.


## Introduction

The string is a special class in java. Most of the programs in java use string class and its methods. Let’s see the String intern() method.

When you are comparing strings, the one method you must know is the intern method of the string. So, you should know, when to use the `intern()`  method, why should we use the `intern()`  method and what will happen to the string after applying the `intern()`  method to it.

In this article, we will learn about the String intern() method and also the Java string pool concept.

`intern()`  method returns the canonical representation of the string. If you have got the previous sentence don’t be a worry. First of all, we will understand the string pool concept so that it will help you to understand the  `intern()`  method.

So, let us learn about the Java string pool first.

## Java String pool

Java Virtual Machine (JVM) privately maintained a special memory space in the java heap memory. This special memory space is called a Java String pool.

Java String pool is a reserved space to store unique string objects.

Whenever we assign a string literal to string variable JVM checks if the string with the equal value is available in the string pool.

If found, it returned the reference of its memory address to the string variable.

If not found, that string will be added to the string pool and its reference will be returned.

The above-mentioned process will happen automatically with string literals. The process of interning happens to the string literals automatically. See the note for more information.

## `intern()`  method.

`intern()`  method is used to add a unique copy of a string object in the string pool manually.

When we create a string using the  `new`  operator the new object of the  `String`  is created in java heap space.

As we apply the  `intern()`  method to that string variable, it first checks if the string with the equal value is available in the string pool.

If found, it simply returns the reference of the memory address of that string object.

And If not found, the copy of that string object will be added to the string pool and its reference will be returned.

In both cases, the process seems like the same, but when we assign a string literal to the string variable, it will be interned automatically. When we create the string using  `new`  operator the string object will directly be added to the Java heap space.

If we want to add that string object to the string pool, we have to apply the intern() method I.e. manually.

```
Public String intern() 
Returns a canonical representation of a string.

Returns -
It returns the string with the equal contents as this string but guaranteed from the string pool of unique strings.
```

I have given two examples below. It will explain the interning of the strings in case of the string literals assigned to the string variable and also string objects created using the  `new`  operator.

In the first example, we will see the automatic interning of the strings literals

```
/**
 * A java program to compare the reference of the strings.
 * We use '==' operator to check the reference equality.
 * 
 * @author Gaurav Kukade at coderolls.com
 *
 */

public class StringReferenceCompare {

  public static void main(String[] args) {
    
    String firstString = "coderolls";
    
    String secondString = "coderolls";
    
    System.out.println(firstString == secondString); //true
  }

}
```
Output:

```
true
```

### Explanation:

1. When we assign the “coderolls” value to the  `firstString`  variable the JVM checks if the string with the value “coderolls” is present in the string pool or not.

   JVM will not found a string with equal value in the java string pool because we have created it for the first time in this program. And therefore it will return the reference to that string after adding it to the string pool.

2. When we assign the “coderolls” value to the  `secondString`  variable the JVM checks if the string with the value “coderolls” is present in the string pool or not.

   Since we have created the string will equal value in the first step of this program JVM will found it and as a result reference to its memory address will be returned.

3. When we check both string using  `==`  operator it will print  `true`, since both string variable is pointing towards the same string object.

In the second example, we will see the manual interning of the string.

```
/**
 * A java program to use an intern() method of the String class.
 * 
 * intern() method returns the canonical representation of the string.
 * @author Gaurav Kukade at coderolls.com
 */

public class UseInternMethod {

  public static void main(String[] args) {

    String firstString = "coderolls";
    String secondString = new String("coderolls");
    
    System.out.println(firstString == secondString); // false
    
    String thirdString = secondString.intern();
    
    System.out.println(firstString == thirdString); // true
  }

}
```

Output:

```
false
true
```

### Explanation:

1. We have assigned the “coderolls” value to the  `firstString`  variable. JVM will checks if the string with the same value is present in the string pool. Since we have not created any string with this value JVM will add it to the string pool.

2. We have created a string with the same value using the new operator and assigned it to the  `secondString`  variable. As a result, this string object will be stored in the java heap space.

3. When we check both the strings using  `==`  operator, it will print the false since the  `firstString`  is pointing towards the string object in the string poo while the  `secondString`  is pointing towards the string object in the java heap space. Hence both  `firstString` and  `secondString` are pointing towards the different objects and it will print  `false`.

4. We have applied the  `intern()`  method to the  `secondString`  and assigned it to the new variable  `thirdString`.

5. After applying intern() method JVM will have a check if the string with same value as  `secondString`  is present in the string pool since it is already added in the first step ( when we have assigned “coderolls” to the `firstString`) JVM will found it and simply the reference to the memory address of it will be returned.

6. Now, when we compare  `firstString`  and  `thirdString`  using  `==`  operator it will print  `true` because both string variables are pointing towards the same string object in the java string pool.

#### Note:
All the literal strings and string-valued constant expressions are interned automatically. i.e.`firstString = "coderolls";`  here  `firstString`  will be interned automatically.

## Conclusion

Java string pool is a special memory maintained by the JVM in heap memory to store a unique string object. For that reason. it will help in the code optimization and to reuse string objects.

When you assigned a literal to string variable it will automatically be interned. This means the string object will be added to the java string pool automatically.

In contrast, when you create a string using  `new`  operator you have applied `intern()`  method to add its copy to the java string pool.

If you found this article worth, please

[Give me a cup of Coffee ☕](https://paypal.me/GauravKukade)

If you have any queries about the code blocks given above, please write it down in the comment section below. Also. let me know if you have any other information about the Java String pool and  `intern()`  method in the comment section.

### Related Article

-   [How do I compare strings in Java](https://coderolls.com/compare-strings-in-java)
-   [Reverse A String In Java (5 ways)](https://coderolls.com/reverse-a-string-in-java/)
-   [Compare Two Strings Lexicographically In Java](https://coderolls.com/compare-two-strings-lexicographically-in-java/)
-   [Introduction to Java Technology (Language and Platform)](https://coderolls.com/java-introduction/)
