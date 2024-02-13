# Information Hiding

Information hiding allows models of our system to give others the `minimum` amount of information needed to use them correctly and hide everything else. 

Information hiding allows a developer to work on a module separately with other developers needing to know the implementation details of this module. They can only use this module through its interface. In general things that might change, like implementation details, should be hidden. And things that should not change, like assumptions, are revealed through interfaces.