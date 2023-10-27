---
layout: post
title: "Your Guide To UUID In Java"
author: gaurav
image: assets/images/2020-12-19/uuid.webp
categories: [ Java, Core Java, String]
description: In this article, you will learn what is UUID and about the Java UUID class.
toc: true
featured: false
---

In this article, we will see, 
- What is UUID?
- Java UUID class

## What is UUID?

UUID, a universally unique identifier is a 128-bit number used to identify information in computer systems.

UUID is made of hex digits along with 4 hyphen ("-") symbols. The length of a UUID is 36 characters.

There are 4 types of UUID

1. Time-based UUID (Version 1)
2. DCE Security UUID (Version 2)
3. Name-based UUID (Version 3 and 5)
4. Randomly Generated UUID (Version 4)

Mostly Randomly Generated UUID i.e. UUID Version 4 is used. 

UUID Version 4 uses random numbers as a source. It uses an unpredictable value as the seed to generate random numbers to reduce the chance of collisions

There are 4 types of UUID variant

-   **0:**  It is reserved for NCS backward compatibility
-   **2:**  Leach-Salz
-   **6:**  It is reserved for Microsoft backward compatibility
-   **7:**  It is reserved for future definition.

Mostly variant 2 is used.

UUID can be used in the following cases
 
 -  As a primary key of the database table
-   To create a session ID for a web application
-   To represent as transaction ID
-   To create a random file name

### Example UUID

df6fdea1-10c3-474c-ae62-e63def80de0b

![Structure of UUID](/assets/images/2020-12-19/uuid.webp)
## Java UUID class

UUID Class belongs to the `java.util` package. It represents an immutable universally unique identifier (UUID).

UUID Constructor

```java
`[UUID](https://docs.oracle.com/javase/8/docs/api/java/util/UUID.html#UUID-long-long-)(long mostSigBits, long leastSigBits)`
```
Constructs a new  `UUID`  using the specified data.

### Static methods
There are three static methods of a UUID class,

```java
UUID.fromString(String name) 
```
The above method creates a UUID from the string standard representation as described in the [toString()](https://docs.oracle.com/javase/8/docs/api/java/util/UUID.html#toString--) method.

```java
UUID.nameUUIDFromBytes(byte[] name) 
```
This method is used to create a version 3 (name-based) UUID based on the specified byte array.

```java
UUID.randomUUID()
```
This method is used to create a version 4 (pseudo-randomly generated) UUID.

### Instance methods

Also, there are a few instance methods of a UUID class.

```java 
clockSequence()
```
This method is used to get the clock sequence value associated with this UUID.

This method returns the clock sequence value as `int`.

```java
compareTo(UUID val)
```
This method is used to compare this UUID with the specified UUID ( the one received as method param i.e. `val`

This method returns -1, 0 or 1 as this `UUID` is less than, equal to, or greater than `val`

```java
equals(Object obj)
```
This method simply compares this object to the specified object. It returns the result in `boolean`

```java
node()
```
This method returns the node value (`long`) associated with this UUID.

```java
timestamp()
```
This method returns the timestamp value (`long`) associated with this UUID.

```java
toString()
```
This method returns a `String` object representing this UUID.

```java
variant()
```
This method returns the variant number (`int`) associated with this UUID.

```java
version()
```
This method returns the version number (`int`)  associated with this UUID.

--------
You can visit my [YouTube channel 'coderolls'](https://www.youtube.com/channel/UCl31HHUdQbSHOQfc9L-wo3w?view_as=subscriber?sub_confirmation=1) to find more video tutorials.
