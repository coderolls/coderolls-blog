---
layout: post  
title: "How to Connect to a MongoDB Atlas Cluster in a Java Application"  
author: gaurav  
categories: [Java, MongoDB, MongoDB Atlas]  
toc: true
description: "In this tutorial, we will see how to connect to a MongoDB Atlas cluster ina Java Application."
---

In this tutorial, we will see how to connect to a MongoDB Atlas cluster ina Java Application.

Your Java application must use the [official MongoDB driver](https://mvnrepository.com/artifact/org.mongodb/mongodb-driver-sync/4.10.2) to connect to a MongoDB Atlas cluster.

You will add the MongoDB driver as dependency in your maven projects `pom.xml` file.

```git
<!-- https://mvnrepository.com/artifact/org.mongodb/mongodb-driver-sync -->
<dependency>
    <groupId>org.mongodb</groupId>
    <artifactId>mongodb-driver-sync</artifactId>
    <version>4.10.2</version>
</dependency>
```
You can check the latest version at https://mvnrepository.com/artifact/org.mongodb/mongodb-driver-sync

To connect to MongoDB Atlas Cluster you need a valid connection String. The connection String is available in Atlas UI. You can get it by login to your Atlas account.

The format of the Connection String is as given below.
```git
mongodb+srv://[username:password@]host[/[defaultauthdb][?options]]mongodb+srv://[username:password@]host[/[defaultauthdb][?options]]
```

For example,
```git
mongodb+srv://user123:password123@cluster0.example.mongodb.net/?retryWrites=true&w=majority
```
Here, `user123` is username and `password123` is a password.

Once you have a valid connection string, you can create a MongoClient using connection string and connect to Atlas cluster as shown below.

```java
import com.mongodb.client.MongoClient;
import com.mongodb.client.MongoClients;
import org.bson.Document;

import java.util.ArrayList;
import java.util.List;

public class ConnectToMongoDBCluster {

    public static void main(String[] args) {
        String connectionString = "mongodb+srv://user123:password123@cluster0.example.mongodb.net/?retryWrites=true&w=majority";
        try (MongoClient mongoClient = MongoClients.create(connectionString)) {
            List<Document> databases = mongoClient.listDatabases().into(new ArrayList<>());
            databases.forEach(db -> System.out.println(db.toJson()));
        }
    }
}
```

When you run the main class `ConnectToMongoDBCluster`, it will connect to MongoDB Atlas cluster and print all the database.



