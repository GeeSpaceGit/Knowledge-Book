---
done: true
---

# What is DD
- The design process continues where software architecture leaves off for providing a white-box approach to design, where details left undefined and deferred to downstream designers are created to define the necessary details for fully specifying the internal structure and behaviour of components identified during architecture.
- Fill the gaps int he design and provide a complete picture of how the system achieves its functional requirements within the quality framework established by the software architecture. Can significantly shape the system's quality include portability, performance and usability. Therefore, they must exist within the bounds of the software architecture. Where modelling tools are used to generate code, detailed designs can also significantly impact the quality properties of the construction phase.
- Upon completion of the detailed design activity, the system's design is sufficiently complete so that it can be formally documented, reviewed and approved by the system's stakeholders, which marks the end of the design phase.

# Why we need DD
- The execution of DD activity requires a shift from the micro design approach to the micro design approach to further decompose and refine system components into one or more fine-grained elements, function and data variables required for supporting the internal structure and behaviour of component that meet assigned roles during the software architecture activity.
- Successful designers are required to have full understanding of the system's requirements and architecture, design strategy, programming language and methods and processes for software quality control.
- DD provide the essential structure that acts as bridge connecting the work performed during architecture and construction. DD need to incorporate design alternatives that support the requirements and quality attributes^[testabikity, maintainability, modifiability] identified in previous phases and activities of the software engineering life cycle.

>[!note] Detailed Design defined by IEEE
>- The process of refining and expanding the preliminary design phase of a system or component to the extent that the design is sufficiently complete to be implemented.

## Difference with Architectural Design
- Whereas the former is concerned mostly with defining the major components of the system and their interfaces, the latter is concerned with how these components realize their assigned responsibility.
- Architectural designs employ a holistic approach to software SD, which emphasizes system quality, while DD focuses on particular components within the system, which emphasizes the functional aspects of a system.
- Essential in determining what and how work is performed during these activities.
>[!example]
>Whereas the component notation provides an appropriate mechanism for designing logical architectures, their level of abstraction is inappropriate for modelling DD elements.

>[!note] Clements, Bachmann, Bass, Garlan, Ivers, Little, Nord and Stafford differentiate between architectural and DD
>Architecture is design, nut not all design is architecture. That is, many design decisions are left unbound by the architecture and are happily left to the discretion and good judgement of downstream designers and implements. The architecture establishes constraints on downstream activities and those activities must produce artifacts, finer design and code that are compliant with the architecture, but architecture does not define an implementation.
## Modelling and analyses
- Occur during architecture help answer the questions of what needs to be developed and themselves these models and analyses cannot be used to build directly a working software system.
- DD goes deep into each component to define its internal structure and behavioural capabilities and the resulting design leads to natural and efficient construction of software.