---
layout: post  
title: "Method Overriding In Java"  
author: gaurav
categories: [Java, Java Interview Questions]
toc: false
description: "In this tutorial, we will see the method overriding in Java."
---

In this tutorial, we will see the method overriding in Java.

When **a child class provides a specific implementation for the method already declared in parent class**, it is called a method overriding.

So both parent class and child class will have the same method but with different implementations.

Example:-

```java
/**
 * A Java Program to explain the method of overriding.
 * @author coderolls.com
 *
 */
public class Test {
  public static void main(String[] args) {
    Dog dog = new Dog();
    Cat cat = new Cat();
    
    dog.printSound();
    cat.printSound();
  }

}
class Animal {
  public void printSound() {
    System.out.println("Print sound of animal");
  }
}

class Dog extends Animal {
  @Override
  public void printSound() {
    System.out.println("Dogs bark..!");
  }
}

class Cat extends Animal {
  @Override
  public void printSound() {
    System.out.println("Cats meow..!");
  }
}
```

1. In the above example `Animal` is the parent class. It has the `printSound()` method with its own implementation.
2. Next, we have created a child class `Dog` by extending the parent class `Animal`. We know dogs do bark so we can provide the specific implementation for the  `printSound()` method in the `Dog` class.
3. Also, we have created a child class `Cat` by extending the parent class `Animal`. We can again provide the cat-specific implementation for the  `printSound()` method in the `Cat` class.
4. In the Test class, we have created objects of the Dog and Cat class and invoked their `printSound()` method. We can see, that when we invoke the  `printSound()` method on Dog object `dog`, it prints the `Dogs bark..!` i.e. dog specific implementation. And when we invoke the  `printSound()` method on the Cat object `cat`, it prints the `Cats meow..!` i.e. dog specific implementation
