---
layout: post
title: "How To Compare Two Strings Lexicographically In Java"
author: gaurav
categories: [ Java, Core Java, String]
description: "In this article, we will learn how to compare two strings lexicographically in java."
featured: false
comments: true
hidden: false
---

In this article, we will learn how to compare two strings lexicographically in java.

## Introduction

First of all, we will understand what does ‘lexicographically’ means?

In simple words ‘lexicographically’ means ‘alphabetically ordered’. Yes, correct. The order in which words are given in the dictionary.

We are going to compare two strings so we can check their lexicographical order.

There are two ways to compare two strings lexicographically
1. Using the Java `compareTo()` method
2. By creating a user-defined method

Let us start with the first option

## 1. Using the Java `compareTo()` method
Java `compareTo()` method Compares two strings lexicographically, The comparison is based on the Unicode value of each character in the strings.

The character sequence represented by the String object is compared lexicographically to the character sequence represented by the argument string.

![Showing which one is the argument string](/assets/images/2019-11-30/compareto-method-string-def.webp)

```java
int compareTo(T o)
where is 'T' is type and 'o' is obejct
returns - a negative integer, 0 or a positive integer

ex. firstString.compareTo(secondString)

// here character sequence of the firstString is compared lexicographically with the character sequence of the secondString
```
`compareTo()` returns the integer (`int`) value. The possible values are a negative integer, zero or a positive integer.

1. If `firstString` is less than the `secondString`, it will return a negative integer.
i.e `firstString` < `secondString`→ returns a negative integer

2. If `firstString` is equal to the `secondString` it will return zero.
i.e `firstString` == `secondString` → returns zero

3. If `firstString` is greater than the `secondString` it will return a positive integer.
i.e `firstString` > `secondString` → returns a positive integer

Note: Always consider ‘Argument string’ as the reference to counting form for the sign of the value.

Java program to check two strings `lexicographically` using Java `compareTo()` method
```java
/**
 * A Java program to compare two strings lexicographically
 * using compareTo() library function.
 * 
 * @author Gaurav Kukade at coderolls.com
 */
public class CompareLexicographically {
  public static void main(String[] args) {
    
    String firstString = "Paneer";
    String secondString = "Paneer";
    String thirdString = "Butter";
    String fourthString = "Cheese";
    
    System.out.println("Comparing two strings lexicographically.");
    
    System.out.print("\nCompairing character sequence of the firstString ("+firstString+") to the character sequence of the secondString ("+secondString+") returns: ");
    System.out.println(firstString.compareTo(secondString));
    
    System.out.print("\nCompairing character sequence of secondString ("+secondString+") to the character sequence of thirdString ("+thirdString+") returns: ");
    System.out.println(secondString.compareTo(thirdString));
    
    System.out.print("\nCompairing character sequence of thirdString ("+thirdString+") to the character sequence of fourthString ("+fourthString+") returns: ");
    System.out.println(thirdString.compareTo(fourthString));
    
    System.out.print("\nCompairing character sequence of fourthString ("+fourthString+") to the character sequence of firstString ("+firstString+") returns: ");
    System.out.println(fourthString.compareTo(firstString));    
  }
}
```
View CompareLexicographically.java as GitHub Gist.

Output :

```java
Comparing two strings lexicographically.

Compairing character sequence of the firstString (Paneer) to the character sequence of the secondString (Paneer) returns: 0

Compairing character sequence of secondString (Paneer) to the character sequence of thirdString (Butter) returns: 14

Compairing character sequence of thirdString (Butter) to the character sequence of fourthString (Cheese) returns: -1

Compairing character sequence of fourthString (Cheese) to the character sequence of firstString (Paneer) returns: -13
```
Explanation:
1. In first case,`compareTo()` method returns zero since firstString and secondString are same.
2. In second case, `compareTo()` method returns 14 since secondString follows thirdString by 14 characters. The pictorial explanation for this case is given below.
![An explanation for the second case of the java program for `compareTo()` method](/assets/images/2019-11-30/comapreto-method-secondstring-compareto-thirdstring.webp)

