---
layout: post  
title: "How To Update A Document in MongoDB Collection in Java Applications?"  
author: gaurav  
categories: [Java, MongoDB, MongoDB CRUD Operations]  
toc: true
description: "In this tutorial, we will see how to update a document in MongoDB in Java applications."
---

In this tutorial, we will see how to update a document in MongoDB in Java applications.

To update a document in MongoDB collection, first we should have a MongoClient. Let's see how to create one. Or You can read more at [How to Connect to a MongoDB Atlas Cluster in a Java Application](/connecting-to-mongodb-atlas-cluster-in-java-application)

```java
String connectionString = "mongodb+srv://user123:password123@cluster0.example.mongodb.net/?retryWrites=true&w=majority";
MongoClient mongoClient = MongoClients.create(connectionString);
```

The above `connectionString` is just an example, kindly get your valid connection String.

We can update a single or multiple documents in MongoDB Collections.

Let's see how to update a single document in MongoDB.

## Update a Single Document in MongoDB Collection

We can use the `updateOne()` method to insert a single document.

The `updateOne()` method accepts a filter that matches the document that we want to update, and an statement with the updates for the matching document.

The `updateOne()` method only updates the only first document that matches the filter. And it returns `UpdateResult`.

**Java Code to Update a Single Document in a collection**

```java
MongoDatabase database = mongoClient.getDatabase("texas_school");
MongoCollection<Document> collection = database.getCollection("students");

Bson query  = Filters.eq("roll_number","202306NJ253");
Bson updates  = Updates.combine(Updates.set("status","ready"),Updates.inc("due",-1200));
UpdateResult updateResult = collection.updateOne(query, updates);
```

The above code will update a single document `student` in `students` mongo collection that has `roll_number` as `202306NJ253`. The `status` will be updated to `ready` and the `due` will be decreased by amount `1200`.

## Update Multiple Documents in MongoDB Collection

We can use the `updateMany()` method to update multiple document.

The `updateMany()` method accepts a filter that matches the documents that we want to update, and an statement with the updates for the matching document.

The `updateMany()` method updates all the documents that matches the filter. And it returns `UpdateResult`.

**Java Code To Update Multiple Documents in Collection**

```java
MongoDatabase database = mongoClient.getDatabase("texas_school");
MongoCollection<Document> collection = database.getCollection("students");

Bson query  = Filters.eq("status","ready");
Bson updates  = Updates.combine(Updates.set("due",0));
UpdateResult upResult = collection.updateMany(query, updates);
```

The above code will update al the documents  `students` mongo collection that has `status` as `ready`. It will set `due` for all the matching documents to `0`.
