---
layout: post  
title: "How Insert A Document in MongoDB Collection in Java Applications?"  
author: gaurav  
categories: [Java, MongoDB, MongoDB Atlas]  
toc: true
description: "In this tutorial, we will see how to insert a document in MongoDB in Java applications."
---

In this tutorial, we will see how to insert a document in MongoDB in Java applications.

To insert a document in MongoDB collection, first we should have a MongoClient. Let's see how to create one. Or You can read more at [How to Connect to a MongoDB Atlas Cluster in a Java Application](2023-10-19-connecting-to-mongodb-atlas-cluster-in-java-application)

```java
String connectionString = "mongodb+srv://user123:password123@cluster0.example.mongodb.net/?retryWrites=true&w=majority";
MongoClient mongoClient = MongoClients.create(connectionString);
```

The above `connectionString` is just an example, kindly get your valid connection String.

We can insert a single or multiple documents in MongoDB Collections.

Let's see how to insert single document in MongoDB.

## Insert a Single Document in MongoDB Collection

We can use the `insertOne()` method to insert a single document.

The `insertOne()` method accepts an Object that contains Document data and returns `InsertOneResult` Object.

We can get id of the inserted document from `InsertOneResult` (like  `insertOneResult.getInsertedId()`.

**Java Code to Insert a Single Document in a collection**

```java
MongoDatabase database = mongoClient.getDatabase("apple_corp");
MongoCollection<Document> collection = database.getCollection("employees");

Document employee = new Document("_id", new ObjectId())
        .append("id", "2023-06-1256")
        .append("name", "Tee Wilson")
        .append("joining_date", Date.from(LocalDate.of(2023, 6, 20).atStartOfDay(ZoneId.systemDefault()).toInstant()))
        .append("status", "onboarding")
        .append("bu", "newyork")
        .append("address", new Document().append("city", "NEW YORK").append("zip", 10022).append("street", "PARK AVENUE").append("number", 25626));

InsertOneResult insertOneResult = collection.insertOne(inspection);
BsonValue id = insertOneResult.getInsertedId();
System.out.println(id);
```

The above code will insert a single document `employee` in `employees` mongo collection. And It will print the inserted documents id on the console.

## Insert Multiple Documents in MongoDB Collection

We can use the `insertMany()` method to insert multiple document.

The `insertMany()` method accepts a list of Objects that contains Document data and returns `InsertManyResult` Object.

We can get id of the inserted documents from `InsertManyResult` (like  `insertManyResult.getInsertedIds().forEach((x,y)-> System.out.println(y.asObjectId()))`.

**Java Code To Insert Multiple Documents in Collection**

```java
MongoDatabase database = mongoClient.getDatabase("texas_school");
MongoCollection<Document> collection = database.getCollection("students");

Document student1 = new Document().append("name","jack sparrow").append("roll_number","202306NJ253").append("due",1256).append("status","checking");

Document student2 = new Document().append("name","mary nelson").append("roll_number","202306NJ073").append("due",25).append("status","ready");

List<Document> students = Arrays.asList(student1, student2);
InsertManyResult insertManyResult = collection.insertMany(students);
insertManyResult.getInsertedIds().forEach((x,y)-> System.out.println(y.asObjectId()));
```

Above code will insert the `student1` and `student2` documents in the `students` collection. Also, it will print  ids of inserted documents.
