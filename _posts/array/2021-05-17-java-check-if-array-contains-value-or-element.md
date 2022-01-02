---
layout: post
title: " Java: Check If Array Contains Value or Element"
author: gaurav
categories: [Java, Array]
toc: true
description: "In this quick beginner-friendly tutorial, we will see how to check if an array contains a value or an element."
---

In this quick beginner-friendly tutorial, we will see how to check if an array contains a value or an element using the Java Programming Language.

We can check if an element or value is present or not in two types of arrays,
1. For String Array
2. For Primitive Array

## 1. For String Array.

For String Array, we can check if an array contains a particular string value using the `contains()` method.

The code snippet is given below.

```java
Arrays.asList(yourArray).contains(yourValue);
```

I have given a program below that checks if an array contains a particular string value.

```java
import java.util.Arrays;

/**
 * A Java program that checks if a String array contains a particular string value
 * 
 * @author Gaurav Kukade
 *
 */
public class CheckInStringArray {

	public static void main(String[] args) {
	
		String [] names = {"gaurav", "shubham", "krishna", "mayur"};
		
		String checkForString = "mayur";
		
		boolean stringPresentInArray = Arrays.asList(names).contains(checkForString);
		
		if(stringPresentInArray) {
			System.out.println("String value '"+checkForString+"' is present in names Array.");
		}else {
			System.out.println("String value '"+checkForString+"' is not present in names Array.");
		}

	} 
}
```
Output:
```
String value 'mayur' is present in names Array.
```
Check the above code as [GitHub Gist](https://gist.github.com/gauravkukade/1914b7274cd5017364e78d2e6bc5f5bb)

### Java 8 Update

In Java 8, we have Streams API. We can use it to check if a String array contains a particular String value.

I have given a complete program below.

```java
import java.util.Arrays;

/**
 * A Java program that checks if a String array contains a particular string value  
 * using the Java 8 Stream API.
 * 
 * @author Gaurav Kukade
 *
 */
public class CheckInStringArrayUsingStream {

	public static void main(String[] args) {
	
		String [] names = {"gaurav", "shubham", "krishna", "mayur"};
		
		String checkForString = "mayur";
		
		boolean stringPresentInArray = Arrays.stream(names).anyMatch(checkForString::equals);;
		
		if(stringPresentInArray) {
			System.out.println("String value '"+checkForString+"' is present in names Array.");
		}else {
			System.out.println("String value '"+checkForString+"' is not present in names Array.");
		}		
	}
}
```
Output:
```
String value 'mayur' is present in names Array.
```
Check the above code as [GitHub Gist](https://gist.github.com/gauravkukade/3df7496b88b2222ab34d685f5287e725)

## 2. For Primitive Array

When we have to check if a primitive array (int[], long[], char[], etc) contains any particular primitive values,  we have to loop over the array and check the condition manually. ( Till Java 7)

I have given a program below that shows how to check if a primitive array (int[], long[], char[], etc) contains a primitive value or not.

```java
/**
 * A Java program to check if a primitive array contains a primitive value
 * 
 * @author Gaurav Kukade at coderolls.com
 *
 */
public class CheckInPrimitiveArray {

	public static void main(String[] args) {
		
		int[] numbers = {1, 2, 3, 4, 5, 6, 7};
		
		int intToCheck = 5;
		boolean contains = false;
		
		for(int number: numbers) {
			// check if number and intToCheck are equal,
			// if yes make contains as true and break the loop
			if(number == intToCheck) {
				contains = true;
				break;
			}
		}
		
		if(contains){
		    System.out.println("The numbers array contians the value '"+intToCheck+"'.");
		}else {
			System.out.println("The numbers array does not contian the value '"+intToCheck+"'.");
		}
	}
}
```
Output:
```
The numbers array contians the value '5'.
```
Check the above code as [GitHub Gist](https://gist.github.com/gauravkukade/7cf0ba43baccbc9e828277c19f5c14a7)

### Java 8 Update 


In Java 8, we have Streams API. We can use it check if a primitive array (int[], long[], char[], etc) contains a primitive value.

We can use classes like `IntStream`, `DoubleStream` or `LongStream`  to check whether an array contains `int`, `double` or `long` values respectively.

I have given a complete program below.

```java
/**
 * A Java program to check if a primitive array contains a primitive value
 * using the Java 8 Stream API
 * 
 * @author Gaurav Kukade at coderolls.com
 *
 */
public class CheckInPrimitiveArrayUsingStream {

	public static void main(String[] args) {
		
		int[] numbers = {1, 2, 3, 4, 5, 6, 7};
		
		int intToCheck = 2;
		boolean contains = IntStream.of(numbers).anyMatch(x -> x == intToCheck);
		
		if(contains){
		    System.out.println("The numbers array contians the value '"+intToCheck+"'.");
		}else {
			System.out.println("The numbers array does not contian the value '"+intToCheck+"'.");
		}
        }
}
```
Output:
```java
The numbers array contians the value '2'.
```
Check the above code as [GitHub Gist](https://gist.github.com/gauravkukade/e2f15eea99ddb869b406ba90f439e419)

## Check if an array contains a value using the 'Apache Commons Lang' library


Apache Commons Lang library has useful functions to manipulate the array.  

It is not recommended to add a new dependency just to check if your array contains a value.

You can go with Apache Commons Lang library to perform such a simple operation if,

-   If your project is not using Java 8
-   it already has a dependency on the 'Apache Commons Lang library'

Since Apache Commons Lang library' is the most commonly used library, there are chances that your project may already have it.
```
<!-- https://mvnrepository.com/artifact/org.apache.commons/commons-lang3 -->
<dependency>
    <groupId>org.apache.commons</groupId>
    <artifactId>commons-lang3</artifactId>
    <version>3.11</version>
</dependency>
```

If you want to check if an array contains a value using the Apache commons Lang Library utility functions, you can do it as given below.

```java
import org.apache.commons.lang3.ArrayUtils;

/**
 * A java program to check if an array contains a value suing the 
 * Apache common lang library's ArrayUtils.contains() method
 * 
 * @author Gaurav Kukade at coderolls.com
 *
 */
public class ArrayUtilsExample {

	public static void main(String[] args) {
		
		// check in primitive ( int[]) array
		int[] numbers = {1, 2, 3, 4, 5, 6, 7, 8, 9};
		int intToCheck = 8;
		
		boolean containsInt = ArrayUtils.contains(numbers, intToCheck);
		
		if(containsInt){
		    System.out.println("The numbers array contians the value '"+intToCheck+"'.");
		}else {
			System.out.println("The numbers array does not contian the value '"+intToCheck+"'.");
		}
		
		// check in String array
		String[] names = {"gaurav", "shubham", "krishna", "mayur"};
		String stringToCheck = "gaurav";
		
		boolean containsString = ArrayUtils.contains(names, stringToCheck);
	
		if(containsString) {
			System.out.println("String value '"+stringToCheck+"' is present in names array.");
		}else {
			System.out.println("String value '"+stringToCheck+"' is not present in names array.");
		}	
	}
}
```
Output:
```
The numbers array contians the '8' value.
String value 'gaurav' is present in names array.
```
Check the above code as [GitHub Gist](https://gist.github.com/gauravkukade/a93dd0faec3bebd75fa9833d5089d482)

## Conclusion

We have seen all the possible ways to check if an array contains a value or not in Java.

We will summarize these ways below

### 1. For String array

We can use the following code snippet.
```java
Arrays.asList(yourArray).contains(yourValue);
```
From Java 8 we can use Stream API to check if an array contains a value. 
```java
String [] names = {"gaurav", "shubham", "krishna", "mayur"};
boolean stringPresentInArray = Arrays.stream(names).anyMatch("mayur"::equals);;
```

### 2.  For Primitive Array

To check if a primitive array contains a value, we can use the simple for loop and add a equals condition in the loop.

```java
int[] numbers = {1, 2, 3, 4, 5, 6, 7};
boolean contains = false;

for(int number: numbers) {
	if(number == 4) {
		contains = true;
		break;
	}
}
```
From Java 8, we can use classes like `IntStream`, `DoubleStream` or `LongStream`  to check whether an array contains `int`, `double` or `long`  value respectively.
```java
int[] numbers = {1, 2, 3, 4, 5, 6, 7};
boolean contains = IntStream.of(numbers).anyMatch(x -> x == 3);
```

### Check using the `ArrayUtils.contains()` method of 'Apache common Lang' Library

You can use the `ArrayUtils.contains()` method of Apache common Lang Library to check if an array contains a value.

```java
int[] numbers = {1, 2, 3, 4, 5, 6, 7, 8, 9};
boolean containsInt = ArrayUtils.contains(numbers, 7);

String[] names = {"gaurav", "shubham", "krishna", "mayur"};
boolean containsString = ArrayUtils.contains(names, "gaurav");
```
I hope this article will help you to check if an array contains a value in Java.

If you have any other ways to check check if an array contains a value or element using java programming language, please comment below.

You can check my YouTube channel [here](https://www.youtube.com/channel/UCl31HHUdQbSHOQfc9L-wo3w)
 
