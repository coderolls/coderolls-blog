---
layout: post  
title: "How To Find A Document in MongoDB Collection in Java Applications?"  
author: gaurav  
categories: [Java, MongoDB, MongoDB CRUD Operations]  
toc: true
description: "In this tutorial, we will see how to find a document in MongoDB in Java applications."
---

In this tutorial, we will see how to find a document in MongoDB in Java applications.

To insert a document in MongoDB collection, first we should have a MongoClient. Let's see how to create one. Or You can read more at [How to Connect to a MongoDB Atlas Cluster in a Java Application](/connecting-to-mongodb-atlas-cluster-in-java-application)

```java
String connectionString = "mongodb+srv://user123:password123@cluster0.example.mongodb.net/?retryWrites=true&w=majority";
MongoClient mongoClient = MongoClients.create(connectionString);
```

The above `connectionString` is just an example, kindly get your valid connection String.

We can find the documents in MongoDB collection using `find()` and `find().first()`methods.

Let's see how to find a documents in mongodb collection using the `find()` method first.

## Finding documents in mongodb collection using the `find()` method

The `find()` method accepts a query filter and returns documents that matches the filter.

In the following code we will try to find all the students who has dues greater than 250 and status as checking.

**Java Code to Find Documents in a collection**

```java
MongoDatabase database = mongoClient.getDatabase("texas_school");
MongoCollection<Document> collection = database.getCollection("students");

try(MongoCursor<Document> cursor = collection.find(
    and(gte("due", 250),eq("status","checking")))
        .iterator())
{
    while(cursor.hasNext()) {
        System.out.println(cursor.next().toJson());
    }
}
```

## Finding a document in mongodb collection using the ``find().first()`` method

The ``find().first()`` method accepts a query filter and returns the first document that matches the filter.

In the following code we will try to find the first student who has dues greater than 250 and status as checking.

**Java Code to Find a Single Documents in a collection**

```java
MongoDatabase database = mongoClient.getDatabase("texas_school");
MongoCollection<Document> collection = database.getCollection("students");

Document doc = collection.find(Filters.and(
    gte("due", 1000), Filters.eq("status", "checking"))).first();

System.out.println(doc.toJson());
```

