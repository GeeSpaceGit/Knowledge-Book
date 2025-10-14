- Within the design process, many principles, considerations and strategies help designers execute the SD process in an effective and consistent manner. These help designers manage and simplify problems, consider the impacts of their proposed solutions and establish a  foundation for decision making during design.
- Design principles refer to knowledge matter that has been found effective throughout the years in multiple projects on the years in multiple projects on different domains.
- Design principles are applicable on most design projects; therefore, their use is expected to help achieve high-quality designs. On the other hand, design considerations are recommendations that help designers in the design process; they may or may not be followed. Finally, design strategies consist of tactical approaches in which design principles and considerations can be employed to drive the design process.

# General SD Principle
- Many design principles have emerged to become fundamental drivers for  decision making during the SD process.
- Provide designers with a foundation from which other more sophisticated methods can be applied. These principles are nit specific to any particular design strategy or process, so they are fundamental to all software design efforts and can be applied during architectural, detailed and construction designs,

## Modularization

## Abstraction

## Encapsulation

## Coupling and cohesion
### Coupling 
>[!note] Coupling defined by IEEE
>The manner and degree of interdependence between software modules.

- Can be applied during software architecture, detailed design and construction design to measure the degree of dependency of design units such as an architectural subsystem, a class in a detailed design's class diagram or function in code.
- Can be used to determine how much an architectural subsystem depends on other architectural subsystem, how much a class depends on other classes and how much a function depends on other functions.
- Design units can depend on well-defined and stable interfaces, common data structures and internal structure of other design units.

| Types of Coupling | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Content coupling  | Represent the most severe type of coupling, since it refers to modules that  modify and rely on the internal details of other module.<br>                                                                                                                                                                                                                                                                                                                     |
| Common coupling   | Refer to dependencies based on a common access area, such as a global variable.<br><br>This type of coupling results in lesser severity than content coupling.<br>                                                                                                                                                                                                                                                                                            |
| Data coupling     | The type of dependency in which design units communicate with each other only through a set of data coupling.<br><br>Does not depend on the internals of other design unit and unlike common coupling common coupling it provides more control over the form of dependency. When dependency between modules relies on data parameters that are globally inaccessible, design units are shielded from undesired changes to the data by other design units.<br> |
| Control coupling  | Used to verify that all the interactions between modules have been covered by at least one test.<br>                                                                                                                                                                                                                                                                                                                                                          |
| Hybrid coupling   | A combination of 2 or more types of coupling. This type of coupling can introduce complexities in understanding and maintaining the  system, as it involves multiple ways in which modules are interdependent                                                                                                                                                                                                                                                 |


>[!example] High degree of coupling give rise to negative side effects.
>- Reusability and manageability of the design units decrease since error or changes to the independent unit propagate to all dependent units.
>- Does the complexity of managing and maintaining design units.

### Cohesion
- Provides an important principle that measures how much design units that are grouped together actually belong together actually belong together based on different criteria.
- During the software architecture activity, logical and communication cohesive modules are typical, whereas, during the detailed and construction design activities, functional, procedural and temporal cohesiveness are more expected.
- Highly cohesive modules increase reusability.
>[!note] Definition of Cohesion from IEEE
>The manner and degree to which the tasks performed by  a single software module are related to one another.

| Type of cohesion       | Description                                                                                                                                                                                                                                                                                                                                          |
| ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Functional cohesion    | Measure a design unit's strength by the degree to which its tasks, operations or subunits all contribute to perform a single function.<br><br>The function to be performed has a single logical meaning, functional cohesion can be seen as a form of logical cohesion.<br>                                                                          |
| Procedural cohesion    | Measures the strength of a design unit by the degree to which its tasks work procedurally to achieve the unit's purpose.<br><br>Functional and procedural cohesion are not mutually exclusive, modules can exhibit both high functional and procedural cohesion.                                                                                     |
| Temporal cohesion      | Measures strength by the degree to which all tasks in a design unit are performed at specific times.<br><br>Consider a design unit responsible for carrying out the initialization of a system. This unit may be responsible for performing a power-on self-test that may include memory tests, file system checks and communication checks.<br><br> |
| Communication cohesion | Measures a unit's strength by the degree to which its tasks                                                                                                                                                                                                                                                                                          |
>[!example] 
>![[Pasted image 20250914210926.png]]
>- As seen in the top part of the figure, Module 1 performs 3 unrelated different tasks^[Task 1, Task2, Task 3], each requiring 3 independent subtasks.
>- Task 1 requires 3 different subtask, denoted by the labels Task 1.1, Task 1.2 and Task 1.3. As seen, Module 1 has dependencies to 9 different unrelated tasks, which can translate to a high degree of coupling and low degree of cohesive.
> ![[Pasted image 20250914210940.png]]
>- Shows how the system is decomposed into 3 more cohesive units, each with lower coupling than the original approach. The system is transformed to a modular system with higher cohesiveness and low coupling.
>- Modules 2 and 3 have lower coupling than Module 1^[both in its original and improve form] and are highly cohesive.
## Practical SD Considerations

## SD strategies


