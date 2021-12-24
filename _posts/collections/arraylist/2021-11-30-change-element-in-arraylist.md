---
layout: post
title: "How To Change An Element In ArrayList?"
author: gaurav
categories: [Collections, ArrayList]
description: "In this article, we will see how to change an element in ArrayList."
---

In this article, we will see how to change an element in [ArrayList](https://coderolls.com/arraylist-in-java/).

## Introduction

In the previous tutorial, we have seen [how we can add an element to the ArrayList](https://coderolls.com/add-element-in-arraylist/). But, if we wish to change an element from the ArrayList, we can change it using the `set()` method.

We know that `ArrayList` is an indexed collection. So we can access any particular element by its index and change it.

## `set() ` method

The `set()` method has a signature as `public E set(int index, E element)`.

This method accepts the index as `int` and an element that need to be set at that particular index.

The `set()` method has a return type as `E` that means it will return an element. **The `set()` method returns the element previously at the specified position.**

Below, we will see a java program to change (set) an element in `ArrayList`.

```java
package com.gaurav.ExProject.ArrayList;

import java.util.ArrayList;

/**
 * A java program to change an element at 
 * particular index in ArrayList.
 * 
 * We can use 'public E set(int index, E element)' method
 * to change an element.
 * 
 * @author Guarav Kukade at coderolls.com
 *
 */
public class ArrayListSetExample {

	public static void main(String[] args) {
ArrayList<String> arrayList = new ArrayList<String>();
		
		//adding elements to the arrayList using normal add method
		arrayList.add("Gaurav");
		arrayList.add("Shyam");
		arrayList.add("Pradnya");
		
		System.out.println(arrayList);// [Gaurav, Shyam, Pradnya]
		
		// change an element at index 1
		arrayList.set(1, "Saurav");
		
		System.out.println(arrayList); // [Gaurav, Saurav, Pradnya]
	}
}
```
Output:
```
[Gaurav, Shyam, Pradnya]
[Gaurav, Saurav, Pradnya]
```

### Explanation

1. In the above program, I  have added three strings (`"Gaurav"`, `"Shyam"`, `"Pradnya"`) to the `arrayList`. We can see this by printing the `arrayList`.
2. I want to change the element at index `1`. So, I have provided the index as `1`, and the new element i.e. String `"Saurav"` as arguments to the `set()` method.
3. On printing the `arrayList` again, we can see the change element at index `1`.

## Conclusion

So we can change the element in [ArrayList](https://coderolls.com/arraylist-in-java/) at particular index bu using the `set()` method.

The set method signature is as follows
```
public E set(int index, E element)
```

The `set()` returns the previously present element in the `ArrayList`.

So, we have seen [how to add an element](https://coderolls.com/add-element-in-arraylist/) and [how to change an element in the ArrayList](https://coderolls.com/change-element-in-arraylist/), next we will see how we can [remove an element from ArrayList](https://coderolls.com/remove-element-from-arraylist/) in Java.

---

The example java programs given in the above tutorial can be found at [this GitHub Repository](https://github.com/coderolls/blogpost-coding-examples/tree/main/collections/arraylist/change-element-in-arraylist).
