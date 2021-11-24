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

#### Related Articles

-   [Learn About Java String Pool And intern() Method](https://coderolls.com/java-string-pool-and-intern-method/)
-   [How Do I Compare Strings In Java](https://coderolls.com/compare-strings-in-java/)
-   [How To Reverse A String In Java (5 ways)](https://coderolls.com/reverse-a-string-in-java/)
-   [Compare Two Strings Lexicographically In Java](https://coderolls.com/compare-two-strings-lexicographically-in-java/)
-   [Difference Between StringBuffer and StringBuilder class](https://coderolls.com/difference-between-stringbuffer-and-stringbuilder/)
-   [8 Basic GIT Commands Every Newbie Developer Must Know](https://coderolls.com/basic-git-commands/)
