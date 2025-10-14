- Carried out to identify how architectural components are designed with enough detail so that their implementation using programming languages can follow without much effort. .
- Many process flows can be identified and used to carry out and manage DD activity, including iterative, sequential and spiral.

# Understanding the Architecture and Requirement
- Where the complete set of system requirements are evaluated and well understood, designers during the DD activity focus on requirements allocated to their specific components.
- Requirements can cross cut several component. Therefore communication with other designers is essential to coordinating the design solution without duplicating work.
- To derive new software requirements as knowledge of the system is enhanced throughout the DD activity. Derived requirements based on higher-level requirements identified in previous phases and activities of the project. Consider an embedded real-time software system broken down into 5 different major subsystem components, each executed on different target hardware and broken down further into numerous other component.
## During Requirement
- The functional capability to log events in the system is specified. To carry out this function of the system, a DD activity is done to create a common event logger so that all component in the systems rely on a standardized way for logging events in the system, simply having one functional requirement to log events provides insufficient specification for the desire behaviour. Consider the case where the event logger is designed to log all events in the system to a file without limits or policies to manage how events are stores, purged.
- Resource constrained environment, enforcing and verifying policies for such behaviour is essential, since a large number of events, depending on the target resources, can slow or bring the system down.^[Maximum number of events logged, event purge policy such as FIFO, LIFO ] provides essential items of verification for the system. 
- When conducting the DD activity, assigned requirement for the components have to be well understood and when appropriate, derived requirements need to be specified before construction begins.

## To maintain Synchronicity throughout the development effort.
- All decisions made during DD must conform to the system's identified architecture.
- Software processes must be in place for monitoring and controlling DD throughout.
- Unmanaged deviations from the software architecture during DD and construction can reshape the properties of the system and affect its overall system plan.
# Creating DD and Evaluating DD
- Consists of structural and behavioural designs required to specify components sufficiently so that they can be consistently constructed by 1 or more programmers.
Including:
- Refining or creating components interface design internal structure and behavioural design
- Identifying design patters
- Applying design principles
- Adopting naming conventions
- Evaluating and documenting DD
## Interface Design
- Can be focused on specifying the interfaces used internally within software components or externally across software components.
- Provide a standardized way for specifying how services can accessed and provided by software components.
- Allows subsystems to be designed independently and in parallel. It is typically done first within the detailed design step.
### External Interface Design
### Internal Interface Design

# Documenting DD
# Documenting DD
# Monitoring and controlling implementation