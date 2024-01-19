# Four Design Principles

## Abstraction
Abstraction is one of the main ways that humans deal with complexity. Abstraction is the idea of simplifying a concept in the problem domain to its `essentials` within some context. Abstraction allows you to better understand a concept by breaking it down into a simplified description that ignores `unimportant details`. 

### Benefits
- emphasizes the essentials needed for the concept and removes details that are not essential. 
- an abstraction should make sense for the concept's purpose.

### Rule of Least Astonishment
the abstraction captures the essential attributes and behavior for a concept with no surprises and no definitions that fall beyond its scope. You don't want to surprise anyone trying to understand your abstraction with irrelevant characteristics.

>The abstractions you create are relative to some context, and there can be different abstractions for one concept. It is up to you to choose the abstraction that is most appropriate for your purpose.

>Within the context of an abstraction, anything other than a concept's essential attributes and behaviors is irrelevant.

If the purpose of your system or the problem changes, don't be afraid to update your abstractions accordingly.

## Encapsulation
Encapsulation forms a self-contained object by bundling the data and functions it requires to work, exposes an interface whereby other objects can access and use it, and restricts access to certain inside details.

### 3 ideas:
it's about making a sort of `capsule`. The capsule contains something inside, some of which you can access from the outside, and some of which you cannot. 
- you bundle attribute values or data, and behaviors or functions, that manipulate those values together into a self-contained object. 
- you can expose certain data and functions of that object, which can be accessed from other objects. 
- you can restrict access to certain data and functions to only within that object. 

![](/img/encapsulation.png)

### Benefits

- You'll find that programming is `easier` when the data, and the code that manipulates that data, are located in the same place.

- Encapsulation helps with data `integrity`. In practice, you often present outside access to all the attributes, except through specific methods. That way, the attribute values of an object cannot be changed directly through variable assignments. Otherwise, such changes could break some assumption, or dependency for the data within an object.

- Encapsulation can `secure` sensitive information.

- Encapsulation helps with software `changes`. The accessible interface of a class can remain the same, while the implementation of the attributes and methods can change. Outsiders using the class, do not need to care how the implementation actually works behind the interface.

- `Black Box Thinking`. Think of a class like a black box that you cannot see inside for details about, how attributes are represented, or how methods compute the result, but you provide inputs and obtain outputs by calling methods. It doesn't matter what happens in the box to achieve the expected behaviors. This distinction between what the outside world sees of a class, and how it works internally is important. Encapsulation achieves what is called, the `Abstraction Barrier`. Since the internal workings are not relevant to the outside world, this achieves an abstraction that effectively reduces complexity for the users of a class.

- This increases `re-usability`, because another class only needs to know the right method to call to get the desired behavior, what arguments to supply as inputs, and what appear as outputs or effects. 

![](/img/blackbox.png)

## Decomposition
Decomposition is taking a whole thing and dividing it up into different parts. Or, on the flip side taking a bunch of separate parts with different functionalities, and combining them together to form a whole. Decomposition allows you to further break down problems into pieces that are easier to understand and solve.

>Sometimes the whole will delegate specific responsibilities to the parts. So, the refrigerator delegates the freezing of food and the storing of that food to the freezer. 

### Fixed / Dynamic Parts

If there is a fixed number, then over the lifetime of the whole object it will have exactly that much of the part object. For example, a refrigerator has a fixed number of freezers, just one. 

but there are sometimes parts with a dynamic number. Meaning, the whole object may gain new instances of those part objects over its lifetime. For example, a refrigerator can have a dynamic number of shelves or food items over time.

### Check by elimination
by a `process of elimination`, we can find out which car parts are dynamic. We know a typical car has one steering wheel, four tires, and one engine at any given time. These numbers do not fluctuate. The number of passengers can change though, making it dynamic. 

### Lifetime
One issue in decomposition involves the lifetimes of the `whole object`, and the `part objects`, and how they could relate. 

- Lifetimes might be closely related. For example, the refrigerator and its freezer have the same lifetime. One cannot exist by itself without the other. 
- But lifetime can also not be so related. The refrigerator and food items have different lifetimes. Either can exist independently.

>lifetime can be assessed with the fact that not-closely relted parts can be disposed or changed many times. in a car, a closely related lifetime would be the frame, and not closely related would be the tires.

### Sharing
You can have whole things contain parts that are shared among them `at the same time`. 

Consider a person who has a daughter in one family, but also a spouse in another family. The two families are regarded as separate wholes, but they simultaneously share the same part. However, sometimes sharing is not possible or intended. 