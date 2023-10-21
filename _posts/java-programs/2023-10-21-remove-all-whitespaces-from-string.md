---
layout: post  
title: "Java Program To Remove All Whitespaces From The Given String."  
author: gaurav  
categories: [String, Java Programs]  
toc: true
description: "In this tutorial, we will see how to remove all whitespaces from the given String."
---



## Remove whitespaces from all over the String

We can replace all whitespaces with empty string using `String.replaceAll() method. 

The replace all methods accepts regex string and replacement string as input params. And return the replaced string.

We can use `"\\s+"` regex expression to find all the whitespaces from the given input string. 

**Java Program**

```java
/**
 * A java program to remove all the whitespaces from the given string.
 * By coderolls.com
 */
public class RemoveWhitespaces {

    public static void main(String[] args) {

        String exampleString = "It is an example string.";

        System.out.println("The example String is as given below: ");
        System.out.println(exampleString);

        // remove all whitespaces from example string
        String stringWithoutWhitespaces = exampleString.replaceAll("\\s+", "");

        System.out.println("\nThe example String after removing all the whitespaces is as given below: ");
        System.out.println(stringWithoutWhitespaces);
    }
}
```

**Output**

```
The example String is as given below: 
It is an example string.

The example String after removing all the whitespaces is as given below: 
Itisanexamplestring.
```