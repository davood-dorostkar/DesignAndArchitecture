# Desing Principles in UML/Code

A UML Class Diagram, or just Class Diagram for short, allows you to represent your design in more detail than CRC cards can but it's still visual. Class Diagrams are much closer to the implementation and can easily be converted to classes in code.

CRC cards are only good for prototyping and simulating higher level designs.

additional details can be represented in a Class Diagram compared to a CRC card.

The four main design principles are:
- [Abstraction](#abstraction)
- [Encapsulation](#encapsulation)
- [Decomposition](#decomposition)
- Generalization
  - [With Inheritance](#generalization-with-inheritance)
  - [With Interfaces](#generalization-with-interfaces)

## Abstraction
Abstraction allows you to better understand a concept by breaking it down into a simplified description that ignores unimportant details. 

### UML Parts
Each class in the Class Diagram is represented by a box. Each box is divided in three sections:
- The top part is the Class Name. 
- The middle part is the Property section. This would be equivalent to the member variables in your Java class and defines the attributes of the abstraction. 

    Properties are mainly composed of the variable `name` and variable `type`. Variable types, much like in Java, can be classes or primitive types.  

    ![](/img/var-uml.png)

- the bottom part is the operations section which is equivalent to the methods in your Java class and defines the behaviors of the abstraction.

    Operations are mainly composed of the operation `name`, `parameter list` and `return type`.

    ![](/img/op-uml.png)

    If an operation takes a parameter our Class Diagram will now look like this. Note how the parameter list follows the same format as the Class Diagrams properties.

    ![](/img/param-uml.png)

>An abstract method, variable, or class name is denoted in UML with `italics`.

![](/img/uml-abstract.png)


### CRC compared with UML
if we compare the CRC card to our Class Diagram, you might notice how some of the responsibilities on the card turned into properties in the Class Diagram. Some, specifically isOnSale, became an operation. 

![](/img/crc-uml1.png)

![](/img/crc-uml2.png)

### CRC ambiguities
a CRC card does not show a separation between properties and operations. They are all listed together. 

### UML to/from Code
Class Diagrams are very close to implementation, making the translation to Java very easy. 
- Class name in Class Diagram turns into a class in Java. 
- Properties in the Class Diagram turn into member variables. 
- And finally, Operations turn into methods.

Converting code to Class Diagram is also straightforward. 

![](/img/uml-to-code.png)


## Why ever use CRC
Class Diagram still can't replace CRC card for simulating and prototyping different designs. 

CRC cards are `cheap and small`. It is easy to play with different designs with your team in the physical world and the fact that it is far from code, makes you `focus on the problem` and not the implementation. 

Class Diagrams, on the other hand, are much closer to code as you have seen. This is great if you want to clearly communicate your `technical design` to the developers but since you have to specify code-specific things like parameter lists and return values, these are `too detailed` for `conceptual design`. 

The details would be a `distraction` and `time-consuming` to describe when creating your initial designs. 


## Encapsulation
These minus signs indicate that a method or attribute is private. Private attributes can only be accessed from within the class.

By only allowing an object's data to be manipulated via a public method, you can control how and when that data is accessed.

>You only let access to data you allow. If your GPA was on a four point scale, you wouldn't want someone to be able to directly set the value to 10.  

![](/img/private-uml.png)

### Getter Methods
Getter Methods are methods that retrieve data, and their names typically begin with get and end with the name of the attribute whose value you will be returning. Getters often retrieve a private piece of data. 

### Setter Methods
Setter Methods change data, and their names typically begin with set and end with the name of the variable you wish to set. Setters are used to set a private attribute in a safe way.

>Data integrity is why you have Getter and Setter Methods. In order to change a piece of data, you need to go through the correct channels. Data must be accessed in an approved way.

### Example
whether or not an attribute or method is private or public influences its accessibility. Attributes that are private cannot be accessed from anywhere other than from inside the class. This hides them from anything outside of the class. The only way you can manipulate the hidden data is by writing public functions that allow access to it.

![](/img/private-java.png)

>The outside observer does not need to know how your public methods are implemented. Just that they perform as expected. That means you can add additional code to your Getters and Setters if you need to.

## Decomposition
There are three types of relationships found in decomposition:
- association
- aggregation
- composition

They define the interaction between the whole and the parts.

### Association
Association is **some** relationship. This means that there is a `loose` relationship between two objects. These objects may interact with each other for some time. For example, an object of a class may use services/methods provided by object of another class.

**Association In UML**

The straight line between two UML objects denotes that the relationship between them is an association. You can see that there is a `0..*` found on both sides of the relationship. This means a person object is associated with zero or more airline objects. And an airline object is associated with zero or more person objects.

![](/img/association.png)

>Each of them are completely separate entities. If one object is destroyed, the other can continue to exist, unlike human and organ. There can be any number of each item in the relationship. One object does not belong to another.

**Association In Code**

 In this code, the student is passed a sport object to play. The student does not possess the sport beyond playing it. The relationship is between two completely separate objects. A student can play any number of sports. And any number of students can play a sport.

![](/img/association-java.png)

### Aggregation
Aggregation is a `has-a` relationship where a whole has parts that belong to it. There may be sharing of parts among the wholes in this relationship. The `has-a` relationship from the whole to the parts is considered `weak`. What this means is although parts can belong to the wholes, they can also exist independently.

These entities have a relationship, but can exist outside of it.

**Aggregation in UML**

This UML says that for an airliner object, it has zero or more crew members. Also, a crew member object can be had by zero or more airline objects. The `empty diamond` denotes which object is considered the `whole` and not the part in the relationship.

![](/img/aggregation-uml.png)

**Aggregation in code**

These are two objects that have a weak has-a relationship. The pet store has a list of pets that can contain zero or more pets. It has the ability to add pets at any time. Both pets stores and pets can exist without each other.

![](/img/aggragation-java.png)

### Composition
Composition is an exclusive containment of parts, otherwise known as a `strong has-a` relationship. What this means is that the whole cannot exist without its parts. If loses any of its parts, the whole ceases to exist. If the whole is destroyed, then all of its parts are destroyed too. Usually, you can only access the parts through its whole. Contained parts are exclusive to the whole.

**Composition in UML**

This UML describes the relationship between a house and a room, that a house object has `one or more` room objects. The `filled in diamond` next to the house means that the house is the `whole` in the relationship. If the diamond is filled in, it means that has-a relationship is `strong`. The two related objects cannot exist without each other.

![](/img/composition-uml.png)

**Composition in code**

In this example, the brain is `created at the same time` that the human object is. The brain does not need to be `instantiated anywhere` else, nor does it need to `be passed` into the human object on creation. The brain is `automatically created` with the human. The two parts, human and brain, are tightly dependent with one not being able to exist without the other.

![](/img/composition-java.png)

**Another Example**

The employee cannot exist without a salary. And the salary cannot exist without an employee. On instantiating an employee, the salary part is made. The salary must always exist as long as the employee does from that point on.

![](/img/composition-java2.png)

## Generalization with Inheritance
You simply connect two classes with a solid lined arrow. This indicates, that two classes are connected by inheritance. the superclasses are always toward the top, and the subclasses are always toward the bottom. 

>You do not need to put any of the inherited superclasses attributes and behaviors into the subclass. 

![](/img/gen-inherit.png)

>The `hash` symbol is used to communicate that the animals attributes are protected. 

### Protected term
In Java, a `protected` attribute or method can only be accessed by, 
- the encapsulating class itself, 
- all subclasses, 
- all classes within the same package. In Java, a `package` is simply a means in which the classes can be organized into a `namespace` that represents those classes. 

### abstract term
Since an animal is a generalization of specific species, we do not want to be able to create an animal object on its own. We use the keyword `abstract` to declare that this class cannot be `instantiated`. That means that we cannot create an animal object. 

![](/img/abstract.png)

### extends term
We declare `inheritance` in Java using the keyword `extends`.

![](/img/extends.png)

### Constructors
Classes can have `implicit` constructors or `explicit` constructors. 
- In implicit constructor all attributes are assigned zero or null, when using the default constructor. 
  
  ![](/img/impl-constr.png)

- Explicit constructors, are use of that we can assign values to attributes during instantiation. 
  
  ![](/img/expl-constr.png)

>A subclass's constructor must call its superclass's constructor, if the superclass has an explicit constructor. This is because explicit constructors of the superclass must be referenced by the subclass. Otherwise the superclass attributes would not be appropriately initialized. 

### super term 
In order to access the superclass's attributes, methods and constructors, the subclass uses the keyword called Super.

![](/img/super.png)

### overriding methods
Subclasses can override the methods of its superclass, meaning that a subclass can provide its own implementation for an inherited superclass's method. 

![](/img/overriding.png)

### Multiple Inheritance in Java
For Java, only single implementation inheritance is allowed. Well a superclass can have multiple subclasses. A subclass can only inherit from one superclass. 

## Generalization with Interfaces
Unlike a class, however, an interface only declares method signatures, and no constructors, attributes, or method bodies. It specifies the expected behaviors in the method signatures, but does not provide any implementation details. 

So, an interface is like a contract to be fulfilled by implementing classes. In both inheritance and interfaces, you achieve consistency between the dog type and the animal type.

Unlike inheritance, interfaces are not a generalization of a set of classes. It is important to understand that interfaces are not classes. They are used to describe behaviors. All that an interface contains are method signatures. 

### Interface in code
In JAVA, we use the key word interface to indicate that we are creating one. Standard JAVA naming convention places the letter I before an actual name to indicate an interface. 

- We only show that an animal has these behaviors.
- the interface does not encapsulate any of the attributes of an animal. 

![](/img/interface.png)

### implements term
Our dog class has declared that it will implement or describe the behaviors that are in the interface. When you do this, you must have all the method signatures explicitly declared and implemented in the class.

![](/img/implements.png)

### Interfaces in UML
Interfaces are explicitly noted in UML class diagrams using guillemets, to surround the words `interface`. The interaction between an interface and a class that is implementing the interface is indicated using a `dotted arrow`. 

![](/img/interface-uml.png)

### Interface Inheritance
Just like with class inheritance, interfaces can inherit from other interfaces. And just like with class inheritance, interface inheritance should not be abused.

**Example**

what if we need to implement the movement of a plane or a submarine that can also move in the zed-axis? We do not want to add an extra behavior to the interface, because on-land and on-water vehicles do not move along the zed-axis. So We can create a second interface that will inherit from our first one.

![](/img/super-interface.png)

![](/img/interface-inherit.png)

Now, we can use the IVehicleMovement3D interface for all vehicles that have three-dimensional movement without having to add the Zed-axis movement to the interface used by the on-land and on-water vehicles.

 ### Interface advantages
1. Like abstract classes, which are classes that cannot be instantiated, interfaces are a means in which you can implement `polymorphism`. 

In object oriented languages, polymorphism is when two classes have the same description of a behavior, but the implementations of the behavior may be different. It is simple to achieve in JAVA using an interface.

2. `multiple inheritance` is when a subclass has two or more super classes. While this is possible to do with other object oriented languages, like C++, JAVA doesn't support Multiple Inheritance. 
   
   >This is because inheriting from two or more superclasses can cause Data Ambiguity. When your subclass inherits from two or more superclasses that have attributes with the same name or behaviors with the same method signature, how do you distinguish between them? 

   Interfaces do not run into this issue. In JAVA, a class can implement as many interfaces as we want. This is because of the nature of interfaces. 

![](/img/multi-inherit.png)

![](/img/class-interface.png)