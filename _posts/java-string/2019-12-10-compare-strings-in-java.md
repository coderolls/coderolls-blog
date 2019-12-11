---
layout: post
title: How Do I Compare Strings In Java
author: gaurav
categories: Java, Core Java, String
description: In this article you are going to learn how to compare strings. What problem occurs when you compare string using `equals to` (`=`)operator.
featured: true
---

In this article you are going to learn how to compare strings. What problem occurs when you compare string using `equals to` (`=`)operator.

## Introduction

The  `String`  is a special Class in Java. We use String regularly in Java programs, so comparing two string is a common practice in Java. In this article I tried to answer the most common questions about the string, ‘How do I compare strings in Java?’

Comparing strings is very helpful the processes like authentication, sorting, reference matching, etc.

I have listed 3 ways to compare strings in Java.

1. Using  `equals()`  method ( comparing the content)

2. Using  `==`  operator (comparing the object reference)

3. Using  `compareTo()`  method (comparing strings lexicographically)

## 1. Compare strings using  `equals()`  method

In this way, I am using  `.equals()`  instance method of the String class. Originally  `.equals()`  method is the  `Object`  class method, String class overrides it.

`**equals()**` **method the compare two strings for value equality, weather they are logically equal.**

`equals()`  method in String class takes another string a parameter and compare it with the specified string, it returns  `true`  if and only if the parameter string is not null and contains the same characters as the specified string.

```
public boolean equals(Object anObject)

It compare this string with the argument strings and return true if the argument is not null and contains the same character as the specified string.

param -
another string

returns -

true - if argument is not null and it contains same characters as the specified string
false - if the argument is null or it does not contain same characters as the specified string

ex. firstString.equals(secondString)
// returns true if and only if the secondString is not null and contains the same characters as firstString.
```

I have given the program to compare string using  `equals()`  method below
```
/**
 * A Java program to compare two strings using equsls()
 * and equalsIgnoreCase() method of the String.
 * 
 * @author Gaurav Kukade at coderolls.com
 */

public class CompareUsingEquals {

  public static void main(String[] args) {
    String firstString = "coderolls";
    String secondString = "javablog";
    String thirdString = "coderolls";
    String fourthString = "CodeRolls";
    
    System.out.println("Comparing strings using equals() and equalsIgnoreCase() method\n");
    
    // Using equals() method
    System.out.print("firstString.equals(secondString) : ");
    System.out.println(firstString.equals(secondString));
    
    System.out.print("firstString.equals(thirdString) : ");
    System.out.println(firstString.equals(thirdString));
    
    /*
     * Using equalsIgnoreCase() method to ignore
     * case consideration (i.e. Capital or small) of both the strings.
     */
    System.out.print("firstString.equalsIgnoreCase(fourthString) : ");
    System.out.println(firstString.equalsIgnoreCase(fourthString));
  }

}
```

Output:

```
Comparing strings using equals() and equalsIgnoreCase() method

firstString.equals(secondString) : false
firstString.equals(thirdString) : true
firstString.equalsIgnoreCase(fourthString) : true
```

## 2. Compare strings using  `==`  operator

**In String,** `**==**` **operator is used to comparing the reference of the given strings, whether they are referring to the same objects.**

When you compare two strings using  `==`  operator, it will return  `true`  if the string variables are pointing toward the same java object, else it will return  `false`.

I have given a Java program to compare using  `==`  operator below
```
/**
 * A Java program to compare strings using == operator.
 * 
 * == operator ckecks weather both the strings referring
 * to the same String Object.
 * 
 * @author Gaurav Kukade at coderolls.com
 */

public class CompareUsingEqualsToOperator {

  public static void main(String[] args) {
    
    String firstString = "coderolls";
    String secondString = "javablog";
    String thirdString = "coderolls";
    
    // creating new String object with the same value as firstString or thirdString
    String fourthString =  new String("coderolls");
    
    System.out.println("Comparing strings using == operator \n");
    
    System.out.print("firstString == secondString : ");
    System.out.println(firstString == secondString);
    
    /*
     * Here firstString and thirdString is referring to the same String object
     * hence it will print 'true'.
     */
    System.out.print("firstString == thirdString : ");
    System.out.println(firstString == thirdString);
    
    /*
     * Here firstString and fourthString have same value
     * but they are referring to the different String object.
     * 
     * hence it will print 'false'
     */
    System.out.print("firstString == fourthString : ");
    System.out.println(firstString == fourthString);
  }
  
}
```

Output:

```
Comparing strings using == operator 

firstString == secondString : false
firstString == thirdString : true
firstString == fourthString : false
```

## Problem with using  `==`  operator for string comparison

Most of the beginner Java developers commit this mistake by comparing two strings using the == operator.

Logically, they have to check whether both the string contains the same character sequence or not.

In Java String, the  `==`  operator used to check the reference of both the string objects and  `equals()`  method used to check the value equality of both strings.

`==`  – checks reference equality

`equals()`  – checks the value equality

When we assign a string value to the string variable JVM will check if the string with the equal value already present in the string pool or not. If it is not present in the string pool, it will be added to the constant pool and the reference to that string object is returned.

If it is present in the string pool, the reference to the memory address of that string object is returned.

