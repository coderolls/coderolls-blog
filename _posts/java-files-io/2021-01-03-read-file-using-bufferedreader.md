---
layout: post
title: "How To Read File Using BufferedReader In Java?"
author: gaurav
image: assets/images/2021-01-03/read-file-using-bufferedreader.webp
categories: [Java, Java File IO]
description: "In this article we will see how to read a file using the `BufferedReader` class in Java."
---

In this article we will see how to read a file using the `BufferedReader `class in Java.

`BufferedReader` class reads text from a character-input stream. Because of buffering characters it provides an  efficient way to read characters, arrays, and lines.

`BufferedReader` provides two important  methods to read from the file. i.e `read()` and `readLine()`.

You can specify the bufferSize in `BufferedReader `constructer. But as [motioned in the docs](https://docs.oracle.com/javase/8/docs/api/java/io/BufferedReader.html), 
>The default is large enough for most purposes.

## BufferedReader `read()` method

`BufferedReader` `read()` method reads a single character. IT returns the `int` representation of the char in range of 0 to 65535 (0x00-0xffff), or -1 if the end of the stream has been reached.

We can cast `int` value returned by `read()` method to `char` to get the character value.

I have given an example to read a file character by character using the `read()` method of the `BufferedReader` class
```java
package com.coderolls;

import java.io.*;

/**
 * A java program to read file character by character using the
 * read() method of the BufferedReader Class.
 * 
 * @author Gaurav Kukade at coderolls.com
 */
public class BufferedReaderReadMethodExample {

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
See [this example on GitHub](https://github.com/coderolls/blogpost-coding-examples/blob/main/java-files-io/BufferedReaderReadMethodExample.java).

## BufferedReader `readLine()` method
As specified in the name, this method reads a line of text.

A line is considered to be terminated by any one of a line feed ('\n') or  a carriage return ('\r').

The `readLine()` method returns the content of a line as string except the line terminating character (i.e. `\n` or `\r`). Or it will return `null` if the end of the stream has been reached.

I have given below an example to read file line by line using the `readLine()` method

```java
package com.coderolls;

import java.io.*;

/**
 * A java program to read file line by line using the
 * readLine() method of the BufferedReader Class.
 * 
 * @author Gaurav Kukade at coderolls.com
 *
 */
public class BufferedReaderReadLineMethodExample {

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
See [this example on GitHub](https://github.com/coderolls/blogpost-coding-examples/blob/main/java-files-io/BufferedReaderReadLineMethodExample.java).

I have given below a combine example of the Java `BufferedReader` `read()` and `readLine()` method below

```java
package com.coderolls;

import java.io.*;

public class BufferedReaderExanple {

	public static void main(String[] args) {
		BufferedReader bufferedReader = null;
		try {
			bufferedReader = new BufferedReader(new FileReader("F:\\sample-text.txt"));
			System.out.println("Read file using read() method: ");
			readFileCharacterByCharacter(bufferedReader);

			bufferedReader = new BufferedReader(new FileReader("F:\\sample-text-two-lines.txt"));
			System.out.println("\n\nRead file using readLine() method: ");
			readFileLineByLine(bufferedReader);
			
		} catch (FileNotFoundException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}

		try {
			bufferedReader.close();
		} catch (IOException e) {
			e.printStackTrace();
		}
	}
	
	/**
	 * A method to read file content character by character using the BufferedReader 
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
	 * A method to read file content line by line using the BufferedReader 
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

See [this example on GitHub](https://github.com/coderolls/blogpost-coding-examples/blob/main/java-files-io/BufferedReaderExanple.java).

## `newBufferedReader()` method in Java 8 

In Java 1.8 and above you can get a `BufferedReader` instance using the `newBufferedReader()` method of the `java.nio.file.Files` class.

## Conclusion

You can read file character by character using the `read()` method of the `BufferedReader`Class.

`read()` method returns an integer value, you have to cast it to `char` to get character value.

Also, you can read file line by line using the `readLine()` method of the `BufferedReader`Class

`readLine()` methods returns the line content as string, except the line terminating character

You can visit my [YouTube channel 'coderolls'](https://www.youtube.com/channel/UCl31HHUdQbSHOQfc9L-wo3w?view_as=subscriber?sub_confirmation=1) to find more video tutorials.

Please write down your thoughts in the comment section below.
