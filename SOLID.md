# [SOLID Principles](http://deviq.com/solid/)

## Single Responsibility Principle
### Gather together the things that change for the same reasons. Separate those things that change for different reasons

>The Single Responsibility Principle is closely related to the concepts of coupling and cohesion.  Coupling refers to how inextricably linked different aspects of an application are, while cohesion refers to how closely related the contents of a particular class or package may be.  All of the contents of a single class are tightly coupled together, since the class itself is a single unit that must either be entirely used or not at all (discounting static methods and data for the moment).  When other classes make use of a particular class, and that class changes, the depending classes must be tested to ensure they continue to function correctly with the new behavior of the class.  If a class has poor cohesion, some part of it may change that only certain depending classes utilize, while the rest of it may remain unchanged.  Nonetheless, classes that depend on the class must all be retested as a result of the change, increasing the total surface area of the application that is affected by the change.  If instead the class were broken up into several, highly cohesive classes, each would be used by fewer other elements of the system, and so a change to any one of them would have a lesser impact on the total system.

SRP is not one method per class etc etc.  SRP is a method of modularizing code that gives each module/class one job, that it and only it has responsibility over, which gives every change you make less of an impact over the body of your code as a whole.  
Decent article on SRP: [SRP Article](https://hackernoon.com/you-dont-understand-the-single-responsibility-principle-abfdd005b137)


## Open/Closed Principle
### Open for extension, closed for modification

>This means creating software entities whose behavior can be changed without the need to edit and recompile the code itself. The simplest way to demonstrate this principle is to consider a method that does one thing. Let’s say it writes to a particular file, the name of which is hard-coded into the method. If the requirements change, and the filename now needs to be different in certain situations, we must open up the method to change the filename. If, on the other hand, the filename had been passed in as a parameter, we would be able to modify the behavior of this method without changing its source, keeping it closed to modification.
The Open-Closed Principle can also be achieved in many other ways, including through the use of inheritance or through compositional design patterns like the Strategy pattern.

## Liskov Substitution Principle
### Follow the contract of the base class

>The Liskov Substitution Principle (LSP) states that subtypes must be substitutable for their base types. When this principle is violated, it tends to result in a lot of extra conditional logic scattered throughout the application, checking to see the specific type of an object. This duplicate, scattered code becomes a breeding ground for bugs as the application grows.

## Interface Segregation Principle
### Keep interfaces thin

>The Interface Segregation Principle (ISP) states that clients should not be forced to depend on methods that they do not use.  Interfaces should belong to clients, not to libraries or hierarchies. Application developers should favor thin, focused interfaces to “fat” interfaces that offer more functionality than a particular class or method needs.
In many languages, such as C#, interfaces can inherit from multiple other interfaces. Thus, if you need a larger interface in some parts of the application, but not in others, you may be able to compose it from two or more other interfaces. This is also a good approach to keep in mind if you find yourself refactoring a legacy codebase, which already has large interfaces that you can’t break.

## Dependency Inversion Principle
### New is glue

>The Dependency Inversion Principle (DIP) states that high level modules should not depend on low level modules; both should depend on abstractions. Abstractions should not depend on details.  Details should depend upon abstractions. It’s extremely common when writing software to implement it such that each module or method specifically refers to its collaborators, which does the same. This type of programming typically lacks sufficient layers of abstraction, and results in a very tightly coupled system, since every module is directly referencing lower level modules.

This pretty much states "Use dependency injection", DI is build into .netcore, so it's not a problem.

## Composite Reuse Principle
### Large objects should be composites of small objects

>An implementation of composition over inheritance typically begins with the creation of various interfaces representing the behaviors that the system must exhibit. The use of interfaces allows this technique to support the polymorphic behavior that is so valuable in object-oriented programming. Classes implementing the identified interfaces are built and added to business domain classes as needed. Thus, system behaviors are realized without inheritance.

>In fact, business domain classes may all be base classes without any inheritance at all. Alternative implementation of system behaviors is accomplished by providing another class that implements the desired behavior interface. Any business domain class that contains a reference to the interface can easily support any implementation of that interface and the choice can even be delayed until run time.
