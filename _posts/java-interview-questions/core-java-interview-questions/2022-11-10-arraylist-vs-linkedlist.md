---
layout: post  
title: "ArrayList VS LinkedList"  
author: gaurav
categories: [Java, ArrayList, Java Interview Questions]
toc: false
description: "In this article, we will see the difference between ArrayList and LinkedList."
---

In this article, we will see the difference between ArrayList and LinkedList.

## ArrayList Vs LinkedList

{:class="table table-bordered"}
| Property                                   | ArrayList                                                    | LinkedList                                                   |
| ------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Internal Implementation                    | ArrayList internally uses a **dynamic array** to store the elements. | LinkedList internally uses a **doubly linked list** to store the elements. |
| Preference                                 | ArrayList is **preferred for storing and retrieving the data** from the list. | LinkedList is **preferred for inserting and deleting the data** in a list. |
| Store and Retrieve Data                    | Storing and retrieving the data from the ArrayList is faster since it uses a **dynamic array** to store the elements.<br /><br /><br /> Time complexity for retrieving an element by id from the ArrayList is **O(1)**. | Storing and retrieving the data from the LinkedList is slower in comparison since it uses  a **doubly linked list** to store the elements.<br /><br /><br /> Time complexity for retrieving an element by id from the LinkedList is **O(n)**. |
| Data Manipulation ( Insert or delete data) | Manipulation with ArrayList is **slower** because it internally uses an array. <br />In case of removing an element from array or inserting an element in between array, all the other elements are shifted in memory. | Manipulation with LinkedList is **faster** than ArrayList because it uses a doubly linked list, so no bit shifting is required in memory. |
| Interface implementation                   | An ArrayList class can **act as a list** only because it implements List interface only.<br /><br />`ArrayList implements List` | LinkedList class can **act as a list and queue** both because it implements List and Deque interfaces.<br /><br />`LinkedList implements List, Deque` |
| Memory Location                            | The memory location for the elements of an ArrayList is **contiguous**. | The location for the elements of a linked list is **not contagious**. |
| Default Capacity                           | On initialisation, a **default capacity of 10** is assigned to the ArrayList. | There is no case of default capacity in a LinkedList. An empty list is created when a LinkedList is initialized. |

