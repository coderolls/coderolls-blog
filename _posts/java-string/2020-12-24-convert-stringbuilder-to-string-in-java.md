---
layout: post
title: "How To Convert StringBuilder To String In Java?"
author: gaurav
image: assets/images/2020-12-24/convert-stringbuilder-to-string-in-java.webp
categories: [ Java, Core Java, String]
description: "In this article you will see, how to convert a StringBuilder to String in Java."
featured: false
---
In this article you will see, how to convert a StringBuilder to String in Java.

## Introduction

Java `StringBuilder` is non-synchronized update of the `StringBuffer` class.

Sometimes there is need to convert the `StringBuilder` object to the `String`. We can do it easily by smply invoking the `toString()` method.

Let see the example program below.

## Java Program to convert `StringBuilder` to `String`

```java
/**
 * A Java program to convert StringBuilder to String
 * @author Gaurav Kukade at cderlls.com
 *
 */
public class StringBuilderToString {

	public static void main(String[] args) {
		StringBuilder stringBuilder = new StringBuilder("Hello ");
		
		stringBuilder.append("Gaurav ")
		.append("Kukade!");
		
		System.out.println("Printing strinBuilder as String: \n");
		System.out.println(stringBuilder.toString());

	}

}
```
Output: 
```java
Printing strinBuilder as String: 

Hello Gaurav Kukade!

```
Get the [above code as GitHub Gist](https://gist.github.com/gauravkukade/00bd416bcb2ca1c72dbcd600d48e2f78).

---------

You can visit my [YouTube channel 'coderolls'](https://www.youtube.com/channel/UCl31HHUdQbSHOQfc9L-wo3w?view_as=subscriber?sub_confirmation=1) to find more video tutorials.
