---
layout: post
title: "How To Read File Using BufferReader In Java?"
author: gaurav
image: assets/images/2021-01-03/read-file-using-bufferreader.png
categories: [Java, Java File IO]
description: "In this article we will see how to read a file using the `BufferReader` class in Java."
---

In this article we will see how to read a file using the `BufferReader `class in Java.

`BufferReader` class reads text from a character-input stream. Because of buffering characters it provides an  efficient way to read characters, arrays, and lines.

`BufferReader` provides two important  methods to read from the file. i.e `read()` and `readLine()`.

You can specify the bufferSize in `BufferReader `constructer. But as [motioned in the docs](https://docs.oracle.com/javase/8/docs/api/java/io/BufferedReader.html), 
>The default is large enough for most purposes.

## BufferReader `read()` method

`BufferReader` `read()` method reads a single character. IT returns the `int` representation of the char in range of 0 to 65535 (0x00-0xffff), or -1 if the end of the stream has been reached.

We can cast `int` value returned by `read()` method to `char` to get the character value.

I have given an example to read a file character by character using the `read()` method of the `BufferReader` class
```java
package com.coderolls;

import java.io.*;

/**
 * A java program to read file character by character using the
 * read() method of the BufferReader Class.
 * 
 * @author Gaurav Kukade at coderolls.com
 */
public class BufferReaderReadMethodExample {

	public static void main(String[] args) {
		
        BufferedReader bufferedReader = null;
		try {
			bufferedReader = new BufferedReader(new FileReader("F:\\sample-text.txt"));
			
			int i;
			//read each character using read() method and print it
			while((i=bufferedReader.read())!=-1){  
				System.out.print((char)i);  
			}
			 
		}catch (IOException e) {
			e.printStackTrace();
		}finally {
			try {
				bufferedReader.close();
			} catch (IOException e) {
				e.printStackTrace();
			}
		}
	}
}
```
Output
```
Welcome to coderolls.com!
```
See [this example on GitHub](https://github.com/coderolls/blogpost-coding-examples/blob/main/java-files-io/BufferReaderReadMethodExample.java).

## BufferReader `readLine()` method
As specified in the name, this method reads a line of text.

A line is considered to be terminated by any one of a line feed ('\n') or  a carriage return ('\r').

The `readLine()` method returns the content of a line as string except the line terminating character (i.e. `\n` or `\r`). Or it will return `null` if the end of the stream has been reached.

I have given below an example to read file line by line using the `readLine()` method

```java
package com.coderolls;

import java.io.*;

/**
 * A java program to read file line by line using the
 * readLine() method of the BufferReader Class.
 * 
 * @author Gaurav Kukade at coderolls.com
 *
 */
public class BufferReaderReadLineMethodExample {

	public static void main(String[] args) {
		
        BufferedReader bufferedReader = null;
		try {
			bufferedReader = new BufferedReader(new FileReader("F:\\sample-text-two-lines.txt"));
			
			String line;
			//read each line using readLine() method and print it
			while((line = bufferedReader.readLine()) != null){  
				System.out.println(line);  
			}
			 
		}catch (IOException e) {
			e.printStackTrace();
		}finally {
			try {
				bufferedReader.close();
			} catch (IOException e) {
				e.printStackTrace();
			}
		}
	}
}
```
Output
```java
Welcome to coderolls.com!

Visit coderolls to read more coding tutorials!
```
See [this example on GitHub](https://github.com/coderolls/blogpost-coding-examples/blob/main/java-files-io/BufferReaderReadLineMethodExample.java).

I have given below a combine example of the Java `BufferReader` `read()` and `readLine()` method below

```java
package com.coderolls;

import java.io.*;

public class BufferReaderExanple {

	public static void main(String[] args) {
		BufferedReader bufferedReader = null;
		try {
			bufferedReader = new BufferedReader(new FileReader("F:\\sample-text-two-lines.txt"));
			
		} catch (FileNotFoundException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
		
		readFileCharacterByCharacter(bufferedReader);
		
		readFileLineByLine(bufferedReader);
		
		try {
			bufferedReader.close();
		} catch (IOException e) {
			e.printStackTrace();
		}
	}
	
	/**
	 * A method to read file content character by character using the BufferReader 
	 * read() method
	 * 
	 * @param bufferedReader
	 */
	public static void readFileCharacterByCharacter(BufferedReader bufferedReader) {
			try {
				int i;
				//read each character using read() method and print it
				while((i=bufferedReader.read())!=-1){  
					System.out.print((char)i);  
				}
			} catch (IOException e) {
				e.printStackTrace();
			}
	}
	
	/**
	 * A method to read file content line by line using the BufferReader 
	 * readLine() method
	 * 
	 * @param bufferedReader
	 */
	public static void readFileLineByLine(BufferedReader bufferedReader) {
		
		try {
			String line;
			//read each line using readLine() method and print it
			while((line = bufferedReader.readLine()) != null){  
				System.out.println(line);  
			} 
		}catch (IOException e) {
			e.printStackTrace();
		}	
	}
}
```

See [this example on GitHub](https://github.com/coderolls/blogpost-coding-examples/blob/main/java-files-io/BufferReaderExanple.java).

## `newBufferedReader()` method in Java 8 

In Java 1.8 and above you can get a `BufferReader` instance using the `newBufferedReader()` method of the `java.nio.file.Files` class.

## Conclusion

You can read file character by character using the `read()` method of the `BufferReader`Class.

`read()` method returns an integer value, you have to cast it to `char` to get character value.

Also, you can read file line by line using the `readLine()` method of the `BufferReader`Class

`readLine()` methods returns the line content as string, except the line terminating character

You can visit my [YouTube channel 'coderolls'](https://www.youtube.com/channel/UCl31HHUdQbSHOQfc9L-wo3w?view_as=subscriber?sub_confirmation=1) to find more video tutorials.

--------------

You can support me by [giving a cup of Coffee ☕](https://www.paypal.me/GauravKukade)

#### Related Articles

- [8 Basic GIT Commands Every Newbie Developer Must Know](https://coderolls.com/basic-git-commands/)

-   [How To Reverse A String In Java (5 ways)](https://coderolls.com/reverse-a-string-in-java/)

- [How To Create UUID in Java?](https://coderolls.com/create-uuid-in-java/)

-   [Learn About Java String Pool And intern() Method](https://coderolls.com/java-string-pool-and-intern-method/)
-   [How Do I Compare Strings In Java](https://coderolls.com/compare-strings-in-java/)

-   [Compare Two Strings Lexicographically In Java](https://coderolls.com/compare-two-strings-lexicographically-in-java/)
-  [Difference Between StringBuffer and StringBuilder class](https://coderolls.com/difference-between-stringbuffer-and-stringbuilder/)

- [8 Basic GIT Commands Every Newbie Developer Must Know](https://coderolls.com/basic-git-commands/)

- [How To Create UUID in Java?](https://coderolls.com/create-uuid-in-java/)
