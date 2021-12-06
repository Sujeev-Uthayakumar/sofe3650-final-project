# SOFE 3650 Final Project Iteration 2: Identifying Structures to Support Primary Functionality
The focus of this section is to present the results of the activities that are performed from each step of the ADD process in the second iteration. This iteration will dive deeper into more detailed decisions that will promote better implementation which will aid the development team. As we can not predict everything, we need to be more disciplined on which decisions we make and attack them from the most significant to least significant.

## Table of Contents:
- [Iteration 2 PDF](https://github.com/Sujeev-Uthayakumar/sofe3650-final-project/blob/master/Iteration%202/Project%20Deliverable%203%20Iteration%202.pdf)
- [Step 2: Establish Iteration Goal by Selecting Drivers](#Step-2-Establish-Iteration-Goal-by-Selecting-Drivers)
- [Step 3: Choose One or More Elements of the System to Refine](#Step-3-Choose-One-or-More-Elements-of-the-System-to-Refine)
- [Step 4: Choose One or More Design  Concepts That Satisfy the Selected Drivers](#Step-4-Choose-One-or-More-Design-Concepts-that-Satisfy-the-Selected-Drivers)
- [Step 5: Instantiate Architectural Elements, Allocate Responsibilities, and Define Interfaces](#Step-5-Instantiate-Architectural-Elements-Allocate-Responsibilities-and-Define-Interfaces)
- [Step 6: Sketch Views and Record Design Decisions](#Step-6-Sketch-Views-and-Record-Design-Decisions)
- [Step 7: Perform Analysis of Current Design and Review Iteration Goal and Achievement of Design Process](#Step-7-Perform-Analysis-of-Current-Design-and-Review-Iteration-Goal-and-Achievement-of-Design-Purpose)
- [Contributors](#Contributors)

## Step 2: Establish Iteration Goal by Selecting Drivers:
The goal of this iteration is to address the general architectural concern of identifying structures to support primary functionality. Identifying these elements is important for understanding how functionality is supported and addressing CRN-3. 

Besides CRN-3, the architect considers the system’s primary use cases:
- UC-1: Store users
- UC-2: Send messages
- UC-6: Display users
- UC-9: Sending joining and leaving messages

## Step 3: Choose One or More Elements of the System to Refine:
The elements that will be refined in this iteration are the modules located in the different layers defined by the three-tier reference architectures from the previous iteration. In general, the support of functionality in this system requires the collaboration of components associated with modules that are located in the different layers. 

## Step 4: Choose One or More Design Concepts that Satisfy the Selected Drivers:
The following table summarizes the design decisions:
<table>
  <tr>
    <th>Design Decisions and Location</th>
    <th>Rationale</th>
  </tr>
  <tr>
    <td>Create a Domain Model for the application</td>
    <td>Before starting a functional decomposition, it is necessary to create an initial domain model for the system, identifying major entities in the domain, along with their relationships.</td>
  </tr>
   <tr>
     <td>Identify Domain Objects that map to the functional requirements</td>
     <td>Each distinct functional element of the application needs to be encapsulated in a self-contained building block - a domain object.</td>
  </tr>
   <tr>
     <td>Decompose Domain Objects into general and specialized Components</td>
     <td>Domain objects represent complete sets of functionality, but this functionality is supported by finer-grained elements located within the layers. The “components” in this pattern are what we have referred to as modules.</td>
  </tr>
   <tr>
     <td>Using JSON programming language, handlebars, and sockets</td>
     <td>By using JSON which is a lightweight data-interchange format where data is able to be transferred and used through a web application. 
Alongside that JSON supports many frameworks and libraries which support scalability. 
By using handlebars which are functions that support GUI it makes it easier to display information from the server. Sockets.io is a library that is a real-time web application that allows for bidirectional communication between clients and servers.</td>
  </tr>

</table>

## Step 5: Instantiate Architectural Elements, Allocate Responsibilities, and Define Interfaces: 
The instantiation design decisions made in this iteration are summarized in the following table:
<table>
  <tr>
    <th>Design Decisions and Location</th>
    <th>Rationale</th>
  </tr>
  <tr>
    <td>Create only an initial domain model </td>
    <td>The entities that participate in the primary use cases need to be identified and modeled but only an initial domain model is created, to accelerate this phase of design. </td>
  </tr>
  <tr>
    <td>Map the system use cases to domain objects</td>
    <td>Initial identification of domain objects can be made by analyzing the system's use cases. To address CRN-3, domain objects are identified for all of the use cases.</td>
  </tr>
  <tr>
    <td>Decompose the domain objects across the layers to identify layer-specific modules with an 
explicit interface 
</td>
    <td>This technique ensures that modules that support all of the functionalities are identified.
The architect will perform this task just for the primary use cases. The rest of the team members will work on other modules, thus dividing up the work.
A new concern will be created in which is identified below:
CRN-4: Some of the modules shall be tested to determine their functionality.
</td
  </tr>
</table>

## Step 6: Sketch Views and Record Design Decisions:
As a result of the decisions made in step 5, the design decisions can be portrayed into several diagrams.

<p align="center">
  <img src="https://i.ibb.co/ThWfWzc/Domain-Model.jpg">
  <p align="center"><b>Figure 3.1 - The figure showcases an initial domain model for the system that showcases the primary use cases</b></p>
</p>

<p align="center">
  <img src="https://i.ibb.co/88VNSJZ/Untitled-Diagram.jpg">
  <p align="center"><b>Figure 3.2 - The figure shows the domain objects that are instantiated for the use case model</b></p>

<p align="center">
  <img src="https://i.ibb.co/v40FFvN/iteration-2-architecture.jpg">
  <p align="center"><b>Figure 3.3 - The figure shows the reference architecture for three-tier architecture, where modules that support the primary use cases</b>
</p>
<table>
  <tr>
    <th>Element</th>
    <th>Responsibility</th>
  </tr>
  <tr>
    <td>User authentication Systems</td>
    <td>Responsible for ensuring the user was created and registered within the database correctly.</td>
  </tr>
   <tr>
    <td>Room Retrieval Module</td>
    <td>Responsible for getting the room Id based on the user input </td>
  </tr>
    <tr>
    <td>Socket Message Listener</td>
    <td>Responsible for listening to the message front he emitted a message module.</td>
  </tr>
    <tr>
    <td>Profanity Checker</td>
    <td>Responsible for checking user input to the chat to see if there is a profane message.</td>
  </tr>
    <tr>
    <td>Socket Message Emit</td>
    <td>Responsible for sending/emitting for which the listener will take in.</td>
  </tr>
   <tr>
    <td>Continuous User Validation</td>
    <td>Responsible for checking if a user is still registered within the database.</td>
  </tr>
   <tr>
    <td>Socket.io Server</td>
    <td>Responsible for encapsulating the emitter and listener.</td>
  </tr>
</table>
<p align="center">
  <img src="https://i.ibb.co/c6nKD1c/usecase-2.jpg">
<p align="center"><b>Figure 3.4 - Sequence diagram for UC-2</b></p>
</p>
<table>
  <tr>
    <th>Element</th>
    <th>Responsibility</th>
  </tr>
  <tr>
    <td>Client Interface</td>
    <td>Display GUI for user to input/view text, view users, and send location.</td>
  </tr>
  <tr>
    <td>Profanity Checker</td>
    <td>Checks if messages do not have offensive language before displaying it to the users.</td>
  </tr>
  <tr>
    <td>Server</td>
    <td>Sends the messages to the rooms and cancels messages which are offensive.</td>
  </tr>
  <tr>
    <td>Room</td>
    <td>Displays messages, users, and the time messages are sent.</td>
  </tr>
</table>
 
## Step 7: Perform Analysis of Current Design and Review Iteration Goal and Achievement of Design Purpose:
The decisions made in this iteration provided an initial understanding of how the system shall function. The modules associated with the primary use cases were identified by the architect, and the modules associated with the rest of the functionality were identified by the rest of the team.
<table>
  <tr>
    <th>Not Addressed</th>
    <th>Partially Addressed</th>
    <th>Completely Addressed</th>
    <th>Design Decisions Made During this Iteration</th>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td>UC-1</td>
    <td>Modules across the layers and preliminary interfaces to support this use case have been identified.</td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td>UC-2</td>
    <td>Modules across the layers and preliminary interfaces to support this use case have been identified.</td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td>UC-6</td>
    <td>Modules across the layers and preliminary interfaces to support this use case have been identified.</td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td>UC-9</td>
    <td>Modules across the layers and preliminary interfaces to support this use case have been identified.</td>
  </tr>
  <tr>
    <td></td>
    <td>QA-1</td>
    <td></td>
    <td>The elements that support the associated use case (UC-1) have been identified.</td>
  </tr>
  <tr>
    <td></td>
    <td>QA-3</td>
    <td></td>
    <td>No relevant decisions were made.</td>
  </tr>
  <tr>
    <td></td>
    <td>QA-4</td>
    <td></td>
    <td>The elements that support the associated use cases (All) have been identified.</td>
  </tr>
  <tr>
    <td></td>
    <td>QA-5</td>
    <td></td>
    <td>The elements that support the associated use case (UC-6) have been identified.</td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td>CON-3</td>
    <td>Modules responsible for authenticating have been identified.</td>
  </tr>
   <tr>
    <td></td>
    <td>CON-4</td>
    <td></td>
    <td>No relevant decision was made.</td>
  </tr>
   <tr>
    <td></td>
    <td>CON-5</td>
    <td></td>
    <td>No relevant decision was made.</td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td>CRN-2</td>
    <td>Modules incorporating handlebars have been identified.</td>
  </tr>
   <tr>
    <td></td>
    <td></td>
    <td>CRN-3</td>
    <td>Modules associated with all of the use cases have been identified and a work assignment matrix has been created</td>
  </tr>
   <tr>
    <td></td>
    <td>CRN-4</td>
    <td></td>
    <td>The architectural concern of unit-testing modules, which was introduced in this new interaction.</td>
  </tr>
</table>

## Contributors:
* Sujeev Uthayakumar - 100744194
* Zirak Mughal - 100749132
* Yash Patel - 100746810
* Kalapan Kannathasan - 100759041
