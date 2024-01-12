# Quality Attributes

`Context` is important to determine what choice of solution is right for the balance of qualities. For example, a home located in a low crime area will require different security needs from one located in a high crime area. For software, talking to its stakeholders will help you to understand the context.

>Besides design reviews, it is worthwhile to slow down while implementing a system and test it carefully. You can prototype alternative ideas and run tests to see what works best.

## Functional Requirements
![](/img/functional.png)

### Common Qualities
- correctness

## Non-Functioanl Requirements
![](/img/nonfunc.png)


### Common Qualities
- performance
- resource usage 
- efficiency
- convenience 
- security
- re-usability: parts of the implementation may have to support use in other similar software products
- flexibility: the implementation may have to allow for future changes
- maintainability

## Common Trade-Offs

Both functional and non-functional requirements are important to satisfy. You'll need to discuss what is acceptable with the stakeholders. 

- there is a common trade-off between performance and maintainability. High performance code may be less clear and less modular making it less maintainable. 
- Another trade-off is security and performance. The extra overhead for high security may reduce performance. 
- Extra code for backward compatibility can worsen both performance and maintainability. 