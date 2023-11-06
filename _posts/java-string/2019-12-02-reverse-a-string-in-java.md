---
layout: post
title: "How To Reverse A String In Java (5 ways)"
author: gaurav
categories: [ Java, Core Java, String]
description: "In this article, we will learn how to reverse strings in Java. I have write down 5 diffrent ways to reverse strings. Have a look!"
featured: true
toc: true
---

In this article, we will learn how to reverse strings in Java. I have write down 5 diffrent ways to reverse strings. Have a look!

## Introduction

This question is simple but important since it is asked in most of the java interviews. You will be asked to reverse a string using a ready to use library method (like `reverse()` of `StringBuilder`) or without using a library method. In this article, we will see both ways.

Below I have listed the 5 ways to reverse a string in Java. In all 5 cases, I will explain the step by step logic and gave the Java program for the same.

1. Using charAt() method of String

2. Using getBytes() method of String

3. Using toCharArray() method of String

4. Using reverse() method of StringBuilder

5. Using reverse() method of Collections

## 1. Using `charAt()` method of String
`charAt()` method of the Java String returns character value at the specified index of the string.
```java
public char charAt(int index)

where 'index' is the index of the character specified

returns - char at specified index

ex.
String blogName = "codeRolls.com";
char returnedChar = blogName.charAt(3); // returns e
```
I hope you have understood how the `charAt()` works, now we will see how can we use the same `charAt()` method to reverse the string.

1. Declare a string that you have to reverse. eg. `blogName`

2. Initialize an empty string with the name `reversedString`.

3. Apply `for` loop to get the characters of the `blogName` in the reverse order i.e `int i = blogName.length()-1; i <= 0; i- -;`

4. Inside the for loop append each character with the `reversedString`.

5. Print the `reversedString`.

A Java program to reverse the string using `charAt()` method of the String class is given below
```java
/**
 * A Java program to reverse a string.
 * We are using 'charAt()' method of the String class to get all char and arrange it in
 * descending order to get a reverse string.
 * 
 * @author Gaurav Kukade at coderolls.com
 */
public class ReverseString {
  public static void main(String[] args) {
    
    String blogName = "coderolls.com";
    String reversedString = "";
    
    for(int i = blogName.length()-1; i>=0; i--){
      reversedString = reversedString + blogName.charAt(i);
    }
    
    System.out.print("The reversed string of the '"+blogName+"' is: " );
    System.out.println(reversedString);
  }
}
```

Output:
```java
The reversed string of the 'coderolls.com' is: moc.slloredoc
```

#### Note:
In the `for` loop, I have assigned `blogName.length()-1` to i instead of `blogName.length()` because the characters in the string are indexed from 0.

I have given an image below to show the string indexing.

![Showing indexes of the characters in the string.](/assets/images/2019-12-02/string-indexing.webp)

