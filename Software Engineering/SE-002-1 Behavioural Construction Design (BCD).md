- The purpose of behavioural design is to model the dynamic aspects of code that makes up a particular function.
- Provide the means for assessing for completeness, correctness and quality of functions before actual implementation occurs and therefore are an essential activity for complex operations.
# Approach for BCD
## Flow-based Design
- Provide a systematic methodology for specifying the logic of operations using a graphical approach.
- 2 popular approaches for creating flow-based designs include flowcharts and Unified Modelling Language (UML) activity diagrams. Both work well for modelling the internal flows, loops, conditional statements and other useful mechanisms needed to model complex business logic or complicated algorithms.
UML activity diagrams provide powerful constructs for modelling complex logic at different stages of the software engineering life cycle, however, when applied toward modelling logic, activity diagrams provide similar features to flowcharts.
- If statements
- Case statement
- Do while loop
- While loops

## State-Based Designs
![[Pasted image 20250915215604.png]]
- Can used to model operational logic by identifying the transitions from activity to activity required to perform an operation. Some cases the operational logic of a function or system is dictated by the different states that the system exhibits during its lifetime. When this occurs, the operational  logic of a system can be modelled as a state machine using a state diagram.
- State diagrams are typically used to model the behaviour of complete system. State diagram can be used to guide the logical design of one or more operations in the system.
- Depicts the design of a software system that receives messages and performs operations based on the messages received and the system's state.

![[Pasted image 20250915215623.png]]
1. During the power-on initialization state, the system only reacts to the GetStatus, SelfTest and SoftwareUpdate message.
	- Once the SelfTest message is received, the system transitions to the self-test state, where system capabilities are evaluated to determine the integrity of the system.
	- Once the self-test state is complete, 2 transitions can occur; if the tests were successful then the system enters a fault state, in which no-commands can be executed.
	- Once the fault state is complete, the system transitions to a power-down state, which allows the system to save all pertinent information to the file system before transitioning to the initialization (Power On) state.

2. Upon successfully execution of the self-test state, the system transitions to the operational state, where all messages in the system can be processed, including the SelfTest message and ShutDown message.
	- The state diagram presents the state of the system, together with the transitions and the events that trigger each transition.
	- Unlike the flow-based design approach in the previous section, the system's state-based designs show the flow of operations from state to state; it acts like a well-structured algorithm that is efficient, simple, adaptable and understandable.

3. The system is et to the Power-onState; therefore, upon executing the code the executePowerOnState() method is called to process the received message and determines if a state is required.
![[Pasted image 20250915231246.png]]
4. The source of the code presented can be traced back to the state design.
	- EmbeddedComponent is in power-on-state, it can execute the messages only for updating the software, retrieving the component's status and executing a self-test.
	- Messages containing different IDs cannot be executed in this state. Therefore, upon receiving any other message the system logs an event and waits for the next message to be received.
	- Similar fashion, the code for all other states is implemented according to the state design.

![[Pasted image 20250915231727.png]]
![[Pasted image 20250915231737.png]]
5. Once the EmbeddedComponent enters the self-test state, it executes the appropriate tests and based on test results it sets the new system state to the operational or fault state, as defined in the state design.
	- Assuming all tests are performed successfully, the EmbeddedComponent transitions to the operational state, where all messages can be received and processed by the EmbeddedComponent.
## Table-Based Designs
- The internal logic of routines is made up of complex conditional statements, each statement evaluating a condition and providing some action as a result. This can lead to an increasingly complex nesting structure that is error-prone, hard to read and hard to maintain.
- A decision table is a well-structured table that provides the means to formulate, evaluate and improve the design of complex problem that deal with cause and effect.
![[Pasted image 20250915232715.png]]

| Section                            | Description                                                                                                                                                      |
| ---------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Condition section                  | Contains a list of all of the conditions present in the decision problem.<br>                                                                                    |
| Action section                     | Which contains a list of all possible outcomes that can result from one or more condition occurring.<br>                                                         |
| Condition and Action (matrix form) | Indicates all possible combinations of conditions for the decision problem, while the matrix adjacent to the Action section indicates the corresponding actions. |

![[Pasted image 20250915232724.png]]
Respective columns in both matrices provide a policy for decision making in the  decision problem.

### Limited-entry decision table (LEDT)
### Extended-entry decision table (EEDT)

### Mixed-entry decision table (MEDT)

### Hybrid-entry decision table (HEDT)
## Programming Design Language (PDL)
- A form of pseudocode used widely for designing internal function behavior. Its popularity stems from the use of natural languages as opposed to computer languages or graphical techniques to define the required behavior of functions. This results in detailed function designs that are easier to create, review and translate to code.
- The usage of a natural language in PDL provide a "comments-first approach" to constructing code for any programming language. Therefore, PDL should be written without concern given to the target programming language and detailed enough that code can be generated with minimal effort.
- Can be effectively employed using a top-down approach that first describes the general work performed by the function and then more specific operations within the function. The description of the general work performed by the function should include
- the function's intent, input and outputs.
>[!example] PDL Form
>![[Pasted image 20250915234557.png]]
>- Provide complete design details for the function. When finished, the function's detailed PDF should result in the identification of operations that support the general description of the functions. Therefore, PDL can be  used as both design technique and effective documentation approach for functions and code within functions.

### Benefit of using PDL
- PDL provides a programming languages independent technique for creating detailed function designs; therefore, collaborative efforts with all disciplines involved in the project can be achieved to provide complete reviews for the design of a functions. Member from the systems, hardware, quality and test groups can all chime in to help the function design meet the required capabilities.