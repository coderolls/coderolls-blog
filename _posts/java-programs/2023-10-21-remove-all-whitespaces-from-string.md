---
layout: post  
title: "Java Program to remove all spaces from the given String."  
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



## Remove all leading and trailing whitespaces from the String



We can remove all the leading trailing spaces from the string in two ways,

1. Using the regex expressing with `String.replaceAll()`
2. Using the ready made `String.trim()` method



### 1. Using the regex expressions with `String.replaceAll()`

We can use following regex expressions to remove leading and trailing whitespaces from the given input string.

`^\s+` - remove all leading whitespaces

`\s+$` - remove all trailing whitespacess

**Java program**

```java
/**
 * A java program to remove all the leading and trailing
 * whitespaces from the given string using String.replaceAll() method.
 * By coderolls.com
 */
public class RemoveLeadingAndTrailingWhitespaces {

    public static void main(String[] args) {

        String exampleString = "     Let's learn Java   ";
        String result = "";

        System.out.println("(We are printing the example string in between the three hyphens" +
                " to show leading and trailing spaces)");
        System.out.println("\nThe example String is as given below: ");

        //We are printing the example string in between the three hyphens
        //to show leading and trailing spaces
        System.out.println("---" + exampleString + "---");

        // removing all leading whitespace
        result = exampleString.replaceAll("^\\s+", "");

        // removing all trailing whitespace from stringWithoutLeadingOrTrailingSpaces
        result = result.replaceAll("\\s+$", "");

        System.out.println("\nThe example String after removing the leading and trailing spaces is as " +
                "given below: ");
        System.out.println("---" + result + "---");
    }
}
```

**Output**

```
(We are printing the example string in between the three hyphens to show leading and trailing spaces)

The example String is as given below: 
---     Let's learn Java   ---

The example String after removing the leading and trailing spaces is as given below: 
---Let's learn Java---
```





### 2. Using the ready made `String.trim()` method

We can remove all the leading (at the start of the sting ) and trailing (at the end of the string) using the `String.trim()` method.

It is a simple way as compare to 1st way.

Here are using the ready made method and we do not need to remember the regex expression for finding all the leading and trailing spaces.

**Java Program**

```java
/**
 * A java program to remove all the leading and trailing
 * whitespaces from the given string using String.trim() method.
 * By coderolls.com
 */
public class TrimMethodExample {

    public static void main(String[] args) {
        String exampleString = "     Let's learn Java   ";

        System.out.println("(We are printing the example string in between the three hyphens to show " +
                "leading and trailing spaces)");
        System.out.println("\nThe example String is as given below: ");

        //We are printing the example string in between the three hyphens 
        //to show leading and trailing spaces
        System.out.println("---" + exampleString + "---");

        String stringWithoutLeadingOrTrailingSpaces = exampleString.trim();
        System.out.println("\nThe example String after removing the leading and trailing spaces is as " +
                "given below: ");
        System.out.println("---" + stringWithoutLeadingOrTrailingSpaces + "---");
    }
}

```

**Output**

```
(We are printing the example string in between the three hyphens to show leading and trailing spaces)

The example String is as given below: 
---     Let's learn Java   ---

The example String after removing the leading and trailing spaces is as given below: 
---Let's learn Java---
```



