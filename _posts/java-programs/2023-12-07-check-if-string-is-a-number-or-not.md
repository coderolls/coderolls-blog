---
layout: post  
title: "Java Program To Check If the given String Is A Number or Not"  
author: gaurav  
categories: [Java Programs, Core Java]  
toc: true
description: "In this tutorial, we will see a Java program to check if the given String is a number or not."
---

In this tutorial, we will see a Java program to check if the given String is a number or not.

We can check it using the regex expression.

## Java Program To Check If the Given String is Number or Not Using Regex Expression

In the below program, we have simply used the regex expression to check whether the given string is numeric or not.

The regex expression to check this is `-?\\d+`

Here,

`-?`     --> negative sign, could have none or one

`\\d+`   --> one or more digits

**Java Program**

```java
import java.util.List;

/**
 *  A Java program to check if the given String is a number or not.
 *  @author coderolls.com
 */
public class CheckIfNumber {

    public static void main(String[] args) {
        List<String> strings = List.of("95965", "Jack485", "-9859", "784Will", "056", "Google");
        for(String str : strings) {
            boolean isNumber = isNumberOrNot(str);
            if (isNumber) {
                System.out.println("The String '" + str + "' is a Number.");
            } else {
                System.out.println("The String '" + str + "' is not a Number.");
            }
        }

    }

    /**
     * A method checks if the input param string is numeric or not
     * It uses a regex Expression
     * -?     --> negative sign, could have none or one
     * \\d+   --> one or more digits
     * @param str
     * @return
     */
    private static boolean isNumberOrNot(String str) {
        return str.matches("-?\\d+");
    }
}
```

Output

```
The String '95965' is a Number.
The String 'Jack485' is not a Number.
The String '-9859' is a Number.
The String '784Will' is not a Number.
The String '056' is a Number.
The String 'Google' is not a Number.
```



## Java Program To Check If the Given String is Number or Not Using the `Character.isDigit()` method

In this method, we are iterating over an array of characters of the String and checking if any character is a digit or not.

If we find one or more digits in the string, the given string is not a number string or a number.

```Java
import java.util.List;

/**
 *  A Java program to check if the given String is a number or not.
 *  using the Character.isDigit() method.
 *  @author coderolls.com
 */
public class CheckIfNumber2 {

    public static void main(String[] args) {
        List<String> strings = List.of("95965", "Jack485", "-9859", "784Will", "056", "Google");
        for(String str : strings) {
            boolean isNumber = isNumberOrNot(str);
            if (isNumber) {
                System.out.println("The String '" + str + "' is a Number.");
            } else {
                System.out.println("The String '" + str + "' is not a Number.");
            }
        }

    }

    /**
     * A method checks if the input param string is numeric or not
     * It uses a regex Expression
     * -?     --> negative sign, could have none or one
     * \\d+   --> one or more digits
     * @param str
     * @return
     */
    private static boolean isNumberOrNot(String str) {
        char[] chars = str.toCharArray();
        for(int i=0; i<str.length(); i++) {

            char ch = str.charAt(i);
            if(i==0 && ch == '-') {
                continue;
            }
            
            if (! (Character.isDigit(ch))) {
                return false;
            }
        }
        //If not a single ch is a digit, the string is numeric
        return true;
    }
}
```

Output

```
The String '95965' is a Number.
The String 'Jack485' is not a Number.
The String '-9859' is a Number.
The String '784Will' is not a Number.
The String '056' is a Number.
The String 'Google' is not a Number.
```



## Java Program To Check If the Given String is Number or Not `NumberFormatExpression` way. 

We can also check if it using the `NumberFormatExpression` way. 

Let's See how. (**Not recommended to use, Just for Info**)

We can try to parse the given String using the `Integer.parseInt(str)` method.

If the given string is not a number the method will throw `NumberFormatExpression` and we can return `false` by catching this expression. Otherwise `true`.

See the sample method below.

```java
public static boolean isInteger(String s) {
    try { 
        Integer.parseInt(s); 
    } catch(NumberFormatException e) { 
        return false; 
    } catch(NullPointerException e) {
        return false;
    }
    // only got here if we didn't return false
    return true;
}
```

**But this way is not recommended as it causes expensive exceptions in the code.**
