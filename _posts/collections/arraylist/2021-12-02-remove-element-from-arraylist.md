---
layout: post
title: "How To Remove An Element From An ArrayList?"
author: gaurav
categories: [Collections, ArrayList]
toc: true
description: "In this article, we will see how to remove an element from an ArrayList."
---
In this article, we will see how to remove an element from an [ArrayList In Java](https://coderolls.com/arraylist-in-java/).
## Introduction

We have seen [how we can add an element to an ArrayList](http://coderolls.com/add-element-in-arraylist/) and  [how we can change the elements of an ArrayList](https://coderolls.com/change-element-in-arraylist/), now we will see how we can remove an element from an ArrayList.

To remove an element from an ArrayList, we use the `remove()` method.

Using the ' Remove (Object o)` method, we can remove the specified object from an ArrayList.

Using the `remove(int index)` method, we can remove the object at the specified index from an ArrayList.

Let's see both methods one by one.

## 1. Remove an element from an ArrayList using the `remove(Object o)` method

The `remove(Object o)` method removes the first occurrences  of the specified object from the ArrayList.

If the specified object `o` is not present in the ArrayList, the ArrayList remains unchanged.

The method signature is as `public boolean remove(Object o)`

The `remove(Object o)` method has a return type as a `boolean`. It returns `true` if it found an occurrence of the specified object and if it removes. Otherwise, it returns `false`.

We will see a Java program to remove an element from the ArrayList using the `remove(Object o)` method.

### Example 1

```java
import java.util.ArrayList;

/**
 * A Java program to remove an element from ArrayList
 * using the remove(Object o) method.
 * 
 * @author coderolls.com
 *
 */
public class ArrayListRemoveExample {

  public static void main(String[] args) {
  
    ArrayList<String> arrayList = new ArrayList<String>();
    
    //adding elements to the ArrayList using the normal add() method
    arrayList.add("Red");
    arrayList.add("Green");
    arrayList.add("Pink");
    
    System.out.println("ArrayList before removing an element"+ arrayList); // ArrayList before removing an element[Red, Green, Pink]
    
    //Remove "Pink" from the ArrayList
    arrayList.remove("Pink");
    
    System.out.println("ArrayList after removing an element"+ arrayList);// ArrayList after removing an element[Red, Green]
  }
}
```
Output:
```
ArrayList before removing an element[Red, Green, Pink]
ArrayList after removing an element[Red, Green]
```
### Example 2

In the above example, we have removed the string object. In this example, we will take an employee object. The Employee.java will look like the given below

```java
/**
 * An employee class for ArrayList remove example
 * @author coderolls.com
 *
 */
public class Employee {
	
  private int id;
  
  private String name;
  
  private int salary;
  
  // a constructor will all the fields
  public Employee(int id, String name, int salary) {
    this.id = id;
    this.name = name;
    this.salary = salary;
  }
  
  // getters and setters for the variables
  public int getId() {
    return id;
  }
  
  public void setId(int id) {
    this.id = id;
  }
  
  public String getName() {
    return name;
  }
  
  public void setName(String name) {
    this.name = name;
  }
  
  public int getSalary() {
    return salary;
  }
  
  public void setSalary(int salary) {
    this.salary = salary;
  }
  
  // Override to string method to print student objects
  @Override
  public String toString() {
    return "{"+this.getId()+", "+ this.getName()+ ", "+this.getSalary()+"}";
  }
}

```

Now, we will create an ArrayList of the above employee objects and try to remove them from the arraylist using `remove(Object o)`.

```java
import java.util.ArrayList;
/**
 * A Java program to remove an object from ArrayList
 * using the remove(int index) method.
 * 
 * @author coderolls.com
 *
 */
public class ArrayListRemoveObjectExample {

  public static void main(String[] args) {
  
    ArrayList<Employee> arrayList = new ArrayList<Employee>();
    
    //create Employee objects
    Employee john = new Employee(100, "John Doe", 20000);
    Employee nathasha = new Employee(101, "Natasha Putin", 28000);
    Employee remo = new Employee(102, "Remo Smith", 40000);
    
    //adding employee objects to the arrayList using the normal add method
    arrayList.add(john);
    arrayList.add(nathasha);
    arrayList.add(remo);
    
    System.out.println("ArrayList before removing an employee Object:\n"+ arrayList); 
    
    //Remove object using the remo0ve(Object o) method 
    //Remove employee nathasha from the arrayList
    arrayList.remove(nathasha);
    
    System.out.println("\nArrayList after removing an employee Object:\n"+ arrayList);
  }
}
```
Output:
```
ArrayList before removing an employee Object:
[{100, John Doe, 20000}, {101, Natasha Putin, 28000}, {102, Remo Smith, 40000}]

ArrayList after removing an employee Object:
[{100, John Doe, 20000}, {102, Remo Smith, 40000}]
```

## 2. Remove an element from an ArrayList using the `remove(int index)` method

The `remove(int index)` removes an element at the specified position from the ArrayList.

The method signature is as `public E remove(int index)`

Once we remove an element from the ArrayList using the `remove(int index)` method, the remaining elements after the specified index get shifted left and its indices are updated.

The return type is an `E`. It returns the element that was removed from the list.

We will see a Java program to remove an element from the ArrayList by passing its index as an argument to the `remove(int index)` method.

### Example 1

```java
import java.util.ArrayList;

/**
 * A Java program to remove an element from ArrayList
 * using the remove(int index) method.
 * 
 * @author coderolls.com
 *
 */
public class ArrayListRemoveExample2 {

  public static void main(String[] args) {
  
    ArrayList<String> arrayList = new ArrayList<String>();
    
    //adding elements to the arrayList using normal add method
    arrayList.add("Apple");
    arrayList.add("Orange");
    arrayList.add("Guava");
    arrayList.add("Banana");
    
    System.out.println("ArrayList before removing an element"+ arrayList);
    // ArrayList before removing an element[Apple, Orange, Guava, Banana]
    
    //Remove the element at the specified index i.e. 2
    //Remove "Guava" from the arrayList
    arrayList.remove(2);
    
    System.out.println("ArrayList after removing an element"+ arrayList);
    // ArrayList after removing an element[Apple, Orange, Banana]
  }
}
```
Output:
```
ArrayList before removing an element[Apple, Orange, Guava, Banana]
ArrayList after removing an element[Apple, Orange, Banana]
```

### Example 2

In the above example, we have removed the string object. In this example, we will take an employee object. The Employee.java will look like the given below

```java
/**
 * An employee class for ArrayList remove example
 * @author coderolls.com
 *
 */
public class Employee {
	
  private int id;
  
  private String name;
  
  private int salary;
  
  // a constructor will all the fields
  public Employee(int id, String name, int salary) {
    this.id = id;
    this.name = name;
    this.salary = salary;
  }
  
  // getters and setters for the variables
  public int getId() {
    return id;
  }
  
  public void setId(int id) {
    this.id = id;
  }
  
  public String getName() {
    return name;
  }
  
  public void setName(String name) {
    this.name = name;
  }
  
  public int getSalary() {
    return salary;
  }
  
  public void setSalary(int salary) {
    this.salary = salary;
  }
  
  // Override to string method to print student objects
  @Override
  public String toString() {
    return "{"+this.getId()+", "+ this.getName()+ ", "+this.getSalary()+"}";
  }
}

```

Now, we will create an arraylist of the above employee objects and try to remove them from the arraylist using `remove(int index)`.
```java
import java.util.ArrayList;

/**
 * A Java program to remove an object from ArrayList
 * using the remove(int index) method.
 * 
 * @author coderolls.com
 *
 */
public class ArrayListRemoveObjectExample2 {

  public static void main(String[] args) {
  
    ArrayList<Employee> arrayList = new ArrayList<Employee>();
    
    //create Employee objects
    Employee john = new Employee(100, "John Doe", 20000);
    Employee nathasha = new Employee(101, "Natasha Putin", 28000);
    Employee remo = new Employee(102, "Remo Smith", 40000);
    
    //adding employee objects to the arrayList using the normal add method
    arrayList.add(john);
    arrayList.add(nathasha);
    arrayList.add(remo);
    
    System.out.println("ArrayList before removing an employee Object:\n"+ arrayList); 
    
    //Remove object using the remove(int index) method 
    //Remove employee nathasha from the arrayList, so pass Natasha's index
    arrayList.remove(1);
    
    System.out.println("\nArrayList after removing an employee Object:\n"+ arrayList);
  }
}
```
Output:
```
ArrayList before removing an employee Object:
[{100, John Doe, 20000}, {101, Natasha Putin, 28000}, {102, Remo Smith, 40000}]

ArrayList after removing an employee Object:
[{100, John Doe, 20000}, {102, Remo Smith, 40000}]
```

## Conclusion

We can remove an element from the ArrayList in two ways.

1. `remove(Object o)` - we can remove the specified object from the ArrayList
2. `remove(int index)` - We can remove an element at the position (index) specified

---

The example Java programs given in the above tutorial can be found at [this GitHub Repository](https://github.com/coderolls/blogpost-coding-examples/tree/main/collections/arraylist/remove-element-from-arraylist).

If you know any other way, please comment below.
