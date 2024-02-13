# Coupling and Cohesion
##  Design complexity metrics
`Coupling` focuses on complexity between a module and other modules. 

`Cohesion` focuses on complexity within a module. 

These two ideas will help you to better apply object-oriented design principles and achieve a more manageable system.

![](/img/coupling.png)

## Coupling
Coupling for a module captures the complexity of connecting the module to other modules. If your module is highly reliant on other modules, you would say this module is tightly coupled to others. 

You want coupling for your module to be loose or low, not tight. 

![](/img/tight-couple.png)

![](/img/loose-couple.png)

### Degree
Degree is the number of connections between the module and others. With coupling, you want to keep the degree small.

For instance, if the module needed to connect to other modules through a few parameters or narrow interfaces, then degree would be small and coupling would be loose. 


### Ease
Ease is how obvious are the connections between the module and others. With coupling, you want the connections to be easy to make without needing to understand the implementations of the other modules. 


### Flexibility
Flexibility is how interchangeable the other modules are for this module. With coupling, you want the other modules easily replaceable for something better in the future.

## Cohesion
Cohesion represents the clarity of the responsibilities of a module. If your module performs one task and nothing else or has a clear purpose, your module has high cohesion. On the other hand, if your module tries to encapsulate more than one purpose or has an unclear purpose, your module has low cohesion. You want high cohesion. 

## Trade-Off
In general, there's a balance to be made between low coupling and high cohesion in your designs. For a complex system, the complexity can be distributed to between the modules or within the modules. 

As modules are simplified to achieve high cohesion, they may need to depend more on other modules thus increasing coupling. As connections between modules are simplified to achieve low coupling, the modules may need to take on more responsibilities thus lowering cohesion.

>By applying good design to your system they will have low coupling and high cohesion.

