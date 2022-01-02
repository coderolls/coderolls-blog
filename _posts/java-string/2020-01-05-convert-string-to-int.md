---
layout: post
title: "How to convert String to int in Java?"
author: gaurav
categories: [ Java, Core Java, String]
toc: true
description: "In this article you are going to learn how one can convert the string to int using the inbuilt methods of the Integer class."
---

In this article you are going to learn how one can convert the string to int using the inbuilt methods of the Integer class.

## Introduction
We have learned many tutorials on the String class and seen the String operations are an important part of java programming.

Sometimes we took some values as a String but we want to operate them as an int, then questions arise how can one convert string to int? The Java team provided the solution for it.

Converting a string to int is one of the most important things to know by a Java Developer.

Now we will see what are the available options to convert a string to int.

I have listed down two ways to convert a String to int.

1. Convert String to int using the `Integre.parseInt()` method
2. Convert String to int using the `Integer.valueOf()` method

You can watch [the video on my youtube channel for "How To Convert A String To An Integer In Java"](https://www.youtube.com/watch?v=pNHjvpNHVCs).

<iframe width="560" height="315" src="https://www.youtube.com/embed/pNHjvpNHVCs" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Now we will see the above ways to convert string to int one by one.

## How to convert string to int using the `Integre.parseInt()` method

We can convert String to int using the `Integre.parseInt()` method.

The `Integer.parseInt()` method can convert an entire string to int, provided the String must contain the digit values only. For example `String str= "123";`

Now we will see one example which converts the string to int using the `Integre.parseInt()` method.

```java
/*
 * A Java program to convert String to int.
 * 
 * @author Gaurav Kukade at coderolls.com
 */
public class StringToInt{
	public static void main(String [] args){
		
		String str = "1254";
		
		// convert string to int
		int result = Integer.parseInt(str);
	
		System.out.println(result);
	}
}
```
Output
```java
1254
```
## How to convert string to int using the `Integer.valueOf()` method

We can also convert String to int using the `Integer.valueOf()` method.

The  `Integer.valueOf()` method returns the integer instance of the value represented by the string variable.

Below we will see one program to convert string to int using the `Integer.valueOf()` method.

```java
/*
 * A Java program to convert String to int.
 * 
 * @author Gaurav Kukade at coderolls.com
 */
public class StringToInt{
	public static void main(String [] args){
		
		String str = "134";
		
		// convert string to int
		int result = Integer.valueOf(str);
	
		System.out.println(result);
	}
}
```
Output
```java
134
```

## A Note about `NumberFormatException`

When you are trying to convert a string to int but your string contains a value other than the decimal digits, then both the methods (`Integre.parseInt()` method and `Integer.valueOf()` method) will throw the `NumberFormatException`.

Below we will one program to see how `Integre.parseInt()` method throw the `NumberFormatException`.

```java
/*
 * A Java program showing the Integer.parseInt() method throwing
 * NumberFormatException
 * 
 * @author Gaurav Kukade at coderolls.com
 */
public class StringToInt{
	public static void main(String [] args){
		
		String str = "134xyz";
		
		// convert string to int
		int result = Integer.valueOf(str);
	
		System.out.println(result);
	}
}
```
Output
```java
Exception in thread "main" java.lang.NumberFormatException: For input string: "134xyz"
	at java.lang.NumberFormatException.forInputString(NumberFormatException.java:65)
	at java.lang.Integer.parseInt(Integer.java:580)
	at java.lang.Integer.valueOf(Integer.java:766)
	at StringToInt.main(StringToInt.java:14)
```

## Conclusion

We can convert String to int using two methods, `Integre.parseInt()` method and `Integer.valueOf()` method.

If the string contains some other value than the decimal numbers both the methods will throw the `NumberFormatException`.

If you know any other way to convert the string to int or if you have any query about the string to int conversion please write it down in the comment section below.
