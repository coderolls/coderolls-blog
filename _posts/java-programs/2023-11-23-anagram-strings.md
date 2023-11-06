---
layout: post  
title: "Java Program To Check If Two Strings are Anagram"  
author: gaurav  
categories: [Java Programs, String]  
toc: true
description: "In this tutorial, we will see a Java program to check if two strings are anagrams."
---

Here, we will see a Java program to check if two strings are anagrams.

If two Strings have the same set of characters, then these are anagram Strings.

Let's see a Java program to check two Strings are anagrams.

**Java Program**

```java
import java.util.Arrays;

/**
 * Java program to check if the two strings are anagrams or not
 * By coderolls.com
 */
public class AnagramStrings {

    public static void main(String[] args) {

        String str1 = "race";
        String str2 = "care";

        System.out.println("Comparing str1 and str2 if they are anagram strings: ");
        boolean result1 = isAnagram(str1, str2);
        if (result1) {
            System.out.println("The two strings " + str1 + " and "+ str2 + " are anagram strings");
        } else {
            System.out.println("The two strings '" + str1 + "' and '"+ str2 + "'  are not anagram strings");
        }
    }

    private static boolean isAnagram(String string1, String string2) {
        //String with different lengths can't be an anagram string
        if (string1.length() != string2.length()) {
            return false;
        }
        char[] arr1 = string1.toCharArray();
        char[] arr2 = string2.toCharArray();
        Arrays.sort(arr1);
        Arrays.sort(arr2);
        return Arrays.equals(arr1, arr2);
    }

}
```

**Output**

```
Comparing str1 and str2 if they are anagram strings: 
The two strings race and care are anagram strings
```
