---
layout: post  
title: "How To Delete Documents in MongoDB Collection in Java Applications?"  
author: gaurav  
categories: [Java, MongoDB, MongoDB CRUD Operations]  
toc: true
description: "In this tutorial, we will see how to delete documents in MongoDB in Java applications."
---

We have seen how to [insert](/inserting-documents-in-mongodb-in-java), [find](/finding-document-in-mongodb-in-java) and [update](/updating-documents-in-mongodb-in-java) documents in mongodb collection. In this tutorial, we will see how to delete documents in MongoDB in Java applications.

To  delete a document in the MongoDB collection, first, we should have a MongoClient. Let's see how to create one. Or You can read more at [How to Connect to a MongoDB Atlas Cluster in a Java Application](/connecting-to-mongodb-atlas-cluster-in-java-application)

```java
String connectionString = "mongodb+srv://user123:password123@cluster0.example.mongodb.net/?retryWrites=true&w=majority";
MongoClient mongoClient = MongoClients.create(connectionString);
```

The above `connectionString` is just an example, kindly get your valid connection String.

We can delete a single document using `deleteOne()` or multiple documents using `deleteMany()` in MongoDB Collections.

Let's see how to delete a single document in MongoDB.

## Delete a single document using `deleteOne()` method

We can use the `deleteOne()` method to delete a single document. The method accepts a query filter that matches the document  that needs to be deleted. It will delete only the first documents that match.

Let's see a code where we want to delete a student document where the roll number is 

```java
MongoDatabase database = mongoClient.getDatabase("texas_school");
MongoCollection<Document> collection = database.getCollection("students");

Bson query  = Filters.eq("roll_number","202306NJ253");
DeleteResult deleteResult = collection.deleteOne(query);
System.out.println("Deleted a document:");
System.out.println("\t" + deleteResult.getDeletedCount());
```

## Delete multiple documents using `deleteMany()` method with a Query Object

To delete multiple documents from a Mongodb collection we can use the `deleteMany()` method.

We can pass a query filter that matches the objects that need to be deleted. If we pass an empty object, it will match with all the documents and delete all the documents.

Let's see an example of deleting the student documents whose status is `rejected`

```java
MongoDatabase database = mongoClient.getDatabase("texas_school");
MongoCollection<Document> collection = database.getCollection("students");

Bson query  = Filters.eq("status","rejected");
DeleteResult deleteResult = collection.deleteMany(query);
System.out.println("Deleted a document:");
System.out.println(deleteResult.getDeletedCount());
```

The `deleteMany()` method returns a `Deleteresult` object. We can get the deleted documents to count from it like `deleteResult.getDeletedCount()`.
