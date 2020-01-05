---
layout: post
title: How to convert String to Integer in Java
author: gaurav
categories: [ Java, Core Java, String]
description: In this article you are going to learn how can one convert the string into an integer using the inbuilt methods of the Integer class.
---

In this article you are going to learn how can one convert the string into an integer using the inbuilt methods of the Integer class. 

## Introduction
We have learned many tutorials on the String class and seen the String operations are an important part of java programming.

Sometimes we took some values as a String but we want to operate them as an Integer, then questions arise how can one convert string to the integer? The Java team provided the solution for it.

Converting a string to integer is one of the most important things to know by a Java Developer.

Now we will see what are the available options to convert a Siring into Integer.

I have listed down two ways to convert a String into an Integer.

1. Using the `Integre.parseInt()` method
2. Using the `Integer.valueOf()` method

Now we will see the above ways to convert string to integer one by one.

## Using the `Integre.parseInt()` method

We can convert the String to an integer using the `Integre.parseInt()` method.

The `Integer.parseInt()` method can convert an entire string to integer provided the String must contain the digit values only. For example `String str= "123";`

Now we will see one example which converts the string to an integer using the `Integre.parseInt()` method.

```java
/*
 * A Java program to convert String to Integer.
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
## Using the `Integer.valueOf()` method

We can also convert String to Integer using the `Integer.valueOf()` method.

The  `Integer.valueOf()` method returns the integer instance of the value represented by the string variable.

Below we will see one program to convert string to int using the `Integer.valueOf()` method.

```java
/*
 * A Java program to convert String to Integer.
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

## Let us know about `NumberFormatException`

When you are trying to convert a string to integer but your string contains a value other than the decimal digits, then bothe the methods (`Integre.parseInt()` method and `Integer.valueOf()` method) will throw the `NumberFormatException`.

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

We can convert String to integer using two methods, `Integre.parseInt()` method and `Integer.valueOf()` method.

If the string contains some other value than the decimal numbers bothe the methods will throw the `NumberFormatException`.

If you found this article worth, support me by  [giving a cup of Coffee ☕](https://www.paypal.me/GauravKukade)

If you know any other way to convert the string to integer or if you have any query about the string to integer conversion please write it down in the comment section below.
