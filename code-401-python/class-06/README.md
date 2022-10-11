# Software Design Patterns Simplified

Developers have noticed that they seemed to be approaching problems in similar ways in a bunch of different software’s, then they decided that it would be pretty useful to be able to talk about those approaches using a common vocabulary, so they wouldn’t have to keep explaining what they were referring to. Thus they figured out general versions of these common practices and gave them names like “Adapter” and “Singleton.”

A design pattern is only a description or template for how to solve a problem! that can be used in many different situations.

_**Example:**_ 

In the case of object-oriented programming paradigm, design patterns are generally aimed at solving the problems of object generation and communication, rather than the larger scale problems of overall software architecture.

**Difference between, Programming Paradigms, Architectural Patterns, Design Patterns and Design Principles**

|Programming Paradigms|Architectural Patterns|Design Patterns|Design Principles|
|---|---|---|---|
| A way to classify programming languages based on their coding styles and features. Some paradigms are concerned mainly with implications for the execution model of the language (Procedural, Functional, Object-oriented…)|Reusable solution to a commonly occurring problem in software architecture within a given context. They are similar to software design pattern but have a broader scope (MVC, Micro-services, Layered...)|Reusable solution to a commonly occurring problem in software design within a given context. It is a description or template for how to solve a problem that can be used in many different situations (Bridge, Builder, Strategy…)|Represent a set of guidelines that help developers to avoid having a bad design. Writing code according to proven principles helps achieving code maintainability and simplicity(KISS, Liskov Substitution, Inversion of Control…)|

**Major types of design patterns**

**Creational Patterns:** 

provide ways to instantiate single or groups of objects. Making it easier to create objects in a way that suits the situation.

**_Some Creational Patterns:_**

- **Factory Method:** The factory pattern is used to replace class constructors, abstracting the process of object generation so that the type of the object instantiated can be determined at run-time.

- **Singleton:** The singleton pattern ensures that only one object of a particular class is ever created. All further references to objects of the singleton class refer to the same underlying instance.

- **Abstract Factory:** The abstract factory pattern is used to provide a client with a set of related or dependent objects. The “family” of objects created by the factory are determined at run-time.

**Structural patterns:** 

Structural patterns provide a manner to define relationships between classes or objects. Making it easier for these entities to work together.

**_Some Structural Patterns:_**

- **Facade:** The facade pattern is used to define a simplified interface to a more complex subsystem.

- **Adapter:** The adapter pattern is used to provide a link between two otherwise incompatible types by wrapping the “adaptee” with a class that supports the interface required by the client.

- **Decorator:** The decorator pattern is used to extend or alter the functionality of objects at run-time by wrapping them in an object of a decorator class. This provides a flexible alternative to using inheritance to modify behavior.

**Behavioral Patterns:** 

Behavioral patterns define manners of communication between classes and objects. Making it easier and more flexible for these entities to communicate.

**_Some Behavioral  Patterns:_**

- **Observer:** The observer pattern is used to allow an object to publish changes to its state. Other objects subscribe to be immediately notified of any changes.

- **Mediator:** The mediator pattern is used to reduce coupling between classes that communicate with each other. Instead of classes communicating directly, and thus requiring knowledge of their implementation, the classes send messages via a mediator object.

- **Chain of Responsibility:** The chain of responsibility pattern is used to process varied requests, each of which may be dealt with by a different handler.

---
---

# What is Risk Analysis in Software Testing and how to perform it?

The probability of any unwanted incident is defined as Risk. In Software Testing, risk analysis is the process of identifying the risks in applications or software that you built and prioritizing them to test. After that, the process of assigning the level of risk is done. The categorization of the risks takes place, hence, the impact of the risk is calculated.

**Why use Risk Analysis?**

In any software, using risk analysis at the beginning of a project highlights the potential problem areas. After knowing about the risk areas, it helps the developers and managers to mitigate the risks. When a test plan has been created, risks involved in testing the product are to be taken into consideration along with the possibility of the damage they may cause to your software along with solutions.

_Possible risks:_

- Use of new hardware

- Use of new technology

- Use of new automation tool

- The sequence of code

- Availability of test resources for the application


_Things can't be ignored:_

- The time that you allocated for testing

- A defect leakage due to the complexity or size of the application
 
- Urgency from the clients to deliver the project
 
- Incomplete requirements

**Risk magnitude indicators?**

**High:** means the effect of the risk would be very high and non-tolerable. The company might face loss.

**Medium:** it is tolerable but not desirable. The company may suffer financially but there is a limited risk.

**Low:** it is tolerable. There lies little or no external exposure or no financial loss.

**Risk Identification**

**Business Risks:** The risk that may come from your company or your customer, not from your project.

**Testing Risks:** You should be well acquainted with the platform you are working on, along with the software testing tools being used.

**Premature Release Risk:** a fair amount of knowledge to analyze the risk associated with releasing unsatisfactory or untested software is required.

**Software Risks:** You should be well versed with the risks associated with the software development process.

**Risk Assessment**

![Risk Assessment](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2019/08/Picture1-768x422.png)

**The perspective of Risk Assessment**

Things to take into consideration; the effect, the cause and the likelihood.

**How to perform Risk Analysis?**

1. Searching the risk

2. Analyzing the impact of each individual risk

3. Measures for the risk identified

---
---

# A quick intro to Dependency Injection: what it is, and when to use it

dependency injection is a technique whereby one object (or static method) supplies the dependencies of another object. A dependency is an object that can be used (a service).

"transferring the task of creating the object to someone else and directly using the dependency is called dependency injection."

**Why should I use dependency injection?**

Dependency injection (DI) is the middleman in our code who does all the work of creating the preferred wheels object and providing it to the Car class.

**Types of DI**

- **constructor injection:** the dependencies are provided through a class constructor.

- **setter injection:** the client exposes a setter method that the injector uses to inject the dependency.

- **interface injection:** the dependency provides an injector method that will inject the dependency into any client passed to it. Clients must implement an interface that exposes a setter method that accepts the dependency.

**Benefits of using DI**

- Helps in Unit testing.

- Boiler plate code is reduced, as initializing of dependencies is done by the injector component.

- Extending the application becomes easier.

- Helps to enable loose coupling, which is important in application programming.

**Disadvantages of DI**

- It’s a bit complex to learn, and if overused can lead to management issues and other problems.

- Many compile time errors are pushed to run-time.

- Dependency injection frameworks are implemented with reflection or dynamic programming. This can hinder use of IDE automation, such as “find references”, “show call hierarchy” and safe refactoring.

---
---

## Things I want to know more about

- OOP

---
---

## References

[1] Mahmoud Zalt, Jul 31, 2017, _Software Design Patterns Simplified_, medium.com, accessed 12 October 2022, <https://medium.com/@Mahmoud_Zalt/software-design-patterns-simplified-8a72232d52b1>

[2] Anamika Kalwan, Jul 13, 2020, _TWhat is Risk Analysis in Software Testing and how to perform it?_, https://www.edureka.co/, accessed 12 October 2022, <https://www.edureka.co/blog/risk-analysis-in-software-testing/>

[3] Bhavya Karia, Oct 18, 2018, _A quick intro to Dependency Injection: what it is, and when to use it_, freecodecamp.org, accessed 12 October 2022, <https://www.freecodecamp.org/news/a-quick-intro-to-dependency-injection-what-it-is-and-when-to-use-it-7578c84fa88f/>