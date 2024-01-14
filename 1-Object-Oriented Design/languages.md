# Languages

Over the years, ideas used in computer languages have caused a shift in programming paradigms. We needed to change the way in which programs were written in order to address the latest problems more effectively.

## Imperative Paradigm
In 1960s, the two most popular programming languages were `COBOL` and `Fortran`. They followed an imperative paradigm which broke up large programs into smaller programs called `subroutines`, which are like methods in Java. 

### Global Data
to maximize processing performance they used global data because they are all located in one place in the computer's memory for a program. With globally accessible variables, all the subroutines would be able to access them to do their necessary calculations.

![](/img/global-data.png)

### Issues with imperative paradigm
- With global data, it was possible that changes in the data could have weird side effects on the program. Sometimes, a subroutine would run into cases where the global data was not as expected. 

## Improved Imparative Paradigm
The need for better data management led to changes to imperative programming and the rise of languages like `Algol 68` and `Pascal` in the 1970s. 

### key changes
1. The idea of `local variables` was introduced. Subroutines were called procedures which could contain nested procedures. And each one could have their own variables. 

![](/img/procedures.png)

2. Algol 68 and Pascal support the notion of an `abstract data type`, which is a datatype that is defined by the programmer and not built into the language. An abstract data type is essentially a grouping of related information that is denoted with a type. It was a way to organize data in a meaningful way

### issues
Problems were becoming more complex. For developers, this meant that software was becoming so massive that having one file for his program was becoming difficult to maintain.

## Modular Languages
New languages arose such as `C` and `Modula-2` that provided a means to organize programs and allow developers to more easily create multiple but unique copies of their abstract data types. 

Programs could now be organized into separate files. In C, each file contained all the associated data and functions that manipulated it and it declared what could be accessed through a separate file called the `Header File`. 

![](/img/header-files.png)

### issues
These languages do not make it easy for an abstract data type to `inherit` from another. you can define as many data types as he wants but cannot declare that one type is an `extension` of another type. 

## Object-Oriented Paradigm
During 1980, the concepts of Object-Oriented Design became popular.

### The goal of object-oriented design
- to make an abstract data type easier to write, 
- structure a system around abstract data types called classes 
- introduce the ability for an abstract data type to extend another by introducing a concept called inheritance. 

### advantages
the system will mimic the structure of the problem, meaning that any object-oriented program is capable of representing real world objects or ideas with more fidelity. 

### structure
- `Class` files replace the standard files in C and Modula-2. 

- Each class defines a type with associated data and functions. These functions are also known as `methods`.

![](/img/oo-languages.png)

## Lessons Learned

while object-oriented programming is a powerful tool, it is not the only one in your toolbox. Object-oriented design is not always the best approach for everything because the design may not fit the problem. Remember, that it is more important to be efficient with your time even if this means taking a non-object-oriented approach.