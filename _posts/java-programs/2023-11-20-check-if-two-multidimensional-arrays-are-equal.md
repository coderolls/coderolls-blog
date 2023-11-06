---
layout: post  
title: "Java Program To Check Whether Two Multidimensional Arrays Are Equal"  
author: gaurav  
categories: [Java Programs, Array]  
toc: true
description: "In this tutorial, we will see a Java program to check whether two multidimensional  arrays are equal or not."
---

In this tutorial, we will see a Java program to check whether two multidimensional  arrays are equal or not.

To check whether two multidimensional  arrays are equal or not, we can use the `Arrays.deepEquals()` method.

Also see, [Java Program To Check Whether Two One-dimensional Arrays Are Equal](/check-if-two-arrays-are-equal)

**Java Program**

{% raw %}

```java
import java.util.Arrays;
/**
 * Java program to check if the two multidimensional arrays are equal or not
 * by Arrays.deepEquals() method
 * By coderolls.com
 */
public class MultidimensionalArraysEquals {

    public static void main(String[] args) {

        int[][] arr = {{3, 4, 5, 7}, {123, 2536, 356}};
        int[][] arr2 = {{3, 4, 5, 7}, {123, 2536, 356}};

        System.out.println("Comparing arr and arr2 multidimensional arrays: ");
        boolean isEqual = Arrays.deepEquals(arr, arr2);

        if (isEqual) {
            System.out.println("The multidimensional arrays are equal");
        } else {
            System.out.println("The multidimensional arrays are not equal");
        }
    }
}
```

{% endraw %}

**Output**

```
Comparing arr and arr2 multidimensional arrays: 
The multidimensional arrays are equal
```