The following image shows the pictorial explanation of the same.

!['firstString' pointing towards the "coderolls" string in string pool](/assets/images/2019-12-10/firstString-pointing-to-coderolls-in-string-pool.png)

‘firstString’ pointing towards the “coderolls” string in string pool

If we are assigning the equal value to another string variable, JVM checks if the string with that value is present in the string constant pool or not.

Since the string object with that value is already created in the previous step. Another string variable starts referring to the previously created string object instance.

The following image shows the pictorial explanation for the same

!['firstString' and 'secondString' pointing towards the "coderolls" string in string pool](/assets/images/2019-12-10/secondString-pointing-to-coderolls-in-string-pool.png)

‘firstString’ and ‘secondString’ pointing towards the “coderolls” string in string pool

When we create string using the  `new`  operator, a new string object is created and stored in the Java heap space.

!['firstString' and 'secondString' pointing towards the "coderolls" string in string pool and 'thirdString' pointing towards the "coderolls" in java heap space.](/assets/images/2019-12-10/thirdString-pointing-to-coderolls-in-heap.png)

‘firstString’ and ‘secondString’ pointing towards the “coderolls” string in string pool and ‘thirdString’ pointing towards the “coderolls” in java heap space.t

## 3. Compare strings using  `compareTo()`  method

`compareTo()`  method is used to compare two strings lexicographically. i.e. Alphabetically.

`compareTo()`  method compares the character sequence of the argument string with the character sequence of the specified string.

![Showing argument string and specified string.](https://coderolls.com/wp-content/uploads/2019/08/showing-argument-string-and-specified-string.png)

Showing argument string and a specified string.

It returns a negative integer if the argument string is lexicographically greater than the specified string. i.e if the argument string follows the specified string. ( argument String > specified String )

It returns positive integer if the argument string is lexicographically smaller than the specified string. i.e. If the argument string precedes the specified string. ( argument String < specified String )

It returns zero if both the strings are lexicographical equals. ( argument String = specified String )

If you want to ignore the cases of both the string use  `compareToIgnoreCase()`  method.

I have given a program for comparing strings using the  `compareTo()`  method. It also consists a case for ignoring the cases with  `compareToIgnoreCase()`  method.
```/**
 * A Java program to compare strings using compareTo()
 * and compareToIgnoreCase() method.
 * 
 * compareTo() compare strings lexicograpgically.
 * 
 * @author Gaurav Kukade at coderolls.com
 */

public class CompareUsingCompareTo {

  public static void main(String[] args) {
    
    String firstString = "java";
    String secondString = "coderolls";
    String thirdString = "sql";
    String fourthString = "CodeRolls";
    
    System.out.println("Comparing strings using compareTo() and compareToIgnoreCase() method\n");
    
    // Using compareTo() method
    System.out.print("firstString.compareTo(secondString) : ");
    System.out.println(firstString.compareTo(secondString));
    
    System.out.print("firstString.compareTo(thirdString) : ");
    System.out.println(firstString.compareTo(thirdString));
    
    /*
     * Using compareToIgnoreCase() method to ignore
     * case consideration (i.e. Capital or small) of both the strings.
     */
    System.out.print("secondString.compareToIgnoreCase(fourthString) : ");
    System.out.println(secondString.compareToIgnoreCase(fourthString));
  }

}
```
View  [CompareUsingCompareTo.java as GitHub Gist](https://gist.github.com/gauravkukade/dc40c37e55c6fbad08755e2281dc2ebe).

Output:

```
Comparing strings using compareTo() and compareToIgnoreCase() method

firstString.compareTo(secondString) : 7
firstString.compareTo(thirdString) : -9
secondString.compareToIgnoreCase(fourthString) : 0
```

I have written a detailed article on  [how to compare strings lexicographically in java](https://coderolls.com/compare-two-strings-lexicographically-in-java/). In this article, I have also created a user-defined method to  [compare two strings lexicographically](https://coderolls.com/compare-two-strings-lexicographically-in-java/), please have a look.

## Conclusion

We can compare strings using the ways given below

1. Using  `equals()`  method :  `equals()`  method in the strings used to check the string value equality whether they contain the same character sequence.

2. Using  `==`  operator :  `==`  operator used to check the reference equality of the two strings, whether they are pointing towards the same string object.

3. Using  `compareTo()`  method : `compareTo()`  method used to check the strings lexicographically. I.e alphabetically. Check the detailed articles on  [How to compare strings lexicographically](https://coderolls.com/compare-two-strings-lexicographically-in-java/).

Most of the beginner java developers do mistakes while comparing strings. They actually want to check the content of the string but they use  `==`  operator to check it.

It is always advised to use equals() method to compare the string on the basis of its content.

If you have any query about the code blocks given above, please write it down in the comment section below. Also. let me know if you have any other way to compare two strings in java in the comment section.

### Related Article

-   [How To Reverse A String In Java (5 ways)](https://coderolls.com/reverse-a-string-in-java/)
-   [How To Compare Two Strings Lexicographically In Java](https://coderolls.com/compare-two-strings-lexicographically-in-java/)
-   [Introduction to Java Technology (Language and Platform)](https://coderolls.com/java-introduction/)
