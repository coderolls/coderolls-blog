---
layout: post
title: "How To Convert An Integer To String In Java"
author: gaurav
image: assets/images/2021-02-27/convert-int-to-string.webp
categories: [Java, Core Java, String]
description: "In this article you are going to learn how can you convert an integer to a String."
---

In this article you are going to learn how can you convert an integer to a String.

There are multiple ways we can convert an int to string in java. let's check what are they.

1. `String.ValueOf()` method
2. `Integer.toString()` method
3. String.format() method

## 1. `String.valueOf()` method

`String.valueOf()` method returns the string representation of the  `Object`  argument.

So when we pass an int as parameter to `valueOf()` method, it returns it's String representation.

If the argument is  `null`, then a string equal to  `"null"`will be returned.

Internally `valueOf()` method calls `toString()` method on the object argument to get its string representation.

An example to convert an int to string using `valueOf()` method is given below.

```java
/*
 * A program to convert an int to string in java using 
 *  the String.toSTring() method.
 *
 * @author Gaurav Kukade at coderolls.com
 */

public class IntToSTring{

     public static void main(String []args){
        
        int number = 1234;
        
        String numberString = String.valueOf(number);
        
        //print string value of number
        System.out.println("numberString: " + numberString);
    }
}
```
Output
```java
numberString: 1234
```

## 2. `Integer.toString()` method

`Integer.toString()` method returns the String object of the Integer's value.

The value is converted to signed decimal representation and returned as a string, exactly as if the integer value were given as an argument to the `toString()` method.

An example to convert an int to string using the `toString()` method is given below.

```java
/*
 * A program to convert an int to string in java using 
 *  the Integer.toString() method.
 *
 * @author Gaurav Kukade at coderolls.com
 */

public class IntToSTring{

     public static void main(String []args){
        
        int number = 1234;
        
        //String numberString = String.valueOf(number);
        
        
        String numberString = Integer.toString(number);
        //print string value of number
        System.out.println("numberString: " + numberString);
    }
}
```
Output
```java
numberString: 1234
```

## Conclusion

We can convert an int to String in Java using 

1. the String.valueOf() method 

```java
String numberString = String.valueOf(number);
```

2. the Integer.toString() method.

```java
String numberString = Integer.toString(number);
```
In both cases, `number` is an `int` value.


### Related Articles

-   [How to convert String to Integer in Java](https://coderolls.com/convert-string-to-int/)
-   [Learn About Java String Pool And intern() Method](https://coderolls.com/java-string-pool-and-intern-method/)
-   [How Do I Compare Strings In Java](https://coderolls.com/compare-strings-in-java/)
-   [How To Reverse A String In Java (5 ways)](https://coderolls.com/reverse-a-string-in-java/)
-   [Compare Two Strings Lexicographically In Java](https://coderolls.com/compare-two-strings-lexicographically-in-java/)
-   [Difference Between StringBuffer and StringBuilder class](https://coderolls.com/difference-between-stringbuffer-and-stringbuilder/)
-   [8 Basic GIT Commands Every Newbie Developer Must Know](https://coderolls.com/basic-git-commands/)
