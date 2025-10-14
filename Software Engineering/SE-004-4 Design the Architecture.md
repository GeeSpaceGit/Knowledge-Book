---
done:
---

- In a typical waterfall model for software development, once the software specification is validate, the architectural design effort can begin.
- Following a strict waterfall model is rarely productive, since new knowledge acquired during the development process forces iterative approaches between requirements and architecture design.
- Be it during requirements or design, designing architectures require the selection of particular perspectives for design that appropriate for describing the system to be developed.
# The 4 +1 View Model
![[Pasted image 20250915151146.png]]
- Philippe Krunchten published an influential paper that proposed modelling software architectures using different perspectives; each perspectives provides avenues for addressing problems from different angles and when combined, the set of models created from each perspective helps form the software architecture.
- Concentrated on 4 main views: logical, process, development and physical. Modelling systems from each view requires addressing design problems of different natures, such as problems that deal with the logical system structure or problems that deal with dynamic, concurrency system issues.
- Provides an adequate framework for modelling the architecture of most software systems. However, adoption of the model varies form organization to organization and from project to project.

>[!example] 
>When concurrency is not an issue, modeling the system from a process view makes little to no sense.

## User View
- Represent the behaviour that the system exhibits to its users. Specifically, the user view depicts how users interact with the system and how the specific sequences of inputs and outputs occur during software operation.
- UML use case models can be used to drive scenarios that provide storyline and to promote consistency among all other models. Scenario created can help capture important system functions and discover new knowledge that drives architectural design decision. Provides an effective source of information for verifying and validating system function, after the system is built.
User represent anyone who interacts with the software system, such as:
- Operator
- Software tester
- Analysts
- Quality
## Process View
- Represent the dynamic or behavioural aspects of the software system where the main units of analysis are processes and threads.
- Software systems are decomposed into processes and threads to address design issues that with the dynamic flow of control between architectural elements, such as concurrency, distribution, system's integrity, fault tolerance and other nonfunctionally requirements. Need to meet performance and availability requirements by modelling aspects of concurrency, distribution and fault tolerance.
- Behavioural UML diagrams can be used efficiently to address issues pertinent to the process views. UML sequence and communication diagrams, together with the active object notation, can be used to evaluate, analyze and characterize the system's capabilities from the process perspective.

## Physical View
![[Pasted image 20250915155828.png]]
- The deployment aspects of software system where the main elements of analysis are nodes, connections between nodes and maps of software artifacts to nodes.
- Focuses on modelling of elements that directly affect quality requirements, such as availability, performance and scalability.
>[!example] System quality is measured in part by the availability of the system.
>- Systems are perceived as low quality when they fail to provide a specified behaviour. In this case, availability can be addressed via redundancy of processors or complete nodes, which both can be depicted using UML deployment diagram.
>- Identification of redundant nodes using the physical view requires downstream design and development to think about techniques for identifying faults and swapping between primary and redundant nodes when necessary to support the system's availability.
>- Performance is measured with throughput, the physical view of systems must identify the elements that directly impact this metric, such as required bandwidth between a client and server.

- Modelling system deployment may require one or more UML deployment diagrams. Different deployment diagrams may be necessary to model different deployment configurations of the same software system.
>[!example] Deployments of software systems in testing environments or in different locations where deployment configuration s may differ.
>In each case, the physical view provides insight into necessary elements that directly affect the perceived quality of the software system.

## Development View
- Represent the software development configuration aspects of the software system, where the main units of decomposition are actual physical files and directories.
- Used to analyze the system from the perspective of how logical components map to physical files and directories. These analyses can be employed to address concerns that deal with ease of development, reusability, constrains imposed by tool sets, allocation of work to teams, cost evaluation and planning, monitoring the project's progress, portability and security.
- Architectural elements resulting from analyzing systems can be documented using package diagrams in combination with components and class diagram with components and class diagrams as well as notes, tagged values and constraints to enhance the meaning of the diagrams.

## Logical View
![[Pasted image 20250915155555.png]]
- Used to decompose systems into logical component that represent the structural integrity that supports functional and nonfunctionally requirement. Provide the building blocks for detailed design; therefore, they are indispensable in the architectural design of software systems.
- The static structure of the system can be modelled using high-level diagrams to decompose, abstract and encapsulate the services that the system needs to provide to its users. By using these diagrams, the major components, their interfaces and associations with all other components are identified.
- Exist at a higher level of abstraction than detailed designs and can be modelled using box and line diagrams, UML component diagrams, package diagrams or class diagrams.
# Components and Connectors
# Designing Logical Architectural Element using Data Flows

# Designing Logical Architectural Elements Using Styles and Patterns
## Processes
## Threads