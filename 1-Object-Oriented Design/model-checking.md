# Model Checking
model checking is a technique that does state exploration. it says, given that you start in this current state, explore all the possible ways you can go into the future and reason about what all those possible future states can look like.

## Example
if at some point in time, ticket A is sold, then at all future states in time, ticket A is only held by exactly one owner.

The model checker can then look at the way the system evolves. the model checker explores the future and then it comes back with an answer. And the answer's either, yep, it's never the case that two people have purchased the same ticket or it says that's wrong and here's the counter example, here's all the weird steps that the system went through, in order to make it so that customer one and two both hold onto the same ticket.

## Pros and Cons
The model checker doesn't only tell you that you're wrong, it says and here's one example were you're wrong.

The problem with model checking is the so called stage space explosion. 

if you model check and you get a counter example, that becomes a new test case. You throw that into your test suite and then when you fix it and run on the second time, that test better fail.

## State Model
Model checkers generate a State Model from your code. A state model is an abstract state machine that can be in one of various states. The model checker then checks that the state model conforms to certain behavioral properties.

## Deadlock
A deadlock is a situation where your system cannot continue because two tasks are waiting for the same resource. 

Your model checker would simulate the different states that could occur in your system and if a deadlock is possible, it would provide details of the violation.

## Race Condition
the model checker can examine the state model for flaws like race conditions.

## Phases of Model Checking
1. The `modeling phase` comes first. This is where you enter the model description. This will be provided in whatever programming language your system uses. You also describe the desired properties.
   
    During the modeling phase, you can perform some `Saturday checks`. These are quick checks that should be easy to do because they usually come from very clear and simple logic. It's like testing if a light bulb is working by flipping a switch on and off. It's beneficial to get rid of these simpler errors before using any model checkers so that you can focus on specifying the more complex properties to check.
    
2. The second phase is the `running phase`, this is when you run the model checker to see how your model conforms to the desired properties that you've wrote in the modeling phase.

3. The last phase is the `analysis phase`. This is where you check if all the desired properties are satisfied and if any are violated. Violations are called `counterexamples`. Your model checker will provide descriptions of violations in your system so that you can analyze how it got to that state.

Using the information from the model checker, you advice yourself where to fix any problems, then run through the phases again. You do this until you can be sure that your software is correct with respect to the desired properties.