---
layout: post
title: "How To Parse JSON In Java?"
author: gaurav
image: assets/images/2021-01-07/parse-json-in-java.png
categories: [JSON, Java]
description: "In this article we will see, how to parse JSON in java. We will be using the JSON Libraries like JSON-java, GSON and json simple"
featured: true
---
In this article we will see, how to parse JSON in java. We will be using the JSON Libraries like JSON-java, GSON and json-simple

**JSON** stands for JavaScript Object Notation. It is easy to use and lightweight open standard file format for storing and transporting data.

As per the [json.org](https://www.json.org/json-en.html),
>It is easy for humans to read and write. It is easy for machines to parse and generate.

Example JSON:

```json
{
  "name": "coderolls",
  "type": "blog",
  "address": {
    "street": "1600 Pennsylvania Avenue NW",
    "city": "Washington",
    "state": "DC"
  },
  "employees": [
    {
      "firstName": "John",
      "lastName": "Doe"
    },
    {
      "firstName": "Anna",
      "lastName": "Smith"
    },
    {
      "firstName": "Peter",
      "lastName": "Jones"
    }
  ]
}
```
In the above JSON, `name` is key and `coderolls` is it's value. For `address` key, value is another JSON object which contains key and values.

For `employees` key, it's value is array of JSON objects.

Today we will see three json libraries in java to parse a JSON string. These are listed below,

1. JSON-Java
2. GSON
4. json-simple

Now we will see one by one example of all three libraries  for parsing a JSON in java.

## How to parse JOSN in Java using JSON-Java

JSON-java is one of the most simple JSON library for Java.

Here, we will be using the `JSONObject` class of the JSON-java library.

`JSONObject` [has a constructor which accepts string](https://stleary.github.io/JSON-java/index.html). We will be using ths constructor to parse a JSON string.

```
public JSONObject(String source) throws JSONException

Construct a JSONObject from a source JSON text string. This is the most commonly used JSONObject constructor.

Parameters:

source  - A string beginning with  `{` (left brace)  and ending with  `}`  (right brace).

Throws:

JSONException  - If there is a syntax error in the source string or a duplicated key.
```

You can refer [JSON-java Docs](https://stleary.github.io/JSON-java/index.html).

Maven:
```
<dependency>
    <groupId>org.json</groupId>
    <artifactId>json</artifactId>
    <version>20201115</version>
</dependency>
```

Gradle:
```
compile group: 'org.json', name: 'json', version: '20201115'
```
Example:

```java
package com.coderolls.JSONExample;

import org.json.JSONArray;
import org.json.JSONObject;

/**
 * A program to parse JSON strin in Java using JSON-Java
 * @author Gaurav Kukade at coderolls.com
 */

public class ParseJSONUsingJSONJava {

	public static void main(String[] args) {
		
		String jsonString = "{"
				+ "  \"name\": \"coderolls\","
				+ "  \"type\": \"blog\","
				+ "  \"address\": {"
				+ "    \"street\": \"1600 Pennsylvania Avenue NW\","
				+ "    \"city\": \"Washington\","
				+ "    \"state\": \"DC\""
				+ "  },"
				+ "  \"employees\": ["
				+ "    {"
				+ "      \"firstName\": \"John\","
				+ "      \"lastName\": \"Doe\""
				+ "    },"
				+ "    {"
				+ "      \"firstName\": \"Anna\","
				+ "      \"lastName\": \"Smith\""
				+ "    },"
				+ "    {"
				+ "      \"firstName\": \"Peter\","
				+ "      \"lastName\": \"Jones\""
				+ "    }"
				+ "  ]"
				+ "}";
		
		System.out.println("Parsing the json string in java using JSON-Java......\n");

		//add jsonString to the constructor
		JSONObject coderollsJSONObject = new JSONObject(jsonString);
		
		//now we can access the values 
		String name = coderollsJSONObject.getString("name");
		System.out.println("Name: "+name+"\n");
		
		//we can get the JSON object present as value of any key in the parent JSON
		JSONObject addressJSONObject = coderollsJSONObject.getJSONObject("address");
		
		//access the values of the addressJSONObject 
		String street = addressJSONObject.getString("street");
		System.out.println("Street: "+street+"\n");
		
		
		//we can get the json array present as value of any key in the parent JSON
		JSONArray employeesJSONArray = coderollsJSONObject.getJSONArray("employees");
		System.out.println("Printing the employess json array: \n"+employeesJSONArray.toString()+"\n");
		
		//we can get individual json object at an index from the employeesJSONArray
		JSONObject employeeJSONObject = employeesJSONArray.getJSONObject(0);
		String firstName = employeeJSONObject.getString("firstName");
		System.out.println("First Name of the employee at index 0: "+firstName);
	}
}
```

Get the code for [ParseJSONUsingJSON.Java](https://github.com/coderolls/blogpost-coding-examples/blob/main/java-json/parse-json-in-java/ParseJSONUsingJSONJava.java)

Output:
```java
Parsing the json string in java using JSON-Java......

Name: coderolls

Street: 1600 Pennsylvania Avenue NW

Printing the employess json array: 
[{"firstName":"John","lastName":"Doe"},{"firstName":"Anna","lastName":"Smith"},{"firstName":"Peter","lastName":"Jones"}]

First Name of the employee at index 0: John
```
## How to parse JOSN in Java using Gson

Gson is an open-source Java library to serialize and deserialize Java objects to JSON developed at Google.

So we can use it to convert a JSON string to an equivalent Java object.

Here, we will be using the `JsonObject` class of the Gson library.

You can refer the [docs of JsonObject](https://www.javadoc.io/doc/com.google.code.gson/gson/latest/com.google.gson/com/google/gson/JsonObject.html).

Maven: 
```
<dependency>
    <groupId>com.google.code.gson</groupId>
    <artifactId>gson</artifactId>
    <version>2.8.6</version>
</dependency>
```
Gradle:
```
compile group: 'com.google.code.gson', name: 'gson', version: '2.8.6'
```

Example:
```java
package com.coderolls.JSONExample;

import com.google.gson.Gson;
import com.google.gson.JsonArray;
import com.google.gson.JsonObject;

/**
 * A program to parse JSON strin in Java using Gson
 * @author Gaurav Kukade at coderolls.com
 */

public class ParseJSONUsingGSON {

	public static void main(String[] args) {

		//take json as string
		String jsonString = "{"
				+ "  \"name\": \"coderolls\","
				+ "  \"type\": \"blog\","
				+ "  \"address\": {"
				+ "    \"street\": \"1600 Pennsylvania Avenue NW\","
				+ "    \"city\": \"Washington\","
				+ "    \"state\": \"DC\""
				+ "  },"
				+ "  \"employees\": ["
				+ "    {"
				+ "      \"firstName\": \"John\","
				+ "      \"lastName\": \"Doe\""
				+ "    },"
				+ "    {"
				+ "      \"firstName\": \"Anna\","
				+ "      \"lastName\": \"Smith\""
				+ "    },"
				+ "    {"
				+ "      \"firstName\": \"Peter\","
				+ "      \"lastName\": \"Jones\""
				+ "    }"
				+ "  ]"
				+ "}";
		System.out.println("Parsing the json string in java using Gson......\n");

		Gson gson = new Gson();
		
		//get json object from the json string
		JsonObject coderollsJsonObject = gson.fromJson(jsonString, JsonObject.class);
		
		//now we can access the values 
		String name = coderollsJsonObject.get("name").getAsString();
		System.out.println("Name: "+name+"\n");
		
		//we can get the JSON object present as value of any key in the parent JSON
		JsonObject addressJsonObject = coderollsJsonObject.get("address").getAsJsonObject();
		
		//access the values of the addressJSONObject 
		String street = addressJsonObject.get("street").getAsString();
		System.out.println("Street: "+street+"\n");
		
		
		//we can get the json array present as value of any key in the parent JSON
		JsonArray employeesJsonArray = coderollsJsonObject.get("employees").getAsJsonArray();
		System.out.println("Printing the employess json array: \n"+employeesJsonArray.toString()+"\n");
		
		//we can get individual json object at an index from the employeesJSONArray
		JsonObject employeeJsonObject = employeesJsonArray.get(0).getAsJsonObject();
		String firstName = employeeJsonObject.get("firstName").getAsString();
		System.out.println("First Name of the employee at index 0: "+firstName);
	}
}
```

Get the code for [ParseJSONUsingGSON.java](https://github.com/coderolls/blogpost-coding-examples/blob/main/java-json/parse-json-in-java/ParseJSONUsingGSON.java)


Output:
```java
Parsing the json string in java using Gson......

Name: coderolls

Street: 1600 Pennsylvania Avenue NW

Printing the employess json array: 
[{"firstName":"John","lastName":"Doe"},{"firstName":"Anna","lastName":"Smith"},{"firstName":"Peter","lastName":"Jones"}]

First Name of the employee at index 0: John
```
## How to parse JOSN in Java using json-simple

JSON.simple is a simple Java toolkit for JSON. You can use JSON.simple to encode or decode JSON text.

Maven: 
```
<dependency>
    <groupId>com.googlecode.json-simple</groupId>
    <artifactId>json-simple</artifactId>
    <version>1.1.1</version>
</dependency>
```

Gradle:
```
compile group: 'com.googlecode.json-simple', name: 'json-simple', version: '1.1.1'
```
You can refer the [json-simple project page.java](https://code.google.com/archive/p/json-simple/).

Example:

```java
package com.coderolls.JSONExample;

import org.json.simple.JSONArray;
import org.json.simple.JSONObject;
import org.json.simple.parser.JSONParser;
import org.json.simple.parser.ParseException;

/**
 * A program to parse JSON strin in Java using json-simple
 * @author Gaurav Kukade at coderolls.com
 */

public class ParseJSONUsingJsonSimple {

	public static void main(String[] args) {
		//take json as string
		String jsonString = "{"
						+ "  \"name\": \"coderolls\","
						+ "  \"type\": \"blog\","
						+ "  \"address\": {"
						+ "    \"street\": \"1600 Pennsylvania Avenue NW\","
						+ "    \"city\": \"Washington\","
						+ "    \"state\": \"DC\""
						+ "  },"
						+ "  \"employees\": ["
						+ "    {"
						+ "      \"firstName\": \"John\","
						+ "      \"lastName\": \"Doe\""
						+ "    },"
						+ "    {"
						+ "      \"firstName\": \"Anna\","
						+ "      \"lastName\": \"Smith\""
						+ "    },"
						+ "    {"
						+ "      \"firstName\": \"Peter\","
						+ "      \"lastName\": \"Jones\""
						+ "    }"
						+ "  ]"
						+ "}";
				
		System.out.println("Parsing the json string in java using json-simple......\n");
		
		JSONParser parser = new JSONParser();
		JSONObject coderollsJSONObject = new JSONObject();
		try {
			coderollsJSONObject = (JSONObject) parser.parse(jsonString);
		} catch (ParseException e) {
			e.printStackTrace();
		}
		
		//now we can access the values 
		String name = (String) coderollsJSONObject.get("name");
		System.out.println("Name: "+name+"\n");
		
		//we can get the JSON object present as value of any key in the parent JSON
		JSONObject addressJSONObject = (JSONObject) coderollsJSONObject.get("address");
		
		//access the values of the addressJSONObject 
		String street = (String) addressJSONObject.get("street");
		System.out.println("Street: "+street+"\n");
		
		
		//we can get the json array present as value of any key in the parent JSON
		JSONArray employeesJSONArray = (JSONArray) coderollsJSONObject.get("employees");
		System.out.println("Printing the employess json array: \n"+employeesJSONArray.toString()+"\n");
		
		//we can get individual json object at an index from the employeesJSONArray
		JSONObject employeeJSONObject = (JSONObject) employeesJSONArray.get(0);
		String firstName = (String) employeeJSONObject.get("firstName");
		System.out.println("First Name of the employee at index 0: "+firstName);
	}
}
```

Get the code for [ParseJSONUsingJsonSimple.java](https://github.com/coderolls/blogpost-coding-examples/blob/main/java-json/parse-json-in-java/ParseJSONUsingJsonSimple.java)

Output:
```java
Parsing the json string in java using json-simple......

Name: coderolls

Street: 1600 Pennsylvania Avenue NW

Printing the employess json array: 
[{"firstName":"John","lastName":"Doe"},{"firstName":"Anna","lastName":"Smith"},{"firstName":"Peter","lastName":"Jones"}]

First Name of the employee at index 0: John
```

## Conclusion

All three libraries allow you create a JSON object from the json string but I found the JSON-Java is easy to use.

You can visit my [YouTube channel 'coderolls'](https://www.youtube.com/channel/UCl31HHUdQbSHOQfc9L-wo3w?view_as=subscriber?sub_confirmation=1) to find more video tutorials.

--------------

You can support me by [giving a cup of Coffee ☕](https://www.paypal.me/GauravKukade)

#### Related Articles

- [8 Basic GIT Commands Every Newbie Developer Must Know](https://coderolls.com/basic-git-commands/)
- [How To Reverse A String In Java (5 ways)](https://coderolls.com/reverse-a-string-in-java/)
- [How To Create UUID in Java?](https://coderolls.com/create-uuid-in-java/)
- [Learn About Java String Pool And intern() Method](https://coderolls.com/java-string-pool-and-intern-method/)
- [How Do I Compare Strings In Java](https://coderolls.com/compare-strings-in-java/)
- [Compare Two Strings Lexicographically In Java](https://coderolls.com/compare-two-strings-lexicographically-in-java/)
- [Difference Between StringBuffer and StringBuilder class](https://coderolls.com/difference-between-stringbuffer-and-stringbuilder/)
