---
layout: post
title: "Groovy: How To Determine The Datatype Of An Object?"
author: gaurav
categories: [Groovy]
description: "In this quick tutorial, we will how can we determine the datatype of an object in Groovy."
---

## Introduction

In this quick tutorial, we will see how we can determine the datatype of an object in Groovy.

When you are writing a Groovy code, sometimes you need to check the datatype of an object.  Also, not following the proper naming convention may lead to object datatype confusion.

We will see the best way to check the datatype of an object in groovy so that you can use it correctly in the code.

## How To Determine The Datatype Of An Object In Groovy?

To determine the class of an object, you can simply call the `getClass()` method on it.

An example is given below.
```groovy
anObject.getClass()
```
let check the above line program.

```groovy
def names = ['Gaurav', 'Shubham', 'Nayan', 'Sudeep'];

println names.getClass(); // prints 'class java.util.ArrayList'

def blogname = '''coderolls''';

println blogname.getClass(); // prints 'class java.lang.String'

println blogname.getClass().name; // prints 'java.lang.String'
```

Output:
```
class java.util.ArrayList
class java.lang.String
java.lang.String
```
In the above program, we can see that the `names` is an `ArrayList`  and `blogname` is a `String` object.

When we call the `getClass()` method on these objects it prints its respective datatype.

In most of the cases you can use the `anObject.getClass()` as `anObject.class`. But if `anObject` is `Map` it will try to retrieve the value with key 'class'.  Because of this it is always recommended to use `anObject.getClass()` instead of `anObject.class`.

If you want to check if an object implements a particular interface or extends a particular class (e.g. String, ArrayList, etc), you can use the `instanceof` keyword.

For example,

```groovy
(anObject instanceof String)
```

Let's check above code in an example program

```groovy
def blogname = '''coderolls''';
println (blogname instanceof String) // true
println (blogname instanceof ArrayList) // false
```
Output: 
```
true
false
```

In the above program, I have defined one String `blogname`. I have used the `instanceof` keyword to check if the `blogname` implements the `String` class and it prints `true`. It means the `blogname` is an instance of the `String` class.

When I used the `instanceof` keyword to check if the `blogname` implements the `ArrayList` class and it prints `false`. It means the `blogname` is not an instance of the `ArrayList` class.

## Conclusion

In this tutorial, we have seen how we can determine the datatype of an object in Groovy.

You can use the `getClass()` method to determine the class of an object.

```groovy
anObject.getClass()
```

Also, if you want to check if an object implements an Interface or Class, you can use the `instanceof` keyword.

```groovy
(anObject instanceof String)
```
That's it about checking the datatype of an object in Groovy. 

If you know any other way to check the datatype of an object, please comment below to help the community. Thank you.

### Related Articles

- [Hello World In Groovy](https://coderolls.com/hello-world-in-groovy/)
