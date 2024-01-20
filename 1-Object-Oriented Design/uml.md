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

