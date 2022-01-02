---
layout: post
title: substring() Method in Java (With example)
author: gaurav
categories: [ Java, Core Java, String]
toc: true
description: The String class in Java is one of the most important classes in Java. After reading this article you will be able to use the 'substring()` method of the String class.
---
The String class in Java is one of the most important classes in Java. After reading this article you will be able to use the 'substring()` method of the String class.

I have given two examples with the pictorial explanation to make this concept easy to understand.

## Introduction

let us understand what does mean by 'substring'. As per the  [Wikipedia](https://en.wikipedia.org/wiki/Substring),

“A **substring** is a contiguous sequence of characters within a string. For instance, “the best of” is a **substring** of “It was the best of times”.

Java  `substring()`  method returns a 'substring' of the specified string. The creation of the 'substring' depends on the parameter passed to the `substring()` method.

In Java, the `substring()`  method is the overloaded method and it has two variants.

1.  `substring(int beginIndex)`
2.  `substring(int beginIndex, int endIndex)`

We will learn about both variants one by one.

## 1.  `substring(int beginIndex)`

The first variant of the  `substring()`  method accepts only one parameter. i.e.  `beginIndex`  The substring will start from the specified  `beginIndex`  and it will extend to the end of the string.

```
public String substring(int beginIndex)

Returns a string that is a substring of this string. The substring begins with the character at the specified index and extends to the end of this string.

Parameters:
beginIndex - the beginning index, inclusive.

Returns:
the specified substring.

Throws:
IndexOutOfBoundsException - if beginIndex is negative or larger than the length of this String object.
```

Please note that the  `beginIndex`  parameter is  **inclusive**, which means the character at the  `beginIndex`  will be the part of the substring.

So, it will return a substring which is started from the character at the  `beginIndex`  and it will extend to the end of the string.

I will take a simple example to explain to same.

If the given string is “codeRolls.com” and we applied the substring() method with the  `beginIndex`  as  `4`, it will return the substring “Rolls.com”.

```
"codeRolls".substring(4) returns "Rolls.com"
```

See the pictorial explanation shown below.

![substring() method explanation with both parameter i.e. beginIndex and endIndex](/assets/images/2019-12-12-java-substring-method/substring-method-with-beginIndex.webp)

substring() method explanation with one parameter i.e. beginIndex

Let us see the full java code for the example stated above.

```java
public class SubstringExample {

    public static void main(String[] args) {
        
        String name = "codeRolls.com";
        
        String result = name.substring(4);
        
        System.out.println(result);
    }

}
```

Output:

```
Rolls.com
```

### Note:

`substring(int beginIndex)`  will throw an  `IndexOutOfBoundsException`  if the  `beginIndex`  is negative or larger than the length of the string object.

i.e. It will throw an exception if

`beginIndex`  is negative OR  `beginIndex`  >  `string.length()`

## 2.  `substring(int beginIndex, int endIndex)`

This variant of the substring method will accept two-parameter,  `beginIndex`  and  `endIndex`. This method will return the substring which starts from the  `beginIndex`  and will end at  `endIndex - 1`.

Yes, the substring will extend till the  `endIndex-1`  because the parameter  `endIndex`  is  **exclusive** in this variant of the method. This means the character at the  `endIndex`  will not be part of the substring.

```
public String substring(int beginIndex, int endIndex)

Returns a string that is a substring of this string. The substring begins at the specified beginIndex and extends to the character at index endIndex - 1. Thus the length of the substring is endIndex-beginIndex.
 
Parameters:
beginIndex - the beginning index, inclusive.
endIndex - the ending index, exclusive.

Returns:
the specified substring.

Throws:
IndexOutOfBoundsException - if the beginIndex is negative, or endIndex is larger than the length of this String object, or beginIndex is larger than endIndex.
```

You can calculate the length of the substring using  `beginIndex`  and  `endIndex`. It will be  `endIndex`  –  `beginIndex`.

I will take a simple example to explain it to you.

Let us take a simple string like “codeRolls.com” and I will apply the  `substring()`  method with the parameter  `beginIndex`  as  `4`  and  `endIndex`  as  `9`  it will return the substring “Rolls”.

```
"codeRolls".substring(4, 9) returns "Rolls"
```

See the pictorial explanation shown below.

![substring() method explanation with both parameter i.e. beginIndex and endIndex](/assets/images/2019-12-12-java-substring-method/substring-method-with-beginIndex-and-endIndex.webp)

Let us see the full java code for the example stated above.

```java
public class SubstringExampleWithBothIndex {

  public static void main(String[] args) {
    
    String name = "codeRolls.com";
    
    String result = name.substring(4, 9);
    
    System.out.println(result);
  }

}
```

Output:

```
Rolls
```

### Note:

`substring(int beginIndex, int endIndex)`  method will throw  `IndexOutOfBoundsException`  exception if  `beginIndex`  is negative, or  `beginIndex`  larger than the  `endIndex`  or  `endIndex`  is larger than the length of the string object.

i.e  `substring(int beginIndex, int endIndex)`  will throw an exception if

`beginIndex`  is negative OR  `beginIndex`  >  `endIndex`  OR  `endIndex`  >  `string.length()`

## Conclusion

In Java  `substring()`  method has two variants.

1.  `substring(int beginIndex)`
2.  `substring(int beginIndex, int endIndex)`

`substring(int beginIndex)`  returns the substring of this string which will start from the character at the  `beginIndex`  and will extend to the end of the string. Here, the parameter  `beginIndex`  is inclusive.

`substring(int beginIndex, int endIndex)`  returns the substring of this string which will start from the character at the  `beginIndex`  and will extend till the character at the  `endIndex - 1`. Here, the parameter  `beginIndex`  is inclusive while the parameter  `endIndex`  is exclusive.

If you have any queries about the  `substring()`  method please write it below in the comment section.
