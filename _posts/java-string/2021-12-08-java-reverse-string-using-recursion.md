---
layout: post
title: "How To Reverse A String In Java Using Recursion"
author: gaurav
categories: [Java, String]
description: "In this article, we will see how to reverse a string in java using the recursion."
---
In this article, we will see how to reverse a string in java using the recursion.

We have seen multiple ways to reverse a string in the previous article.

Now we will see how to reverse a string using the recursion.

## A function to reverse the string using the recursion 


```java
public static String reverse(String str) {
    if ((null == str) || (str.length() <= 1)) {
        return str;
    }
    return reverse(str.substring(1)) + str.charAt(0);
}
```

In the above method `reverse()` we are taking String `str` to be reversed.

We are checking if the `str` is null or its length is less than 1. If found, we will return the same string.

Then we are returning the following statement
```java
reverse(str.substring(1)) + str.charAt(0);
```

In the above statement we are calling the `reverse()` function again with  `str.substring(1)` as parameter. And adding the character at `0`th index.


So if we passed the "Hello" String to the function, the call will look like the code below.

```java
reverse("Hello")
(reverse("ello")) + "H"
((reverse("llo")) + "e") + "H"
(((reverse("lo")) + "l") + "e") + "H"
((((reverse("o")) + "l") + "l") + "e") + "H"
(((("o") + "l") + "l") + "e") + "H"
"olleH"
```

## A complete Java Example
The full example java program is as given below.

```java
/**
 * A java program to reverse a striong using recursion.
 * 
 * @author gaurav
 *
 */
public class ReverseStringUsingRecursion {

	public static void main(String[] args) {
		String str = "hello";
		System.out.println(reverse(str));

	}

	public static String reverse(String str) {
	    if ((null == str) || (str.length() <= 1)) {
	        return str;
	    }
	    return reverse(str.substring(1)) + str.charAt(0);
	}
}
```
Output:
```
olleh
```

The example java program given in the above tutorial can be found at [this GitHub Gist](https://gist.github.com/gauravkukade/16388aabb97a4990bd91cd32f3acf9d6).

Please write you thoughts in the comment section below.
