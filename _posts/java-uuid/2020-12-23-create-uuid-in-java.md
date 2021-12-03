---
layout: post
title: "How To Create UUID in Java?"
author: gaurav
image: assets/images/2020-12-23/create-uuid-in-java.webp
categories: [Java, Core Java, String]
description: "In this article you will see, how to create UUID in Java."
hidden: false
---

In this article you will see, how to create UUID in Java.

## Introduction

UUID, a universally unique identifier is a 128-bit number used to identify information in computer systems.

UUID is made of hex digits along with 4 hyphen ("-") symbols. The length of a UUID is 36 characters.

There are 5 types of UUID but mostly version 4 i.e. Randomly Generated UUID is used.

We are going to create the version 4 UUID here.

### Example UUID

df6fdea1-10c3-474c-ae62-e63def80de0b

## How to create UUID in Java?

Creating a Randomly Generated UUID (version 4) is really easy in Java.

UUID Class is present in  `java.util` package. And it has the static method `randomUUID()` which returns the randomly generated UUID.

The example is given below.

```java
import java.util.UUID;

/**
 * A Java program to create a Randomly Generated UUID i.e. Version 4 UUID
 * @author Gaurav Kukade at coderolls.com
 *
 */
public class CreateUUID {

	public static void main(String[] args) {
		
		// creating random uuid i.e. version 4 UUID
		UUID uuid = UUID.randomUUID();
		
		System.out.println("Printing the randomly generated UUID value......\n");
		
		System.out.println("uuid: "+uuid);
		
	}

}

```
Output
```java
Printing the randomly generated UUID value......

uuid: e3aed661-ccc2-42fd-ad69-734fee350cd2

```

Get the [above code as GitHub Gist](https://gist.github.com/gauravkukade/395f314c549969bd300d72c7e032dbcb).

--------

You can visit my [YouTube channel 'coderolls'](https://www.youtube.com/channel/UCl31HHUdQbSHOQfc9L-wo3w?view_as=subscriber?sub_confirmation=1) to find more video tutorials.
