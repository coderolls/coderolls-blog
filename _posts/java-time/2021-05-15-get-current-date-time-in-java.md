---
layout: post
title: "How To Get Current Date Time In Java?"
author: gaurav
categories: [Java, Java Time]
toc: true
description: "We need to use Date and Time in day-to-day programming. In this article, we will see how to get the current date and time in Java. "
---
We need to use Date and Time in day-to-day programming. In this article, we will see how to get the current date and time in Java. 

## Introduction

There are many ways to get the current date and time in Java. One of them is, using Legacy date and calendar API, and another one is using Java 8 date and time API. 

1. Java Date API (`java.util.Date`) (Legacy)
2. Java Calendar API (`java.util.Calendar`) (Legacy)
3. LocalDate (`java.time.LocalDate`)
4. LocalTime (`java.time.LocalTime`)
5. LocalDateTime (`java.time.LocalDateTime`)
6. ZonedDateTime (`java.time.ZonedDateTime`)
7. Instant (`java.time.Instant`)

We will see all of the above mentioned ways to get current date time in java.

We have used [SimpleDateFormat](https://docs.oracle.com/javase/7/docs/api/java/text/SimpleDateFormat.html) for legacy Date and Calendar classes and [DateTimeFormatter](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html) for Java 8 Date/Time API.

## 1. Java Date API (`java.util.Date`) (Legacy)

To get the current date and time using the `java.util.Date` class, we can create a new date object. And we can format it using [SimpleDateFormat](https://docs.oracle.com/javase/7/docs/api/java/text/SimpleDateFormat.html).

I have given an example below that shows how to get the current date and time using the `java.util.Date` class.

```java
import java.text.SimpleDateFormat;
import java.util.Date;

/**
 * A Java program to get current date time using the java.util.Date class
 * @author Gaurav Kukade at coderolls.com
 *
 */
public class DateExample {

  public static void main(String[] args) {
    SimpleDateFormat simpleDateFormat = new SimpleDateFormat("dd/MM/yyyy HH:mm:ss");
    Date date = new Date();  
    
    // print date object
    System.out.println(date);  // Sat May 15 12:21:39 IST 2021
    
    // print formatted date object
    System.out.println(simpleDateFormat.format(date));    // 15/05/2021 12:21:39
    
    // creates new Date() object using System.currentTimeMillis()
    Date date2 = new Date(System.currentTimeMillis());
    System.out.println(simpleDateFormat.format(date));    // 15/05/2021 12:21:39	
  }

}
```
Output:

```
Sat May 15 12:21:39 IST 2021
15/05/2021 12:21:39
15/05/2021 12:21:39
```
Check the above code as [GitHub Gist](https://gist.github.com/gauravkukade/c0abb86106b161cd9b3d12de37e34cb3)

## 2. Java Calendar API (`java.util.Calendar`) (Legacy)

We can use the `java.util.Calendar` class to get the instance of the Date class. The `getTime()` method of the Calendar class returns the instance of `java.util.Date`

I have given an example below that shows how to get the current date and time using the `java.util.Calendar` class.
```java
import java.text.SimpleDateFormat;
import java.util.Calendar;
import java.util.Date;

/**
 * A java program to get current date time using the java.util.Calendar class
 * @author Gaurav Kukade at coderolls.com
 */
public class CalendarExample {

  public static void main(String[] args) {
    SimpleDateFormat simpleDateFormat = new SimpleDateFormat("dd/MM/yyyy HH:mm:ss");
    
    // get the instance of the java.util.Calendar
    Calendar calendar = Calendar.getInstance();
    
    // getTime() method returns the instance of java.util.Date
    Date date = calendar.getTime();
    
    // prints the date object
    System.out.println(date);  // Sat May 15 12:50:17 IST 2021
    
    // print the formatted date 
    System.out.println(simpleDateFormat.format(date));  // 15/05/2021 12:50:17
  }
}
```
Output:
```
Sat May 15 12:50:17 IST 2021
15/05/2021 12:50:17
```

Check the above code as [GitHub Gist](https://gist.github.com/gauravkukade/b29079c6b840d9c894c836468d9326dd)

## 3. LocalDate (`java.time.LocalDate`)


`LocalDate` is one of the most commonly used classes of Java date/Time API. As given in the name specifies the local date.

We can use this class when zones are not required to be specified. The `LocalDate` represents a date in ISO format (yyyy-MM-dd) without time. ex. 2021-05-15

I have given an example below that shows how to get the current local date using the `java.time.LocalDate` class.
```java
import java.time.LocalDate;
import java.time.format.DateTimeFormatter;
/**
 * A java program to get local date using the java.time.LocalDate class
 * @author Gaurav Kukade at coderolls.com
 */
public class LocalDateExample {

  public static void main(String[] args) {
    DateTimeFormatter dateTimeFormatter = DateTimeFormatter.ofPattern("yyyy/MM/dd");
    LocalDate localDate = LocalDate.now();
    
    // print localDate object
    System.out.println(localDate); // 2021-05-15
    
    // print formatted localDate
    System.out.println(dateTimeFormatter.format(localDate)); // 2021/05/15
  }

}
```
Output:
```
2021-05-15
2021/05/15
```
Check the above code as [GitHub Gist](https://gist.github.com/gauravkukade/4a756785c65e94fa645c1a4faa65edb4)

## 4. LocalTime (`java.time.LocalTime`)

`LocalTime` is one of the most commonly used classes of Java date/Time API. As given in the name specifies the local time.

We can use this class when zones are not required to be specified. The `LocalTime` represents a time without a date. ex. 20:21:32

I have given an example below that shows how to get the current local time using the `java.time.LocalTime` class.

```java
import java.time.LocalTime;
import java.time.format.DateTimeFormatter;
/**
 * A Java program to get local time using the java.time.LocalTime class
 * @author Gaurav Kukade at coderolls.com
 */
public class LocalTimeExample {
  public static void main(String[] args) {
    DateTimeFormatter dateTimeFormatter = DateTimeFormatter.ofPattern("HH:mm:ss");
    LocalTime localTime = LocalTime.now();
    
    // print localTime object
    System.out.println(localTime);  // 13:11:46.140359217
    
    // print formatted localTime
    System.out.println(dateTimeFormatter.format(localTime));  // 13:11:46
  }
}
```
Output:
```
13:11:46.140359217
13:11:46
```
Check above code as [GitHub Gist](https://gist.github.com/gauravkukade/8ca11fd8b4652f33932b66a518c5775d)

## 5. LocalDateTime (`java.time.LocalDateTime`)


`LocalDateTime` is one of the most commonly used classes of Java date/Time API. As given in the name specifies the local date and time.

We can use this class when zones are not required to be specified. The `LocalDateTime` represents a combination of date and time. ex. 2021-05-15

I have given an example below that shows how to get the current local date-time using the `java.time.LocalDateTime` class.

```java
import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;
/**
 * A Java program to get local date-time using the java.time.LocalDateTime class
 * @author Gaurav Kukade at coderolls.com
 */
public class LocalDateTimeExample {
  public static void main(String[] args) {
    DateTimeFormatter dateTimeFormatter = DateTimeFormatter.ofPattern("dd/MM/yyyy HH:mm:ss");
    LocalDateTime localDateTime = LocalDateTime.now();
    
    // print localDateTime object
    System.out.println(localDateTime);  // 2021-05-15T13:20:13.329481722
    
    // print formatted localDateTime
    System.out.println(dateTimeFormatter.format(localDateTime)); //15/05/2021 13:20:13
  }
}
```
Output:
```
2021-05-15T13:20:13.329481722
15/05/2021 13:20:13
```
Check above code as [GitHub Gist](https://gist.github.com/gauravkukade/ef36191b7cca3069631ab45918624c1c)

## 6. ZonedDateTime (`java.time.ZonedDateTime`)

When we need to use zone-specific dates and times, we can use the `ZonedDateTime` class.

The different zones are represented by the [`ZoneId`](https://docs.oracle.com/javase/8/docs/api/java/time/ZoneId.html). We can get all the list of available ZoneIds using the [`getAvailableZoneIds()`](https://docs.oracle.com/javase/8/docs/api/java/time/ZoneId.html#getAvailableZoneIds--)

The code snippet to get the set of all available 	`ZoneIds` is given below.
```java
Set<String> allZoneIds = ZoneId.getAvailableZoneIds();
```

We can use the `ZonedDateTime.now()` method to get the system's default zone local time. We can specify the zone using the `now.withZoneSameInstant(zoneId)` method.

I have given an example below that shows how to get the zone-specific date-time using the `java.time.ZonedDateTime` class.

```java
import java.time.OffsetDateTime;
import java.time.ZoneId;
import java.time.ZoneOffset;
import java.time.ZonedDateTime;
import java.time.format.DateTimeFormatter;
/**
 * A Java program to get the zone-specific date-time using the java.time.ZonedDateTime class
 * @author Gaurav Kukade at coderolls.com
 */
public class ZonedDateTimeExample {

  public static void main(String[] args) {
    DateTimeFormatter dateTimeFormatter = DateTimeFormatter.ofPattern("yyyy/MM/dd HH:mm:ss"); 
    
    // get system default zone date time, 
    // my system default zone is +05:30 
    ZonedDateTime now = ZonedDateTime.now();
    System.out.println(dateTimeFormatter.format(now));   // 2021/05/15 13:45:55                 
    System.out.println(now.getOffset()); // +05:30
    
    // check the  default time zone
    System.out.println(ZoneOffset.systemDefault());   // Asia/Kolkata
    System.out.println(OffsetDateTime.now().getOffset());   // +05:30
    
    // get get current date time for Kolkata, India
    ZonedDateTime indiaDateTime = now.withZoneSameInstant(ZoneId.of("Asia/Kolkata"));  
    System.out.println(dateTimeFormatter.format(indiaDateTime));      // 2021/05/15 13:45:55    
    System.out.println(indiaDateTime.getOffset()); // +05:30
    
    // get get current date time for Paris , France
    ZonedDateTime franceDateTime = now.withZoneSameInstant(ZoneId.of("Europe/Paris"));
    System.out.println(dateTimeFormatter.format(franceDateTime));     // 2021/05/15 10:15:55     
    System.out.println(franceDateTime.getOffset()); // +02:00
  }
}
```
Output:
```
2021/05/15 13:45:55
+05:30
Asia/Kolkata
+05:30
2021/05/15 13:45:55
+05:30
2021/05/15 10:15:55
+02:00
```
Check above code as [GitHub Gist](https://gist.github.com/gauravkukade/1ef796c53091ddb2a658f3e7dda22366)

## 7. Instant (`java.time.Instant`)

We can use `java.time.Instant` to get epoch timestamps in seconds and milliseconds.
```java
import java.time.Instant;
import java.time.LocalDateTime;
import java.time.ZoneId;
import java.time.format.DateTimeFormatter;

/**
 * A Java program to get the current date time using the java.time.Instant class
 * @author Gaurav Kukade at coderolls.com
 */
public class InstantExample {

  public static void main(String[] args) {
    Instant instant = Instant.now();
    
    //print instant object
    System.out.println(instant);  // 2021-05-15T10:11:45.331237189Z
    
    //get epoch time in milliseconds 
    //epoch timestamp is the number of milliseconds/seconds since January 1, 1970, 00:00:00 GMT
    System.out.println(instant.toEpochMilli()); // 1621073505331
    
    // get epoch time in seconds 
    System.out.println(instant.getEpochSecond());  // 1621073505
    
    //We can convert instant to LocalDateTime, LocalDate, LocalTime
    DateTimeFormatter dateTimeFormatter = DateTimeFormatter.ofPattern("dd/MM/yyyy HH:mm:ss");
    LocalDateTime localDateTime = LocalDateTime.ofInstant(instant, ZoneId.systemDefault());
    System.out.println(dateTimeFormatter.format(localDateTime)); // 15/05/2021 15:41:45
  }
}
```
Output:
```
2021-05-15T10:11:45.331237189Z
1621073505331
1621073505
15/05/2021 15:41:45
```
Check above code as [GitHub Gist](https://gist.github.com/gauravkukade/f490a87ced1aa63c076bbe6bd7860a2c)

## Conclusion

We have seen all the ways to get the current date and time in Java. It is recommended to use the Java 8 Time/Date API.

Below I have listed down the code snippets to get the current date and time in Java for the respective class.

Using`java.util.Date` class
```java
SimpleDateFormat simpleDateFormat = new SimpleDateFormat("dd/MM/yyyy HH:mm:ss");
Date date = new Date();  

// print date object
System.out.println(date);  // Sat May 15 12:21:39 IST 2021

// print formatted date object
System.out.println(simpleDateFormat.format(date));    // 15/05/2021 12:21:39
```
`java.util.Calendar` class
```java
// get the instance of the java.util.Calendar
Calendar calendar = Calendar.getInstance();

// getTime() method returns the instance of java.util.Date
Date date = calendar.getTime();
System.out.println(date);  // Sat May 15 12:50:17 IST 2021
```
`java.time.LocalDate` class
```java
LocalDate localDate = LocalDate.now();
System.out.println(localDate); // 2021-05-15
```
`java.time.LocalTime` class
```java
LocalTime localTime = LocalTime.now();
System.out.println(localTime);  // 13:11:46.140359217
```
`java.time.LocalDateTime` class
```java
LocalDateTime localDateTime = LocalDateTime.now();
System.out.println(localDateTime);  // 2021-05-15T13:20:13.329481722
```
`java.time.ZonedDateTime` class
```java
DateTimeFormatter dateTimeFormatter = DateTimeFormatter.ofPattern("yyyy/MM/dd HH:mm:ss"); 

ZonedDateTime now = ZonedDateTime.now();
ZonedDateTime indiaDateTime = now.withZoneSameInstant(ZoneId.of("Asia/Kolkata"));  

System.out.println(dateTimeFormatter.format(indiaDateTime));      // 2021/05/15 13:45:55    
System.out.println(indiaDateTime.getOffset()); // +05:30
```
`java.time.Instant` class
```java
Instant instant = Instant.now();

System.out.println(instant);  // 2021-05-15T10:11:45.331237189Z
System.out.println(instant.toEpochMilli()); // 1621073505331
System.out.println(instant.getEpochSecond());  // 1621073505
```

So, we have seen all the ways to get the current date and time in Java. You can comment below if you know of any other way to get the current date time in Java.

If you want to check, [how can we get the current timestamps in Java?](https://coderolls.com/how-to-get-current-timestamps-in-java/) we have written an article on it.

You can check my YouTube channel [here](https://www.youtube.com/channel/UCl31HHUdQbSHOQfc9L-wo3w)
