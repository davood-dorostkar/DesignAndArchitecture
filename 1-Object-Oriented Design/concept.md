# Concepts
## Top Down Programming
This strategy map the processes in the problem to `routines` to be called. As you broke down the processing needs top down, you made a tree of routines for the eventual solution. These routines would be implemented in a programming language that supported `subroutines`. 

## Analysis and Design
There's a **conceptual design** involving `object-oriented analysis` to identify the key objects in the problem. 

There's also **technical design** involving `object-oriented design` to further refine the details of the objects, including their attributes and behaviors. 

>The design activities happen iteratively and continuously. The goal during software design is to construct and refine models of all the objects. 

## Design Process
These models are useful throughout the design process. 

1. Initially, the focus will be on the `entity` objects from the problem space. 

2. As a solution in software arises, you introduced `control` objects that receive events and coordinate actions. 

3. You also introduce `boundary` objects that connect to services outside your system.

## Documentation
The models also serve as design documentation for your software and can be easily mapped to skeletal source code, particularly for an object-oriented language like Java. 