# Inheritance Issues
Each of 4 principles requires you to make a decision on how they apply to your system. Some design decisions will be easier to make than others. But how does everything relate to each other? Can we generalize any parts of the car? Generalization and inheritance are some of the more difficult topics to master in object-oriented programming and modeling.

## Misusing inheritance
when design principles are used improperly, creating more problems than they are meant to solve. 

1. First, you need to ask yourself, am I using inheritance to simply share attributes or behavior without further `adding anything` special in my subclasses? If the answer is yes, then you're misusing inheritance.

2. when you break the `Liskov Substitution` Principle. 


### LSP:
a subclass can replace a superclass, if and only if, the subclass does not change the functionality of the superclass. 

**Example**: 

The Liskov Substitution Principle is violated here, because the whale class overrides the animals classes running and walking functions and replaces them with swimming behaviors. The whale no longer behaves in the way we would expect it superclass to behave.

![](/img/lsp.png)

## Examples of Misusing Inheritance
- in `Java Collections Library`. A stack is understood as first in and last out data structure. the `stack` class inherits from the `vector` class. This means that the stack class is able to return an element at a specified index, retrieve the index of an element and even insert an element into a specific index. These are not behaviors expected from a stack, but because of poor use of inheritance, they are allowed in Java.

- If inheritance does not suit your need, consider whether `decomposition` is more appropriate. A `smartphone` has characteristics of a phone and a camera. It does not make sense for us to Inherit from the `phone` and then add `camera` methods to the subclass smartphone. 

![](/img/bad-inherit-phone.png)

We should be using decomposition to extract out the camera responsibilities, and put them in their own class.

![](/img/good-inherit-phone.png)