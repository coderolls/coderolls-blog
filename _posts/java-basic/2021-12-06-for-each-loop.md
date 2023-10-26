---
layout: post
title: "For-each loop in Java or Enhanced For loop in Java"
author: gaurav
categories: [Java, Control Flow Statements]
toc: true
description: "In this article, we will see the for-each loop in java i.e. Enhanced for loop"
---
In this article, we will see the for-each loop in java i.e. Enhanced for loop

## Introduction

For-each loop is introduced in Java 1.5.

It provides a better approach to traversing the array or collection.

In a simple for loop, we initialize the variable and write the condition for that variable. But in for each loop, we do not have to initialize a variable or write any condition for that.

The foreach loop is always used to traverse over the array or any collection.

The for-each loop i.e. enhanced for loop will automatically traverse for each element of the array or collection.

I have given the syntax for the for-each loop below.

```java
for(DataType item : Array | Collection){
	//We have the item with us to operate
}
``` 

## Examples

I have given a simple Java program to traverse over an array using the for-each loop i.e. enhanced for loop.

```java
/**
 * A Java program to traverse the array using the 
 * for-each loop i.e. enhanced for loop
 * 
 * @author Guarav Kukade at coderolls.com
 *
 */
public class ArrayForEachExample {

	public static void main(String[] args) {
		
		//Create an array of marks
		int[] numbers = { 88, 95, 65, 76, 78, 45, 95, 96, 56};
		
		// traversing the array using for-each loop
		for(int number: numbers) {
			
			System.out.println("The number is "+ number);
		}
	}
}
```
Output:
```
The number is 88
The number is 95
The number is 65
The number is 76
The number is 78
The number is 45
The number is 95
The number is 96
The number is 56
```


Also, I have given a Java program below to traverse a collection using the for-each loop i.e. enhanced for loop.

```java
import java.util.ArrayList;
import java.util.List;

/**
 * A Java program to traverse the collection using
 * the for-each loop i.e. enhanced for loop
 * 
 * @author Gaurav Kukade at coderolls.com
 *
 */
public class ArrayListForEachExample {

	public static void main(String[] args) {
		
		//Create an empty ArrayList of Integer
		List<Integer> numbers = new ArrayList<Integer>();
		
		//add number to the list
		numbers.add(1);
		numbers.add(8);
		numbers.add(8);
		numbers.add(5);
		numbers.add(4);
		numbers.add(6);
		numbers.add(3);
		numbers.add(2);
		numbers.add(9);
		
		//traversing the collection using for-each loop
		for(Integer number: numbers) {
			System.out.println("The number is "+ number);
		}
	}
}
```
Output:
```
The number is 1
The number is 8
The number is 8
The number is 5
The number is 4
The number is 6
The number is 3
The number is 2
The number is 9
```

## Conclusion

For-each loop i.e. enhanced for loop can be used to traverse over the array or collection.

It provides a more readable syntax as compared to the simple for loop.

The example Java program used in the above article can be found at [this GitHub repository.](https://github.com/coderolls/blogpost-coding-examples/tree/main/java-basic/for-each-loop)

Please write down your thoughts in the comment section below.
