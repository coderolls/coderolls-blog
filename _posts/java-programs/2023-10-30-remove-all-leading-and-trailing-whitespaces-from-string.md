---
layout: post  
title: "Java Program To Remove All Leading and Trailing Whitespaces From The Given String."  
author: gaurav  
categories: [String, Java Programs]  
toc: true
description: "In this tutorial, we will see how to remove all the leading and trailing whitespaces from the given String."
---

In this tutorial, we will see how to remove all the leading and trailing whitespaces from the given String.

## Introduction

We can remove all the leading and trailing spaces from the string in two ways,

1. Using the regex expressions with `String.replaceAll()`
2. Using the ready-made `String.trim()` method

### 1. Using the regex expressions with `String.replaceAll()`

We can use the following regex expressions to remove leading and trailing whitespaces from the given input string.

We are simply replacing all leading and trailing whitespaces with empty strings.

`^\s+` - remove all leading whitespaces

`\s+$` - remove all trailing whitespaces

**Java program**

```java
/**
 * A Java program to remove all the leading and trailing
 * whitespaces from the given string using the String.replaceAll() method.
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

        //Removing all leading whitespace
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

The example String is given below: 
---     Let's learn Java   ---

The example String after removing the leading and trailing spaces is as given below: 
---Let's learn Java---
```

### 2. Using the ready-made `String.trim()` method

**We can remove all the leading (at the start of the sting ) and trailing (at the end of the string) using the `String.trim()` method.**

It is a simple way as compared to 1st way.

Here are using the ready-made method and we do not need to remember the regex expression to find all the leading and trailing spaces.

**Java Program**

```java
/**
 * A Java program to remove all the leading and trailing
 * whitespaces from the given string using the String.trim() method.
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

        String result  = exampleString.trim();
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

## Conclusion

We can remove all the leading and trailing whitespaces from the given String as follows.

1. replace all the leading and trailing whitespaces with an empty string
   ```java
   result = exampleString.replaceAll("^\\s+", ""); // remove leading whitespaces
   result = result.replaceAll("\\s+$", ""); // then removes trailing whitespaces
   ```

2. Use the ready-made `String.trim()` method.
   ```java
   String result  = exampleString.trim();
   ```

   
