# Objective 01 — The Four Pillars of OOP

## Object-Oriented Programming

Object-oriented programming (OOP) is a way of writing computer programs to use "objects" to model data and behaviors. Frequently, computer programs are just a list of instructions to the computer (procedural programming), telling the computer to do certain things in a certain way. However, in object-oriented programming, computer programs make use of "objects" that "talk" to one another to change the data in those objects. Also, because of the way a programmer designs an object-oriented program, other parts of the program or other people can easily reuse the code.

Most programming languages allow many ways of writing computer programs (multi-paradigm). For example, Python allows a developer to write programs using an object-oriented design or a procedural design.

## The Problem with Procedural Programming

The primary purpose of procedural programming is to break down a programming task into a collection of variables, data structures, and subroutines. This is the first approach many programmers learn because it is simple and straightforward. However, when writing larger computer programs that are likely more complex, it is easy for a procedural program to devolve into "spaghetti code"–a phrase for unstructured and difficult-to-maintain code.

## The Four Pillars of OOP

The four pillars of OOP are:

1. Encapsulation
1. Abstraction
1. Inheritance
1. Polymorphism

Below, we will discuss these pillars in greater detail and you will see how each of these concepts, when put into practice, can help a programmer avoid turning their programs into "spaghetti code".

### Encapsulation

The main point of representing an object in object-oriented design is to define the object's public **interface** (the collection of attributes and methods that other objects can use to interact with the object). Other objects in the program need not access the inner workings of that object.

The television is a real-world example. The interface to interact with the television is the remote control. Each button on the remote represents a method you can call on the television object. When we press "volume up" on the remote control, we don't know or care what electronic signals are being sent to change the volume. The television is designed in such a way that those that interact with it through its common interface, the remote control, are free to not care or know about the inner workings of the television.

In programming, hiding the implementation details of an object is called encapsulation.

One thing to note about this process is the need to design the public interface of your objects carefully. Once you've developed a large program with many interacting objects, changing the public interface can have cascading effects that are difficult to correct and keep track of. However, the benefit of encapsulation is you can change the inner workings of your objects without having negative effects on your program. For example, imagine you've carefully designed an object's public interface, but later you realize the inner workings are inefficient and are slowing down your program. You can go refactor the inner workings of that object to improve the efficiency and you won't have to change the other objects in your program at all.

### Abstraction

In its simplest terms, abstraction means dealing with the level of detail that is most appropriate to a task. It is important to remember that the objects in our program are not real objects; they are models of objects. A model car may look like the real thing on the outside, but the engine doesn't run and the brakes likely don't work. The model car is an **abstraction** of the real thing.

It is important to reach the correct level of abstraction for other objects that will interact with it. For instance, in order for a `Driver` object to drive a `Car` object, it needs to have access to a few attributes (`brakes`, `gas_pedal`) and a few methods (`steer()`, `change_gears()`, `apply_brakes()`).

![S1-Illustrations.001](https://i.imgur.com/OV8yunr.jpg)

However, a `Mechanic` object would need a different level of abstraction to interact with the `Car` object. In order for the `Mechanic` to repair the `Car`, it would need access to the `disc_brakes`, `fuel_injected_engine`, and `automatic_transmission` attributes. It would also need access to the `adjust_brake()` and `change_oil()` methods.

![S1-Illustrations.002](https://i.imgur.com/O9d9XkQ.jpg)

Obviously, this is a contrived example, but it illustrates how it is important to be thoughtful on what the right level of abstraction is when designing your objects so that the rest of the objects in your program can interact with that object effectively.

One tip to achieve the right level of abstraction is to only model exactly what the system needs to perform. Don't model what the system might need. By targeting exactly what the system needs, you are more likely to achieve the correct level of abstraction for your program.

### Inheritance

There are many types of relationships that you can model between objects. Inheritance describes the relationship where, "The dog is an animal" or where "The teacher is an employee".

Inheritance is like a family tree. A person could say that they inherited their last name and their brown eyes from their grandfather. Similarly, inheritance allows our object classes to inherit attributes and methods from other classes in the program.

For example, we could create an Animal class that has attributes and methods that all animals within our program possess. However, we may want to create a Dog class that has all the Animal attributes and methods as well as dog-specific attributes and methods.

### Polymorphism

Polymorphism is the ability to treat a class differently depending on which subclass is implemented.

For example, let's say we modeled a game of chess in our program. We created a `Board` class that can accept a move from a `Player` class. Now, the `Board` will call a move function on the `Piece` class. Each of the six pieces are subclasses of the `Piece` class (`Rook`, `Bishop`, `King`, `Knight`, `Queen`, and `Pawn`). Each of these classes has a specific move method that overrides the move methods on the parent classes.

So, the `Board` class has a move method available on its interface. The `Board` class need not know what type of piece it is dealing with when it calls move, because the subclasses override that method. This is an example of ***Polymorphism***.

## Challenge

In your own words, write a short paragraph describing each of the four pillars of OOP.