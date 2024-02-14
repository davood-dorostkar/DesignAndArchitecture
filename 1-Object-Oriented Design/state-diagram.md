# State Diagram
## Definition
A state diagram is a technique that you can use to describe how your system behaves and responds. 

The state diagram follows the states of a system or object, and shows changes between the states as events occur.

State diagrams can describe a single object and illustrate how that object behaves in response to a series of events in your system. 

## Goal
- it can help you determine the different events that might occur during an object's lifetime. 
- State diagrams can also help you to find issues in your system. Like discovering a condition that you did not plan for. 
- Knowing the different states of a system can help to make sure that your tests are complete and correct. 

## State
A state is the way an object exists at a particular point in time. The state of an object is determined by the values of its attributes. 

When an object is in a certain state, it behaves in specific ways or has attributes set to specific values.

## Creating State Diagrams
1. indicate the start of this diagram with a `filled circle`. every state diagram has a filled circle to indicate which is the `starting state`.
2. draw states as `rounded rectangles`.
   
    ![](/img/state-start.png)

3. each state has three important sections, a state `name`, state `variables`, and `activities`. Each state should at least have a state name. 

    ![](/img/state-parts.png)

   - `names` should be meaningful for the states of your object. For example, a car in reverse would have a state named reverse. 
   
   - State `variables` are data relevant to the state of the object. For example, using a course as an object, a relevant variable is the number of students enrolled. 
   
   - `Activities` are actions that are performed when in a certain state, and they're displayed at the bottom. There are three types of activities for each state, entry, exit, and do. `Entry` activities are actions that occur when the state is just entered from another state. `Exit` activities are actions that occur when the state is exited and moves on to another state. And `Do` activities are actions that occur once, or multiple times while the object is in a certain state. 

    ![](/img/state-activities.png)

4. `Events` could change a state label transitions between the states. You draw these `transitions` with `arrows` from one state to another. Each transition arrow will always have an event, and may have a guard condition and an action. The transition and action happens from a given state if the event occurs and the condition is true. 
   
    ![](/img/state-event.png)

5. `Termination` represents an object being destroyed, or the process being completed, and is drawn as a circle with a `filled circle inside`. For example, when using a bank machine, you can represent it returning your card at the end of the process and thus ending in termination. 
   >Not all diagrams have a termination like the vending machine, they may run continuously.

   ![](/img/state-termination.png)

## Example

![](/img/state-example.png)