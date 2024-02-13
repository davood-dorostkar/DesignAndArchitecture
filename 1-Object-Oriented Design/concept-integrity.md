# Conceptual Integrity
onceptual integrity is about creating consistent software. so that even if multiple people worked on the software, it would seem as if there was only one mind guiding all the work.

>conceptual integrity does not mean that the developers in your team don't get to voice their opinions about the software. It's more about everyone agreeing to use certain design principles and conventions.

## Communication
Adopting certain agile development practices like `daily stand-up` meetings and sprint `retrospectives`, where team members can agree to use certain `libraries` or `methods` when addressing certain issues, can help to maintain the consistency of the code. For example, team members can all follow a particular `naming convention`.

## Code reviews
Code reviews are systematic examinations of written code. It's similar to peer review in writing. It's often used to find mistakes in the software, but also to keep different developers consistent with each other. Developers evaluate each other's' code line by line to uncover issues. 

## Using design principles
- `Java Interfaces`: This creates consistency in your software.

## well defined design or architecture 
While software `design` is typically associated with guiding the internal design of software running as a single process, software `architecture` describes how software, running as multiple processes, work together, and how they relate to each other. 

- `Design Patterns`: They provide conventional structures for your classes to solve a design issue and lead to consistency.

## Unifying concepts
It is taking seemingly different things and finding common ground so that each concepts can be seen and treated in similar ways. 

For example, in the `Unix` operating systems, every resource can be seen and manipulated as if it were a `file`. The same set of operations can be used on different types of resources. This simplifies things by making it so that any resource can be treated in the same way.

## small core group
the group that accepts commits to the code base. This is similar to exercising code reviews, but it restricts the review to only core members of your software team. These members will be responsible for ensuring that any software changes follow the overall architecture and design of the software.

>Fred Brooks, in his book, The Mythical Man-Month: "it is better to have a system omit certain anomalous features and improvements, but to reflect one set of design ideas, than to have one that contains many good but independent and uncoordinated ideas."

