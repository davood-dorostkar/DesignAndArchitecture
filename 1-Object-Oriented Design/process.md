# Design in the Software Process

![](/img/scrum.png)

## Avoid starting straight into code
Evidence suggest that diving straight into implementation work is a leading cause of project failure. In a survey from The Standish Group, the most common causes of project failures are related to issues in requirements and design.

![](/img/inc-req.png)

Once you begin coding a solution and depend on certain assumptions, it can become difficult to change those assumptions.

## Elicit Requirements
Eliciting requirements involves not only listening to what the client is telling you, but asking questions to clarify what the client has not told you.

## Conceptual Design
The design activity involves taking requirements and outlining a solution. This activity involves producing a conceptual design and then a technical design, which results in two corresponding kinds of artifacts, conceptual mockups and technical diagrams.

Each component has a task it needs to perform, known as `responsibility`.

![](/img/concept-des.png)

I recommend finishing the conceptual design before moving on to forming the technical design. The clearer your conceptual design is, the better your technical designs will be.

## Technical Design
Describing how responsibilities are met is the goal of technical design.

In a technical design, you start specifying the technical details of each component. This is done by splitting components into smaller and smaller components that are specific enough to be designed in detail. 


By breaking down components more and more into further components, each with specific responsibilities, you get down to a level where you can do a detailed design of a particular component.

If components and connections and their responsibilities in your conceptual design prove impossible to achieve in the technical design. Or fail to meet the requirements, you will need to go back to your conceptual design and rework it. 