Also you can watch [the video on my youtube channel for reverse a string with the above method](https://www.youtube.com/watch?v=vrTYrQuB0BE).

<iframe width="560" height="315" src="https://www.youtube.com/embed/vrTYrQuB0BE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


## 2. Using `getBytes()` method of String
In the `getBytes()` method of Java String first encodes the specified string into the sequence of bytes using the platforms default charset and then save the result in the byte array. The same byte array will be returned.
```java
public byte[] getBytes()

It encodes the string into sequence of the bytes and return the byte array with this result

returns - byte array of the encoded sequence of bytes

ex.
String blogName = "coderolls.com";
byte [] stringByteArray = blogName.getBytes();
```
Now we will see the step by step logic to reverse the string using the `getBytes()` method

1. Declare a string that you have to reverse. eg. `blogName`

2. Create a `byte []` to store the byte array of the specified string. Let say `stringByteArray`

3. Create another `byte []` with the same length of the previous `byte [] stringByteArray`. Let say `reversedStringByteArray`

4. Create a string `reversedString`.

5. Apply for loop to iterate over `stringByteArray`.

6. Using for loop set all the elements of the `stringByteArray` in reverse order with `reversedStringByteArray`.

7. Create a new String object using `reversedStringByteArray` and assign it to the `reversedString`.

8. Print `reversedString`.

The program to reverse the string using `getBytes()` method of the Java String is given below
```java
/**
 * A Java program to reverse a string.
 * 
 * We are using 'getByets()' method of the String class to get byte array of the specified string
 * and assign it to the another byte array of the same length in the descending order.
 * 
 * New String object of the reversed byte array will give reversed string.
 * 
 * @author Gaurav Kukade at coderolls.com
 */
 
public class ReverseStringUsingGetBytes {
  public static void main(String[] args) {
    
    String blogName = "coderolls.com";
    byte[] stringByteArray = blogName.getBytes();
    byte[] reverseStringByteArray = new byte[stringByteArray.length] ;
    String reversedString;
    
    for(int i = 0;  i<=stringByteArray.length-1; i++) {
      reverseStringByteArray [i] = stringByteArray[stringByteArray.length-i-1];
    }
    
    reversedString = new String(reverseStringByteArray);
    
    System.out.print("The reversed string of the '"+blogName+"' is: " );
    System.out.println(reversedString);
  }
  
}
```

Output:
```java
The reversed string of the 'coderolls.com' is: moc.slloredoc
Note: Like character indexing of the string, elements of the array starts from 0; that’s why I have used stringByteArray.length-1 in the for loop.
```
## 3. Using toCharArray() method of String

`toCharArray()` is an instance method of the String class in Java.

`toCharArray()` method returns a new character array of the string specified.
```java
public char [] toCharArray()

This method converts the string into new character array of the same length containing the character sequence represented by the string.

returns - new char array containing character sequence represented by the string.
Now we will see how can we use the toCharArray() method to reverse the string.
```
Below I have given the step by step logic for the program to reverse string using `toCharArray()` method.

1. Declare a string that you have to reverse. eg. `blogName`

2. Create a new char array using the `blogName` string. eg. `stringCharArray`

3. Create an empty string, we will be using that string to append with elements of the `stringCharArray`. Let say the empty string is `reversedString`.

4. Apply for loop to iterate `stringCharArray` in the reverse order.

5. In the for loop, append the `reversedString` with the `i`th element of the `stringCharArray`.

6. Print the `reversedString`.

I have given the program as per the above logic.
```java
/**
 * A Java program to reverse a string.
 * 
 * We are using 'toCharArray' method of the String class to get char array of the specified string
 * and append it with the temp string in reverse order.
 * 
 * @author Gaurav Kukade at coderolls.com
 */
public class ReverseStringUsingToCharArray {
  public static void main(String[] args) {
    
    String blogName = "coderolls.com";
    char [] stringCharArray = blogName.toCharArray();
    String reversedString = "";
    
    for(int i = stringCharArray.length-1; i>=0; i--) {
      reversedString = reversedString + stringCharArray[i];
    }
    
    System.out.print("The reversed string of the '"+blogName+"' is: " );
    System.out.println(reversedString);
  }
}
```

Output:
```java
The reversed string of the 'coderolls.com' is: moc.slloredoc
```
## 4. Using reverse() method of StringBuilder

`reverse()` method of the `StringBuilder` class replaces the character sequence represented by a string in the reverse order.
```java
public StringBuilder reverse()

reverse() method reverse the char sequence of the string

return - reference to the StringBuilder object with reverse char sequence
```
I have given the step by step logic for the program to reverse the string using `reverse()` method of `StringBuilder` class.

1. Declare a string that you have to reverse. eg. `blogName`

2. Create a new instance of the `StringBuilder` class as a `stringBuilder` using `blogName` string.

3. Apply `reverse()` on the `stringBuilder` instance and assign it to the same `stringBuilder` instance.

4. Print the `stringBuilder` instance.

I have written the Java program to reverse the string using `reverse()` method of the `StringBuilder` class below.
```java
/**
 * A Java program to reverse a string.
 * 
 * We are using 'reverse()' method of the StringBuilder class. This method rverse the
 * character sequence represented by the string.
 * 
 * @author Gaurav Kukade at coderolls.com
 */
 
public class ReverseStringUsingReverseMethodOfStringBuilder {
  public static void main(String[] args) {
    
    String blogName = "coderolls.com";
    
    StringBuilder stringBuilder = new StringBuilder(blogName);
    
    String reversedString = stringBuilder.reverse().toString();
    
    System.out.print("The reversed string of the '"+blogName+"' is: ");
    System.out.println(reversedString);
  }
}
```

Output:
```java
The reversed string of the 'coderolls.com' is: moc.slloredoc
```
## 5. Using reverse() method of Collections

`reverse()` method of the Collections take list as a parameter and reverse the order of elements.
```java
public static void reverse(List<?> list)

this method reverse the order of elements in the specified list

parameters
list - list whose elements you have to reverse
```
The logic for the program to reverse a string using the `reverse()` method of the Collections is given below.

1. Declare a string that you have to reverse. eg. `blogName`

2. Create a new char array using the `blogName` string. eg. `stringCharArray`

3. Create a new `ArrayList`. eg. `arrayList`

4. Create an empty string, we will be using that string to append with elements of the `arrayList`. Let say the empty string is `reversedString`.

5. Apply `forEach` loop to iterate over the `stringCharArray`. In the `forEach` loop add each element of the `stringCharArray` to `arrayList`

6. Use`reverse()` method of the Collections to reverse the order of elements in `arrayList`.

7. Apply `forEach` loop to iterate over `arrayList`. In the `forEach` loop append the `reversedString` with each element of the `arrayList`.

8. Print `reversedString`.

The program for the above logic is given below.
```java
/**
 * A Java program to reverse a string.
 * 
 * We are using 'reverse()' method of the Collections. This method reverse the
 * order of elements of the list specified.
 * 
 * @author Gaurav Kukade at coderolls.com
 */
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;
public class ReverseStringUsingReeverseMethodOfCollections {
  public static void main(String[] args) {
    
    String blogName = "coderolls.com";
    char [] stringCharArray = blogName.toCharArray();
    List<Character> arrayList = new ArrayList<>();
    String reversedString = "";
    
    for(char ch : stringCharArray) {
      arrayList.add(ch);
    }
    
    Collections.reverse(arrayList);
    
    for( Character ch: arrayList) {
      reversedString = reversedString + ch;
    }
    
    System.out.print("The reversed string of the '"+blogName+"' is: ");
    System.out.println(reversedString);  
  }
  
}
```
Output:
```java
The reversed string of the 'coderolls.com' is: moc.slloredoc
```
So we have seen all five ways to reverse the string in Java.

## Conclusion
We can reverse the string in multiple ways. I have listed the five ways below.

1. Using `charAt()` method of String

   In the first way, we have used `charAt()` method to get every character of the specified string and append it to an empty string in the reveres order.

2. Using `getBytes()` method of String

   In a second way, I have converted a string into byte Array and created another byte array with same length. Then I have inserted elements of byte array in the new byte array in the reverse order. Finally, convert new byte array to string to get the reverse string.

3. Using `toCharArray()` method of String

   In a third way, I have converted the string to the character array using the `toCharArray()` method. Then I have to append and an empty string with every character of the character array in the reverse order.

4. Using reverse() method of `StringBuilder`

   In a fourth way, I have created a `stringBuilder` instance using the string, which I have to reverse. And finally, I have used the `reverse()` method of the `StringBuilder` class to get the reversed string.

5. Using reverse() method of Collections

   In the last way, I have created an `ArrayList` using the string, which I have to reverse. Then I have used `reverse()` method of the Collections to reverse the order of elements in the `ArrayList`. And finally, I have appended an empty string with every element of the `ArrayList` to get the reversed string.

These are the ways we can reverse the string in Java.

If you have any queries or any suggestions or if you find any mistakes in the article or in the code snippet given above please feel free to comment below.

Have you  try the different ways to reverse the string in the java? or do you know the most simple way? please write it down in the comment section below.
