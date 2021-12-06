# SOFE 3650 Final Project Iteration 2: Identifying Structures to Support Primary Functionality
In this iteration, the architecture elements are revised and structures are identified to support the primary functionality.<br/>

The focus of this section is to present the results of the activities that are performed from each step of the ADD process in the second iteration. This iteration will dive deeper into more detailed decisions that will promote better implementation which will aid the development team. As we can not predict everything, we need to be more disciplined on which decisions we make and attack them from the most significant to least significant.

## Table of Contents:
- [Iteration 2 PDF](https://github.com/Sujeev-Uthayakumar/sofe3650-final-project/blob/master/Project%20Deliverable%203%20Iteration%202.pdf)
- [Step 2: Establish Iteration Goal by Selecting Drivers](#Step-2-Establish-Iteration-Goal-by-Selecting-Drivers)
- [Step 3: Choose One or More Elements of the System to Refine](#Step-3-Choose-One-or-More-Elements-of-the-System-to-Refine)
- [Step 4: Choose One or More Design  Concepts That Satisfy the Selected Drivers](#Step-4-Choose-One-or-More-Design-Concepts-that-Satisfy-the-Selected-Drivers)
- [Step 5: Instantiate Architectural Elements, Allocate Responsibilities, and Define Interfaces](#Step-5-Instantiate-Architectural-Elements-Allocate-Responsibilities-and-Define-Interfaces)
- [Step 6: Sketch Views and Record Design Decisions](#Step-6-Sketch-Views-and-Record-Design-Decisions)
- [Step 7: Perform Analysis of Current Design and Review Iteration Goal and Achievement of Design Process](#Step-7-Perform-Analysis-of-Current-Design-and-Review-Iteration-Goal-and-Achievement-of-Design-Purpose)
- [Contributors](#Contributors)

## Step 2: Establish Iteration Goal by Selecting Drivers
The goal of this iteration is to address the general architectural concern of identifying structures to support primary functionality. Identifying these elements is important for understanding how functionality is supported and addressing CRN-3. 

Besides CRN-3, the architect considers the system’s primary use cases:
- UC-1: Store users
- UC-2: Send messages
- UC-6: Display users
- UC-9: Sending joining and leaving messages

## Step 3: Choose One or More Elements of the System to Refine
The elements that will be refined in this iteration are the modules located in the different layers defined by the three-tier reference architectures from the previous iteration. In general, the support of functionality in this system requires the collaboration of components associated with modules that are located in the different layers. 

## Step 4: Choose One or More Design Concepts that Satisfy the Selected Drivers
The following table summarizes the design decisions.
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

## Step 5: Instantiate Architectural Elements, Allocate Responsibilities, and Define Interfaces 
The instantiation design decisions made in this iteration are summarized in the following table:

## Step 6: Sketch Views and Record Design Decisions
As a result of the decisions made in step 5, the design decisions can be portrayed into several diagrams.
- The figure showcases an initial domain model for the system
- The figure shows the domain objects that are instantiated for the use case model in Section 

## Step 7: Perform Analysis of Current Design and Review Iteration Goal and Achievement of Design Purpose
The decisions made in this iteration provided an initial understanding of how the system shall function. The modules associated with the primary use cases were identified by the architect, and the modules associated with the rest of the functionality were identified by the rest of the team.

## Contributors:
* Sujeev Uthayakumar - 100744194
* Zirak Mughal - 100749132
* Yash Patel - 100746810
* Kalapan Kannathasan - 100759041