3. In third case, `compareTo()` method returns -1 since thirdString precedes fourthString by 1 character.
4. In last case, `compareTo()` method returns -13 since fourthString precedes firstString by 13 characters. The pictorial explanation for this case is given below.

![An explanation for the fourth case of the java program for `compareTo()` method](/assets/images/2019-11-30/comapreto-method-fourthString-compareto-firstString.webp)

## 2. By creating a user-defined method

You can create a method that will compare two strings lexicographically.

First, we will see the logic, how can we build the logic for our user-defined method. I have given the step by step logic below.

1. Get the length of the shorter string in an integer variable lim.

2. Apply while loop for condition `k`<`lim` where k is integer variable initiated with 0.

3. Apply if condition to check if the character at an index k of both the strings is not similar; if the condition returns the difference between these two characters.
  
   We will cast the difference as integer value so that the difference between the Unicode value of character will be return.

4. If the if condition is false, the while loop will continue for the rest of the iterations until condition is true i.e `k`<`lim`.

5. If the if condition is false for all iterations, return the difference between two strings.

I have given the program with a user-defined method `comapreString` below
```java
/**
 * The Java program to compare two strings lexicographically
 * by creating user defined function.
 * 
 * @author Gaurav Kukade at coderolls.com
 */
public class CompareLexicographicallyWithUserDefinedFunction {
  public static void main(String[] args) {
    
    String firstString = "Paneer";
    String secondString = "Paneer";
    String thirdString = "Butter";
    String fourthString = "Cheese";
    String fifthString = "PaneerButter";
    
    System.out.println("Comparing two strings lexicographically by user defined function");
    
    System.out.print("\nCompairing firstString ("+firstString+") to the secondString ("+secondString+") returns: ");
    System.out.println(compareString(firstString, secondString));
    
    System.out.print("\nCompairing secondString ("+secondString+") to the thirdString ("+thirdString+") returns: ");
    System.out.println(compareString(secondString, thirdString));
    
    System.out.print("\nCompairing thirdString ("+thirdString+") to the fourthString ("+fourthString+") returns: ");
    System.out.println(compareString(thirdString, fourthString));
    
    System.out.print("\nCompairing fourthString ("+fourthString+") to the firstString ("+firstString+") returns: ");
    System.out.println(compareString(fourthString, firstString));
    
    // Edge case comparing Paneer & PaneerButter
    System.out.print("\nCompairing firstString ("+firstString+") to the fifthString ("+fifthString+") returns: ");
    System.out.println(compareString(firstString, fifthString));
  }
  
  /*
   * User defined function to compare two string lexicographically
   */
  
  public static int compareString(String str, String argumentString) {
    
    int lim= Math.min(str.length(), argumentString.length());
    
    int k=0;
    while(k<lim) {
      if(str.charAt(k)!= argumentString.charAt(k)) {
        return (int) str.charAt(k)- argumentString.charAt(k);
      }
      k++;
    }
    return str.length() - argumentString.length();
  }
}
```
Output:
```java
Comparing two strings lexicographically by user defined function

Compairing firstString (Paneer) to the secondString (Paneer) returns: 0

Compairing secondString (Paneer) to the thirdString (Butter) returns: 14

Compairing thirdString (Butter) to the fourthString (Cheese) returns: -1

Compairing fourthString (Cheese) to the firstString (Paneer) returns: -13

Compairing firstString (Paneer) to the fifthString (PaneerButter) returns: -6
```
## Conclusion
We have seen how to compare two strings lexicographically in Java. As per the articles, there are two ways to do the same
1. Using the Java `compareTo()` method
2. By creating a user-defined method

In a first way, I am using the `compareTo()` method of the Java and in the second way I have created the user-defined method `compareToString()`.

Most noteworthy, In `compareTo()` method of the Java, the comparison is based on the Unicode value of each character in the strings.

If you found this article worth, please [Give me a cup of Coffee ☕](https://www.paypal.me/GauravKukade)

Have you tried the `compareTo()` method or created a user-defined method to compare two string lexicographically? How was your experience? Have you faced any problem? please write down the same in the comment section below.
