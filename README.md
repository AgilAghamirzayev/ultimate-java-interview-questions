# 🚀 Ultimate Java Developer Interview Questions

# Table of Contents

## - [Java Versions and Features](sections/java-versions.md)
## - [String](sections/strings.md)

- [Java](#java) 

    - [OOP](#oop)
        - [What are the 4 pillars of OOPS?](#question-what-are-the-4-pillars-of-oops)
    - [Collections](#collections)
    - [Multithreading](#multithreading)
    - [Lambda](#lambda)
    - [Stream](#stream)
        - [What is the difference between map and flat map](#question-what-is-the-difference-between-map-and-flat-map)

- [SOLID](#solid)
- [Design Patterns](#design-patterns)
- [Spring Boot](#spring-boot)
    - [Core](#core)
      - [How HTTPS requests flow through the Spring Boot application?](https://medium.com/javarevisited/top-15-spring-boot-interview-questions-and-answers-for-java-developers-series-24-q-a-on-actuators-7253402c671)
      - [What happens in the background when a Spring Boot Application is “Run as Java Application”?](https://medium.com/javarevisited/top-15-spring-boot-interview-questions-and-answers-for-java-developers-series-24-q-a-on-actuators-7253402c671)
    - [JPA](#jpa)
    - [Caching](#caching)
    - [Transaction](#transaction)
    - [AOP](#aop)
      - [What is AOP?](#what-is-aop)
      - [Which design pattern applies to spring AOP?](#which-design-pattern-applies-to-spring-aop)
      - [What are the benefices of AOP?](#what-are-the-benefices-of-aop)
      - [AOP use cases](#aop-use-cases)
      - [Advantages and Disadvantages of AOP](#advantages-and-disadvantages-of-aop)
      - [AOP terminology](#aop-terminology)
      - [What advice types are in AOP?](#what-advice-types-are-in-aop)
      - [What type of weaving do you know?](#what-type-of-weaving-do-you-know)
      - [What are the differences of Spring AOP and AspectJ?](#what-are-the-differences-of-spring-aop-and-aspectj)
      - [AOP pointcut execution](#aop-pointcut-execution)
- [Microservices](#microservices)
    - [Patterns](#patterns)
- [Algorithms](#algorithms)
- [Database](#database)
- [Communication protocols](#communication-protocols)
- [DevOps](#devops)
    - [Docker](#docker)
        - [What is the difference between Container vs virtual machine?](#question-what-is-the-difference-between-container-vs-virtual-machine)
- [CI/CD](#cicd)
- [Git](#git)

# Java

---


## OOP

### Question: What are the 4 pillars of OOPS?

Answer:

![oop.png](images/oop.png)

There are four pillars of OOPS:

1. Abstraction
2. Encapsulation
3. Inheritance
4. Polymorphism

Let’s take a look at them:

1. Abstraction is a way of hiding the implementation details of something and showing only the functionality that the
   user needs to know.
   This makes your code more organized and easy to understand because you can work with high-level ideas rather than
   getting lost in the complexities of every detail.

   Real world examples:

   - Car engine: When you drive a car, you don't need to know how the engine works or how the brakes work. You just need to
     know how to steer the car and how to use the pedals. The car abstracts away all the complex internal details so
     that you can focus on driving.

   - Computer: When you use a computer, you don't need to know how the hardware works or how the operating system works.
     You just need to know how to use the mouse and keyboard and how to open programs and files. The computer abstracts
     away all the complex internal details so that you can focus on using the computer to do your work.

    In java, Abstraction can be achieved in two ways:

   - Abstract classes
   - Interfaces

2. Encapsulation may be used by creating ‘get’ and ‘set’ methods in a class which are used to access the fields of the 
   object.
   Typically, the fields are made private while the get and set methods are public.

   To achieve encapsulation in Java:
   - Declare the variables of a class as private.
   - Provide public setter and getter methods to modify and view the variables values.

   Benefits of Encapsulation
   - The fields of a class can be made read-only or write-only.
   - A class can have total control over what is stored in its fields.

3. Inheritance.
   Using inheritance means defining a parent-child relationship between classes, by doing so, you can 
   reuse the code already defined in the parent class.
   Code re-usability is the biggest advantage of Inheritance.

   _Java does not allow multiple inheritance through classes, but it allows it through interfaces._

4. Polymorphism
   Poly means many and Morph means forms. Polymorphism is the process in which an object or function takes different forms. 
   
   There are 2 types of Polymorphism :

   ✅ Compile Time Polymorphism (Method Overloading)

   ✅ Run Time Polymorphism (Method Overriding)


   In Method overloading, two or more methods in one class have the same method name but different arguments. It is called 
   as Compile time polymorphism because it is decided at compile time which overloaded method will be called.   

   Overriding means when we have two methods with same name and same parameters in parent and child class. Through overriding, 
   child class can provide specific implementation for the method which is already defined in the parent class.

## Collections

## Multithreading
### Question: What is daemon threads?

### Question: What does thread.join() method? 


### Question: What is the difference between latency and throughput

- **Latency** - The time to completion of a task. Measured in time units
- **Throughput** - The amount of tasks completed in a given period. Measured in tasks/time unit



Answer:


## Lambda

## Stream

## Stream

### Question: What is the difference between map and flat map

- `map` is used to transform each element of a collection independently and returns a new collection with the 
transformed elements.
- `flatMap` is used to transform each element of a collection into a sequence of elements and then flatten the 
  sequences into a single collection.

In other words, map applies a one-to-one transformation to each element, while flatMap applies a one-to-many 
transformation and flattens the resulting sequences into a single collection.

Example using map:

    List<String> words = Arrays.asList("Hello", "world");
    List<Integer> wordLengths = words.stream()
                                     .map(String::length)
                                     .collect(Collectors.toList());
    // Result: [5, 5]

Example using flatMap:

    List<List<Integer>> listOfLists = Arrays.asList(Arrays.asList(1, 2), Arrays.asList(3, 4));
    List<Integer> flattenedList = listOfLists.stream()
                                             .flatMap(List::stream)
                                             .collect(Collectors.toList());
    // Result: [1, 2, 3, 4]



# SOLID

---

# Design patterns



---

# Spring Boot

## Core

## JPA

## Caching

## Transaction

## AOP

### What is AOP?

Answer:
- Programming technique based on the concept of an Aspect
- Aspect encapsulates cross-cutting logic
- Cross-cutting concerns (concern - logic/functionality)

![img.png](images/cross-cutting-concern.png)

### Which design pattern applies to spring AOP?
Answer: Proxy design pattern

### What are the benefices of AOP?
Answer:

-
-
-

### AOP use cases
Answer:



### Advantages and Disadvantages of AOP
Answer:

- Advantages:
  - Reusable modules
  - Resolve code tangling
  - Resolve code scatter
  - Applied selectively based on configuration
- Disadvantages:
  - Too many aspects and app flow is hard to follow
  - Monitor performance cost for aspect execution (runtime weaving)

### AOP terminology
Answer:

- Aspect: module of code for a cross-cutting concern
- Advice: What action is taken and when is should be applied
- Join Point: When to apply code during program execution
- Point cut: A predicate expression for where advice should be applied


### What advice types are in AOP?
Answer:

- Before advice: run before the method
- After finally advice: run after the method (finally)
- After returning advice: run after the method (success execution)
- After throwing advice: run after the method (if exception thrown)
- Around advice: run before and after the method

### What type of weaving do you know?
Answer:

- Compile time 
- Load time (runtime)
- _Note: Runtime weaving is the slowest_


### What are the differences of Spring AOP and AspectJ?




### AOP pointcut execution



---

# Microservices

## Patterns



---

# Algorithms


---

# Database

## How can you find slow queries in PostgreSQL?
Answer:

- Using the slow query log: The slow query log is a file that logs all queries that take longer than a certain amount of time to execute.
- Using auto_explain extension: PostgreSQL can help to surface the slow queries, Lets explore in subsequent sections.
- Using pg_stat_statements: pg_stat_statements is a built-in PostgreSQL extension that collects statistics about SQL statements. This information can be used to identify the queries that are consuming the most CPU or I/O, and the ones that are causing the most waits.





---

# Communication protocols

---

# DevOps

---

## Docker

### Question: What is the difference between Container vs virtual machine

Answer:

![container-virtual-machine.png](images/container-virtual-machine.png)

| Feature                     | Container                                                                               | Virtual machine                       |
|-----------------------------|-----------------------------------------------------------------------------------------|---------------------------------------|
| Resource usage              | More efficient                                                                          | Less efficient                        |
| Start-up and shut-down time | Faster                                                                                  | Slower                                |
| Isolation                   | Shares the operating system kernel, but has its own isolated file system and resources	 | Has its own isolated operating system |
| Security                    | Less secure than VMs	                                                                   | More secure than containers           |

- Containers:
    - Share the host OS kernel, making them lightweight and efficient.
    - Minimal overhead, faster to start, and use fewer resources.
    - Provide process-level isolation; applications share the host kernel.
    - Highly portable across different environments.
    - Ideal for microservices, cloud-native apps, and quick scaling.

- Virtual Machines:
    - Run with their own OS and kernel, which can be resource-intensive.
    - Have more overhead, requiring additional memory and CPU resources.
    - Offer strong isolation due to separate OS instances.
    - Less portable, especially when migrating between hypervisors or providers.
    - Suited for legacy apps, strong isolation, and running different OS on one host.

# CI/CD

---

# GIT

---