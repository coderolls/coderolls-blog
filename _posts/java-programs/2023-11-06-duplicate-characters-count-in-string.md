---
layout: post  
title: "Java Program To Find Duplicate Characters And Their Count In a String."  
author: gaurav  
categories: [String, Java Programs]  
toc: true
description: "In this tutorial, we will see how to find duplicate characters and their count in the string using the Java program."
---

In this tutorial, we will see how to find duplicate characters and their count in the string using the Java program.

We will be iterating over the string and then we will be using the HashMap to store characters and their count as a key and value pair.

**Java Program To Find Duplicate Characters And Their Count Form The String**

```java
import java.util.Map;
import java.util.HashMap;

/**
 * Java program to print duplicate characters and their count
 * By coderolls.com
 */
public class CharactersCount {

    public static void main(String[] args) {

        String exampleString = "This is an example string.";
        System.out.println("The example string is as given below: ");
        System.out.println(exampleString);

        Map<Character, Integer> map  = new HashMap<>();

        for(int i=0; i<exampleString.length(); i++){
            char ch = exampleString.charAt(i);

            if(map.containsKey(exampleString.charAt(i))) {
                //Increase count in character already present
                map.put(ch, map.get(ch)+1);
            } else {
                // else add a character and count as 1
                map.put(ch, 1);
            }

        }

        // printing all the characters and their count
        System.out.println("\nThe duplicate characters and their respective count is as given below: ");

        for (Map.Entry<Character, Integer> entry : map.entrySet()) {
            if (entry.getValue()>1) {
                System.out.println(entry.getKey() + ": " + entry.getValue());
            }
        }

    }
}
```

**Explanation**

1. We have an example string to get duplicate characters and their respective count from it.
2. We have created a new HashMap with `Character` as the key and `Integer` as the value.
3. We will be iterating over the example string using the for loop. 
4. We can use the `String.charAt(index)` method to get the character at index `index`.
5. We will check if the map contains the key or not. If present, that means this character was also present one or more times in the string before. So we will fetch its count and increase it by one.
6. If the map does not contain the key, that means we are getting characters for the first time. We will simply add the character and it counts as 1.
7. In the next for loop, we will print the duplicate characters and their respective counts. If the value is greater than 1 it means the character came more than one time in the string and we can print it.

**Output**

```
The example string is given below: 
This is an example string.

The duplicate characters and their respective count are given below: 
 : 4
a: 2
e: 2
i: 3
n: 2
s: 3
```

