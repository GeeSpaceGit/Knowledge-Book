---
Done: true
---
# Introduction
- The design phase incorporates many activities and tasks conducted by different teams and typically managed by personnel other than designers. This requires a formal process to ensure that the design phase is conducted properly and that it addresses all the concerns identified for the software system being built.
-  In today's professional software engineering landscape, software engineers are being asked to build larger and more complex software systems in the same or different sites. Therefore, both design processes and artifacts are increasing in complexity. This means that it is not enough to know how to model structural and behavioural aspects of the system in the design, but it is also essential that software designers know about the particular process required to manage, create and control SD activities.

Many processes exist to carry out phases, activities and tasks throughout the software engineering life cycle:
- Unified process (UP)
- Scrum
- Dynamic system development method (DSDM)


>[!note] Software Process defined by Sommerville
>A set of activities that lead to the production of a software product. Similarly, a SD process is a set of activities and controls that specify how resources work together for the production of SD artifacts

# SD Process
The software engineering body of knowledge identifies 2 major activities for SD:
- Software architecture
- Detailed design

These are the essential activities for managing the complexity involved in developing large-scale software system. However, numerous other important activities required for supporting the creation of architectural and detailed designs. 

- Emphasis that some forms of design place on construction, the detailed design activity process can be modified to explicitly present the construction design that addresses design issues encountered during the construction phase.
- The architectural design activities can begin during the analysis activity of the requirements phase and span through the design phase; in others, it begins after the requirements are specified and validated. In a similar fashion, the detailed design activity can start at the project's design phase and span through the software construction phase.
![[Pasted image 20250914213401.png]]

## Software Architecture
- Corresponds to a macro design approach for creating models that depict the quality and function of the software system. It provides black-box models used to evaluate the system's projected capabilities as well as its expected quality, all from multiple perspectives. Therefore, architectural designs allow different stakeholders, with different backgrounds and expertise to evaluate the design and ensure that the software architecture is addressing their concerns.
- From the configuration management perspective, architectural designs can provide information about the the hierarchy of files in the file system and how these files are interconnected to build and deploy the software system.
- From the software engineering perspective, different architectural designs can help decompose the software and define the major structural components of the system, identify interfaces between the components, map the requirement to them, evaluate concurrency issues and provide overall insight into design solution.

>[!example]
>Systems engineering perspective, architectural designs can provide information about the physical deployment of the system, including subsystems located at different locations, the artifacts executing in the subsystems and how the system as a whole communicates.

### Benefit of architecture design
- Capacity to evaluate high-level concerns from stakeholders that deal mostly with non-functional requirement.
- Serve as important communication reasoning and analysis tools that support the  systems.
- Lays the foundation for all subsequent work in the software engineering life cycle.

## Detailed Design
- Build on the software architecture to provide white-box design elements of the structure and behaviour of the software system and in many cases is the last major effort before software construction begins.
- Activity that deals with refining the software architecture to reach a point where the SD, including architecture and detailed design, is deemed sufficiently complete for construction to begin.
- The software architecture places a major emphasis on quality^[nonfunctional requirements], the detailed design activity places a major focus on addressing functional requirements of the system.
>[!note] Object-oriented systems
>The detailed design activity is where components are refined into:
>- One or more classes.
>- Interfaces are realized.
>- Relationships between classes are specified.
>- Class functions.
>- Variable names are created.
>- Design patterns are identified and applied.
>- Design tools are configured for code generation.
### Interface Design
- Can be focused on specifying the interfaces used internally within software components or externally across software components.
- Interfaces provide a standardized way for specifying how services are accessed and provided by software component.
- Allows subsystems to be designed independently and parallel; therefore, it is typically one of the first tasks performed as part of detail design.

>[!example]  Design specify communication between systems
> Custom binary or Extensible Markup Language (XML) messaging specifications used for communication between 2 or more subsystems through the network.

### Component Design
- The software system is decomposed into logical components that abstract required system functions. These logical components are refined and their interactions are refined and their interactions are modelled to verify the validity of their structural composition.
- Execution of detailed design activity requires a shift from the macro design approach to further decompose and refine system components into one or more fine-grained elements, functions and data variables required for supporting the internal structure and behaviour of components that meet assigned roles during the software architecture activity.
- Component design refers to modelling the internal structure and behaviour of components, which includes the internal structure of both logical and physical component identified during the software architecture phase.
## Construction Design
- In object-oriented systems, this amounts to identifying classes, their attributes and functions and interrelationships with other classes. These tasks are done while abstracting and deferring details of implementation to the construction phase.
- Implementing complex software functions identified during the detailed design activity requires additional design work to ensure they work properly and maintain the quality standards sought during the software architecture activities.
- Construction design is the last design activity, typically conducted during the construction phase, required to support the system's quality attributes ^[performance, maintainability and testability].
>[!example] Authors have proposed it as an important design activity.
>- McConnell specifies 5 levels of SD. One of them, being at the lowest level, deals with internal routine design.
>- Fox identifies a form of low-level, design that fills the gap between detailed design and programming and deals with issues such as operation specification, including operation name, parameter types and return types among others.
>- Meyers have highlighted the importance of designing code at low levels, during construction.
## HCI Design
- Where general principles are applied to optimize the interface between human and computers.
- Visual designs have a major role on the success or failure of software systems. Systems that meet functional requirements but that are not usable cannot succeed. HCI design activity can be executed in parallel to the software architecture or detailed design activities. Can considered an architectural task, while in others it is considered a detailed design task.

>[!example] Major concerns of the HCI design
>- Evaluation and use of modes
>- Navigation
>- Visual designs
>- Response time and feedback
>- Design modalities
### SD Documentation (SDD)
- Play a pivotal role in professional, large-scale or software intensive systems.
- Should include the necessary information that properly captures the design of the system. 
- As tools for generating design documents, validation and configuration management must be addressed.
>[!note] SDD Defined by IEEE
>- Play a pivotal role in the development and maintenance of software systems. During its lifetime, a given design description is used by project managers, quality assurance staff, configuration manager, software designers, programmers, tester and maintainers.
>- Each of these users has unique needs, both in terms of required design information and optimal organization of that information. 
>- A design description must contain all the design information needed by those users.
### SD Management 
>[!note] SD Management defined by Griffin
>A set of activities directed at an organization's resources and information with the aim of achieving organizational goals in an efficient and effective manner.

- Management refer to the set of activities required to efficiently create and implement quality design artifacts within schedule and budget constrains.
- The core of every organization's management activities, quality is a focal point. The quality of SD can be assessed in various ways.

>[!note] From difference perspective
>- Management
>  Quality of SD can be evaluated in terms of cost and scheduling.
>- Engineering
>  Quality in design can be evaluated using a set of well-known design principles as well-known design principles  as well as modelling and evaluating the quality attributes that the software must exhibit, which are specified via nonfunctionally, quality requirements.
>- Configuration management
>  Design quality can be achieved through change management processes that control how designs are created, modified and improved.