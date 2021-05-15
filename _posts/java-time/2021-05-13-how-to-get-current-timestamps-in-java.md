---
layout: post
title: "How To Get Current Timestamp In Java?"
author: gaurav
categories: [Java, Java Time]
description: "In this article, we will see how to get the current timestamp in Java."
---
In this article, we will see how to get the current timestamp in Java. 

To get the current timestamp in Java, we can use [`java.time.Instant`](https://docs.oracle.com/javase/8/docs/api/java/time/Instant.html) from Java 8 and [`java.sql.Timestamp`](https://docs.oracle.com/javase/7/docs/api/java/sql/Timestamp.html) till Java 7.

We check both [`java.time.Instant`](https://docs.oracle.com/javase/8/docs/api/java/time/Instant.html)  and [`java.sql.Timestamp`](https://docs.oracle.com/javase/7/docs/api/java/sql/Timestamp.html)  one by one.

## 1. Using  `java.time.Instant` ( for Java 8)
As per the [javadoc](https://docs.oracle.com/javase/8/docs/api/java/time/Instant.html),
> This class models a single instantaneous point on the time-line. This might be used to record event time-stamps in the application. 

I have given an example below that shows how to get the current timestamp using `java.time.Instant`  

```java
import java.sql.Timestamp;
import java.time.Instant;
import java.util.Date;

/**
 * A Java Program to get current timestamp using using the java.time.Instant
 * 
 * @author Gaurav Kukade at coderolls.com
 *
 */
public class InstantExample {
	
	public static void main(String[] args) {
	    
		Instant instant = Instant.now();
	    System.out.println("1. instant: "+ instant);    // 2021-05-13T15:05:18.734Z
	    

	    //convert date object to instant
	    Date date = new Date();
	    Instant instantFromDate = date.toInstant();
	    
	    System.out.println("2. instantFromDate: " +instantFromDate);  // 2021-05-13T15:05:18.873Z
	    
	    
	    //get instnat from the java.sql.Timestamp
	    Timestamp timestamp = new Timestamp(System.currentTimeMillis());
	    Instant instantFromTimestamp = timestamp.toInstant();
	    
	    System.out.println("3. instantFromTimestamp: "+ instantFromTimestamp);  // 2021-05-13T15:05:18.874Z 
	    
	    //get the epoch timestamp in milliseconds 
	    //epoch timestamp is number of milliseconds since January 1, 1970, 00:00:00 GMT
	    Instant instant2 = Instant.now();  
	    long timeStampMillis = instant2.toEpochMilli();
	    
	    System.out.println("4. timeStampMillis: "+ timeStampMillis);   // 1620918318874
	    
	    //get the epoch timestamp in seconds
	    Instant instant3 = Instant.now();
	    long timeStampSeconds = instant3.getEpochSecond();
	    
	    System.out.println("5. timeStampSeconds: "+ timeStampSeconds);   // 1620918318

	}

}
```
Output:
```
1. instant: 2021-05-13T15:24:19.907Z
2. instantFromDate: 2021-05-13T15:24:19.988Z
3. instantFromTimestamp: 2021-05-13T15:24:19.988Z
4. timeStampMillis: 1620919459988
5. timeStampSeconds: 1620919459
```
See above code as [GitHub Gist](https://gist.github.com/gauravkukade/b1ceabac137864efd7258b60610cd9dd)

### Explanation:

1. In the first case, we have used the `.now()` method of the `Instant` class to get the current timestamp.
2. In the second case, we have created a new `date` object, and then we have used the `.toInstant()` on the `date` object to get the current timestamp.
3. In the third case, we have created a new `timestamp` object using the system time in milliseconds. We can get the system time in millisecond using the `System.currentTimeMillis()`. To get the current timestamp (as instant) we have used the `.toInstant()` method on the `timestamp` object.
4. In the fourth case, we are trying to get the epoch timestamp in milliseconds. We can get it using the `.toEpochMilli()` method on the `instant` object.
5. In the fifth case, we are trying to get the epoch timestamp in seconds. We can get it using the `.getEpochSecond()` method on the `instant` object.

## 2. Using  `java.sql.Timestamp` ( for Java 7 and below)

```java
import java.sql.Timestamp;
import java.util.Date;

/**
 * A Java program to get the current timestamp using java.sql.Timestamp
 * 
 * @author Gaurav Kukade at coderolls.com
 *
 */
public class TimestampExample {

	public static void main(String[] args) {
		
		 //using system time in milliseconds
	    Timestamp timestampFromSystemTime = new Timestamp(System.currentTimeMillis());
	    System.out.println("1. timestampFromSystemTime: "+timestampFromSystemTime); // 2021-05-13 20:55:44.179
	     
	    //using java.util.Date
	    Date date = new Date();
	    Timestamp timestampFromDateObject = new Timestamp(date.getTime());	  
	    System.out.println("2. timestampFromDateObject: " +timestampFromDateObject); // 2021-05-13 20:55:44.187

	}

}
```
Output:

```
1. timestampFromSystemTime: 2021-05-13 20:55:44.179
2. timestampFromDateObject: 2021-05-13 20:55:44.187
```

See above code as [GitHub Gist](https://gist.github.com/gauravkukade/a965f1a078d382ff7366e7ba6d13561c)

### Explanation:

1. In the first case, we are got the `timestamp` using the system time in milliseconds. We can get the system time in millisecond using the `System.currentTimeMillis()`.
2. In the second case, we have created a new `date` object, and then we have used the `.getTime()` on the `date` object to get the current time in milliseconds. We have passed the time milliseconds to timestamp constructor to get the current timestamp.

Sometimes we may need to convert the `java.time.Instant` to `java.sql.Timestamp` or vice versa. So let's see both conversions below.

## How to convert `Instant` to `Timestamp` In Java?

I have given an example below that converts the `java.time.Instant` to `java.sql.Timestamp` class.

```java
import java.sql.Timestamp;
import java.time.Instant;

/**
 * A Java Program to convert java.time.Instant to java.sql.Timestamp
 * 
 * @author Gaurav Kukade at coderolls.com
 *
 */
public class InstantToTimestamp {

	public static void main(String[] args) {
		
		// get Timestamp from Instant 
		Instant instant = Instant.now();
	    Timestamp timestamp = Timestamp.from(instant);
	    System.out.println("Instant To Timestamp: " +timestamp); // 2021-05-13 21:07:44.381


	}

}
```

Output:
```
Instant To Timestamp: 2021-05-13 21:07:44.381
```
See above code as [GitHub Gist](https://gist.github.com/gauravkukade/ea3bc951f15be0010569d306ccafa975)

### Explanation:

In the above example, we have used `.from()` of the `Timestamp` class to get the current timestamp from the `instant` object.

```java
Timestamp timestamp = Timestamp.from(instant);
```


## How to convert `Timestamp` to `Instant` In Java?

I have given an example below that converts the `java.sql.Timestamp` to `java.time.Instant` class.

```java
import java.sql.Timestamp;
import java.time.Instant;

/**
 * A Java Program to convert java.sql.Timestamp to java.time.Instant
 * 
 * @author Gaurav Kukade at coderolls.com
 *
 */
public class TimestampToInstant {

	public static void main(String[] args) {
		
	    //get instnat from the java.sql.Timestamp
	    Timestamp timestamp = new Timestamp(System.currentTimeMillis());
	    Instant instant = timestamp.toInstant();
	    System.out.println("Timestamp To Instant: " +instant); // 2021-05-13T15:39:08.046Z
	    
	}

}
```

Output:
```
Timestamp To Instant: 2021-05-13T15:39:08.046Z
```
See above code as [GitHub Gist](https://gist.github.com/gauravkukade/a031b1904d4efaf758a59462ee2dc02e)

### Explanation:

In the above example, we have used the `.toInstant()` method on the `timestamp` object to get the current timestamp (as Instant ).

## Conclusion 

We can get the current timestamp in java using the `Instant` and `Timestamp`.

From Java 8, it is recommended to use the timestamp of the Instant class. We can get the current timestamp from `Instant`as is given below,

```java
Instant instant = Instant.now();

//convert date object to instant
Date date = new Date();
Instant instantFromDate = date.toInstant();	    

//get instnat from the java.sql.Timestamp
Timestamp timestamp = new Timestamp(System.currentTimeMillis());
Instant instantFromTimestamp = timestamp.toInstant();


//get the epoch timestamp in milliseconds 
//epoch timestamp is number of milliseconds since January 1, 1970, 00:00:00 GMT
Instant instant2 = Instant.now();  
long timeStampMillis = instant2.toEpochMilli();


//get the epoch timestamp in seconds
Instant instant3 = Instant.now();
long timeStampSeconds = instant3.getEpochSecond();
```

In Java 7 or below, we can use the `Timestamp` class to get the current timestamp.

```java
 //using system time in milliseconds
Timestamp timestampFromSystemTime = new Timestamp(System.currentTimeMillis());

//using java.util.Date
Date date = new Date();
System.out.println(date.getTime());
Timestamp timestampFromDateObject = new Timestamp(date.getTime());	  

``` 
Also we can convert the `java.time.Instant` to `java.sql.Timestamp` or vice versa.


**Instant To Timestamp**

```java
Instant instant = Instant.now();
Timestamp timestamp = Timestamp.from(instant);
```

**Timestamp to Instant**

```java
Timestamp timestamp = new Timestamp(System.currentTimeMillis());
	    Instant instant = timestamp.toInstant();
```

That's it for now. 

If you have any queries about the above article, please comment below. Thanks.

We will see [how to get the current date-time in java](https://coderolls.com/get-current-date-time-in-java/). Also, we will see how we can format them using the SimpleDateFormat.

You can check my YouTube channel [here](https://www.youtube.com/channel/UCl31HHUdQbSHOQfc9L-wo3w)

### Related Articles

-   [How To Get Current Date Time In Java](https://coderolls.com/get-current-date-time-in-java/)

-   [How To Convert An Integer To String In Java](https://coderolls.com/convert-int-to-string/)
    
-   [How to convert String to Integer in Java](https://coderolls.com/convert-string-to-int/)
    
-   [How To Convert StringBuilder To String In Java?](https://coderolls.com/convert-stringbuilder-to-string-in-java/)
    
-   [How Do I Compare Strings In Java](https://coderolls.com/compare-strings-in-java/)
    
-   [How To Reverse A String In Java (5 ways)](https://coderolls.com/reverse-a-string-in-java/)

