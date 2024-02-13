# Separation of Concerns
## Goal
Our goal is to create `flexible`, `reusable`, and `maintainable` code. Separation of concerns creates more cohesive classes using abstraction, encapsulation, decomposition, and generalization.

Deciding how to abstract, encapsulate, decompose and generalize to address the many concerns for a given problem is at the core of designing modular software.

## What is Concern
A concern is a very general notion, basically it is anything that matters in providing a solution to a problem.

There are concepts that can be abstracted from the problem space. How these abstractions are implemented in the software can lead to more concerns. Some of these concerns may involve:
- what information the implementation represents, 
- what it manipulates, 
- and what gets presented at the end. 

## Solution
It's easy to get lost and tangled up in all these concerns and their sub-problems. We need to be `organized`, so that we can think about and address these concerns effectively. 

As a software solution is designed and constructed, we express how we can address the different sub-problems by separating them into `separate sections`.

Each concept in the problem space leads to a separate abstraction with its own relevant attributes and behaviors into their own section of code called a `class`.

>Separation of concerns is an ongoing process throughout the design process.

## SmartPhone Example
initial code:

![](/img/smartphone.png)

### Issues
1. there is `low cohesion` in the SmartPhone class, because we have behaviors that are not related to each other. 
2. our smartphone components do not offer us any `modularity`. 
   - We cannot access the camera or the phone separately if we were to build another system that required only one or the other. 
   - We cannot replace our current camera with a different camera, 
   - or replace it with a completely different object, without removing the code for the camera completely in this class.

### Solution
Our SmartPhone class has two concerns. 
- act as a traditional telephone, 
- be able to use the built-in camera to take pictures. 

Now that we have identified these two different concerns, we can separate them out into their own more cohesive classes and encapsulate all the details about each into functionally distinct and independent classes. 

The SmartPhone class will reference instances of our newly created classes, so that the smartphone can act as a `coordinator` of the camera and the phone. This will let our smartphone provide access to all the behaviors of the camera and the phone **without having to know how each component behaves**.

### Implementation

- our smartphone provides the functions of both the camera and the phone, while keeping the functionalities of either one `separate` and `hidden` from each other. 

- Also, we can have a smartphone `constructor` with camera and phone as parameters. Then we can create a new instance of the SmartPhone class by passing in a instances of classes that implemented the camera and phone interfaces. Note that we leave it as a separate responsibility of who will instantiate the appropriate phone and camera objects. The smartphone class does not actually need to know. 

- Finally, the smartphone class has methods that `forward` the responsibilities of using the camera and phone to these objects.

![](/img/phone-uml.png)

![](/img/phone-interface.png)

![](/img/phone-sep.png)

