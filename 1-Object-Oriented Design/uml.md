# Desing Principles in UML

A UML Class Diagram, or just Class Diagram for short, allows you to represent your design in more detail than CRC cards can but it's still visual. Class Diagrams are much closer to the implementation and can easily be converted to classes in code.

CRC cards are only good for prototyping and simulating higher level designs.

additional details can be represented in a Class Diagram compared to a CRC card.

## UML Parts
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

## Abstraction
Abstraction allows you to better understand a concept by breaking it down into a simplified description that ignores unimportant details. 

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