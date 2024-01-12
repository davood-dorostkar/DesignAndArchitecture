# Class-Responsibility-Collaborator
as we form the conceptual design we are going to represent them with our new technique, the CRC card.

A CRC card has three sections. The top of the card has the class name. On the left are the responsibilities of the class, and on the right, you list collaborators. 

`Collaborators` are other classes that the class interacts with to fulfill its responsibilities.

![](/img/crc-card.png)

>CRC cards are **small** on purpose, so you can't write much on them. This forces you to keep breaking down each component into smaller components and eventually, classes that are small enough to be individually described on index cards. 

a key advantage of using CRC cards is that it allows you to physically reorganize your design. 

## Example of CRC
![](/img/crc-ex.png)

## Extending components
You can find more candidate components by using CRC cards to prototype and simulate various scenarios.

![](/img/expand-crc.png)

## Breaking down components
As well, you probably notice that each component itself contains several different components, which seem small enough to be individual classes for programming. Each of these classes with their responsibilities and collaborators can be described on their own cards.

## Design Meeting
In a design meeting with the software development team, you can have all the cards on the table and discuss a simulation of how these classes work with other classes to achieve their responsibilities.

This allows you to reveal shortcomings in the requirements or design.