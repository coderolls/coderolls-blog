---
layout: post
title: "Difference Between StringBuffer and StringBuilder class"
author: gaurav
image: assets/images/2019-12-24-difference-between-stringbuffer-and-stringbuilder/blog-cover.jpg
categories: [ Java, Core Java, String]
description: "In this article, we are going to discuss the differences between the `StringBuffer` and `StringBuilder` class. And we will see why it `StringBuilder` is preferable to `StringBuffer` class."

---
In this article, we are going to discuss the differences between the `StringBuffer` and `StringBuilder` class. And we will see why it `StringBuilder` is preferable to `StringBuffer` class."

## Introduction

The String class is one of the most important classes in Java. In every day to day coding in Java, we use string many times.

We create a new string and perform various operations on it, like adding a character or removing a character, but do you know every time you operate on the string, each time a new string object is created and assigned to your current string variable.

Yes, it happens under the hood.

Most of us know that String is immutable. This means we can not edit the current string object, when we try to do it we are creating a new string object.

As I said in the very first line, String is one of the most important classes in Java and we use it many times in our code. The number of operations creates the same amount of garbage string objects, which put pressure on the Garbage Collector.

Taking this need into consideration the Java Team introduce `StringBuffer` class.

`StringBuffer` is mutable. You can edit it. But we can say that the Java Team was more concern about the correctness of the operations so they made it synchronized. All methods of the `StringBuffer` class are synchronized.

But what does it mean by the word 'synchronized'?

Synchronization is the capability to control the access of methods. An only a single thread can access a method at one time.

That means all the methods of the `StringBuffer` class can be accessed by a single thread at a time.

After using it for a while, java developers feel that the `StringBuffer` is taking more time because of synchronization. Making all methods of `StringBuffer` class synchronized is not required. Then the Java team realize making `StringBuffer` class synchronized wasn't a great decision and they corrected it by introducing the `StringBuilder`  class in Java 1.5.

`StringBuilder` class is like `StringBuffer` only but with one difference. 
> [`StringBuffer`](http://docs.oracle.com/javase/8/docs/api/java/lang/StringBuffer.html) is synchronized, [`StringBuilder`](http://docs.oracle.com/javase/8/docs/api/java/lang/StringBuilder.html) is not.

Now we will discuss the difference between the  `StringBuffer` and `StringBuilder`  class in detail.

## Difference Between `StringBuffer` and `StringBuilder` 

To understand the difference between the `StringBuffer` and `StringBuilder` class we should first understand the need for the `StringBuilder` class.

We have discussed earlier that because of day to day use and a lot of pressure on the Garbage collector due to garbage string objects, the java team introduced `StringBuffer` class. They made it synchronized in concern with the correctness.

Making `StringBuffer` class synchronized causing the performance issue and that's why `StringBuilder` came.

Now you can learn the difference, the `StringBuffer` class is synchronized while the `StringBuilder` class is not.

But this is the main difference. We will discuss a few more differences which came into the existence because of this main difference.

| Feature | `StringBuffer` | `StringBuilder`|
| --- | --- |---|
| Synchronization| `StringBuffer` is synchronized. That means all the methods of the `StringBuffer` class are synchronized.| `StringBuilder` is not synchronized. That is none of the methods of the `StringBuilder` class  is synchronized.|
| Thread safety | `StringBuffer` is thread-safe. Since all method of `StringBuffer` class is synchronized, only one thread can access a method at one time. | `StringBuilder` is not thread-safe. Since none of the methods of `StringBuilder` class is synchronized, multiple threads can access a method at one time.|
| Speed | Since all methods of the `StringBuffer` class are synchronized, it takes more time as compared to the `StringBuilder` class for the same task. i.e. `StringBuffer` is slower as compare to `StringBuilder`| Since none of the methods of the `StringBuilder` class is synchronized, it takes less time as compare to `StringBuffer` class for the same task. i.e. `StringBuilder` is faster as compare to `StringBuffer`|
|Efficiency| Slower nature makes `StringBuffer` class inefficient. | Faster nature makes `StringBuilder` class efficient.|

In support of the above discussion, we will see the first paragraph from the [Java API documentation of the `StringBuilder` class](https://docs.oracle.com/javase/8/docs/api/java/lang/StringBuilder.html),  that states you should give preference to the `StringBuilder` class.
> A mutable sequence of characters. This class provides an API compatible with `StringBuffer`, **but with no guarantee of synchronization**. This class is designed for use as a drop-in replacement for `StringBuffer` in places where the string buffer was being used by a single thread (as is generally the case). Where possible, it is recommended that this class be used in preference to `StringBuffer` **as it will be faster under most implementations.**

Also, I will like to share one detail with you, when you perform the string concatenation operation and if you are using Java 1.4 or lower then java internally using `StringBuffer` class for string concatenation operation.

After an introduction to `StringBuilder` class in Java 1.5, from Java 1.5 and higher Java internally uses `StringBuilder` class for string concatenation.

## Conclusion

The most important difference between the `StringBuffer` class and `StringBuilder` class is
> [`StringBuffer`](http://docs.oracle.com/javase/8/docs/api/java/lang/StringBuffer.html) is synchronized, [`StringBuilder`](http://docs.oracle.com/javase/8/docs/api/java/lang/StringBuilder.html) is not.

So, `StringBuffer` class takes more time as compare to `StringBuilder` class for performing the same operation.

Taking efficiency into consideration, it is highly recommended to use `StringBuilder` class instead of the old `StringBuffer` class.

If you found this article worth, support me by  [giving a cup of Coffee ☕](https://www.paypal.me/GauravKukade)

Also, if you have other information about the difference between `StringBuffer` class and `StringBuilder` class please write it down in the comment section below.
