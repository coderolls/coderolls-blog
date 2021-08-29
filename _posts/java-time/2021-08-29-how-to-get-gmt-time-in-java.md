---
layout: post
title: "How To Get GMT Time In Java?"
author: gaurav
categories: [Java, Java Time]
description: "In this article, we will see how we can get GMT time in Java."
---

In Java Programming, sometimes we need date in GMT format. In this quick tutorial, we will see how we can get GMT time in Java.

We will be using the `ZonedDateTime` class to get the GMT. We can get any zone time using the `ZonedDateTime` class. You can <a target="_blank" href="https://coderolls.com/get-current-date-time-in-java/">see this article</a> to learn more about it.

I have given a java program below, it has the `getGMTTime()` method. This method receives the Date object (java.util.Date) and returns a GMT string.

```java
package com.coderolls.examples;

import java.time.Instant;
import java.time.ZoneOffset;
import java.time.ZonedDateTime;
import java.time.format.DateTimeFormatter;
import java.util.Date;
/**
 * A Java Program to get time in GMT
 * 
 * @author Gaurav Kukade at coderolls.com
 *
 */
public class GMTTimeExample {

	public static void main(String[] args) {
		
		Date date = new Date();
		String gmtTime = getGMTTime(date);
		System.out.println("Print time in GMT: "+gmtTime);

	}
	
	/**
	 * A method to return GMT time string
	 * @param date
	 * @return
	 */
	public static String getGMTTime(Date date) {
		
		DateTimeFormatter customFormatter = DateTimeFormatter.ofPattern("MM/dd/yyyy HH:mm:ss O");
		Instant instant = date.toInstant();
		ZonedDateTime zonedDateTime = instant.atZone(ZoneOffset.UTC);
		return customFormatter.format(zonedDateTime);
		
	}
}
```

In the above program, we have used the <a target="_blank" href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html">DateTimeFormatter</a>. You can check its various patterns in the <a target="_blank" href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html">documentation</a>.

If you are looking to get the current timestamp in java, you can visit this article <a target="_blank" href="https://coderolls.com/how-to-get-current-timestamps-in-java/">How To Get Current Timestamp In Java?</a>.

You can check my YouTube channel [here](https://www.youtube.com/channel/UCl31HHUdQbSHOQfc9L-wo3w).

### Related Articles

- [How To Get Current Timestamp In Java?](https://coderolls.com/how-to-get-current-timestamps-in-java/)

-   [How To Convert An Integer To String In Java](https://coderolls.com/convert-int-to-string/)
    
-   [How to convert String to Integer in Java](https://coderolls.com/convert-string-to-int/)
    
-   [How To Convert StringBuilder To String In Java?](https://coderolls.com/convert-stringbuilder-to-string-in-java/)
    
-   [How Do I Compare Strings In Java](https://coderolls.com/compare-strings-in-java/)
    
-   [How To Reverse A String In Java (5 ways)](https://coderolls.com/reverse-a-string-in-java/)

