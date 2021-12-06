# SOFE 3650 Final Project Iteration 1
In this iteration, the reference architecture was revised and the overall system structure was established.

## Table of Contents:
- [Iteration 1 PDF](https://github.com/Sujeev-Uthayakumar/sofe3650-final-project/blob/master/Project%20Deliverable%203%20Iteration%201.pdf)
- [Iteration 1: Establishing an Overall System Structure](#iteration-1-establishing-an-overall-system-structure)
- [Step 2: Establish Iteration Goal by Selecting Drivers](#step-2-establish-iteration-goal-by-selecting-drivers)
- [Step 3: Choose One or More Element to Refine](#step-3-choose-one-or-more-element-to-refine)
- [Step 4: Choose One or More Design Concepts That Satisfy The Selected Drivers](#step-4-choose-one-or-more-design-concepts-that-satisfy-the-selected-drivers)
- [Step 5: Instantiate Architecture Elements, Allocate Responsibilities, and Define Interfaces](#step-5-instantiate-architecture-elements-allocate-responsibilities-and-define-interfaces)
- [Step 6: Sketch Views and Record Design Decisions](#step-6-sketch-views-and-record-design-decisions)
- [Step 7: Perform Analysis of Current Design and Review Iteration](#step-7-perform-analysis-of-current-design-and-review-iteration)
- [Contributors](#contributors)

## Iteration 1: Establishing an Overall System Structure
The focus of this section is to present the results of the activities that are performed in each of the steps in iteration 1 of the ADD design process. Step 2 till the end of step 7 will be focusing on iteration 1, where we will refine our requirements and quality attributes.

## Step 2: Establish Iteration Goal by Selecting Drivers
This is the first iteration of the design of a USChat system, so the iteration goal is to establish the initial design of the system, where we will establish the overall system structure. This iteration will be driven by general architectural concerns, and there will be a focus on all the drivers that may further influence the general structure of the system. In particular, we will focus on items within:  
- QA-1: Scalability
- QA-3: Security
- QA-4: Performance
- QA-5: Availability
- CON-3: Users should be authenticated before joining the room
- CON-4: Network connection between user and server must have low bandwidth and be reliable
- CON-5: The system must be accessed through a web browser such as Chrome, Firefox Safari, etc.
<p align="center">
  <img src="https://i.ibb.co/txs2sfQ/context-diagram.jpg">
</p>

## Step 3: Choose One or More Element to Refine
In this case, the element to refine is the entire USChat system. This refinement is performed through decomposition. 

## Step 4: Choose One or More Design Concepts That Satisfy the Selected Drivers
In this current iteration, the goal of structuring the entire system, design concepts are selected from the criteria presented in Section 1.1. The table below will summarize the selection of design decisions.
<table style="width: 50%">
  <tr>
    <th>Design Decision and Location</th>
    <th>Rationale</th>
  </tr>
  <tr>
    <td>Logically structure the client part of the system using the Web Application reference architecture.</td>
    <td>The Web Application reference architecture supports the development of a web browser that communicates with the Heroku Development Server. This application supports web applications as the majority of it resides on the server, and its architecture is typically composed of three layers.
      <table>
        <tr>
          <th>Alternatives</th>
          <th>Reason for Discarding</th>
        </tr>
        <tr>
          <td>Rich Client Applications</td>
          <td>This reference architecture is oriented towards a local application that is stand-alone. This architecture will not support your system as it requires a server to allow users to use it concurrently. This was discarded due to the usage of local components.
</td>
        </tr>
        <tr>
          <td>Rich Internet Applications</td>
          <td>This reference architecture is oriented towards a browser application, however, it is using asynchronous javascript and XML. This was discarded due to not using some of the supported languages.</td>
        </tr>
        <tr>
          <td>Mobile Applications</td>
          <td>This reference architecture is oriented towards handheld devices. This was discarded as this system is not oriented towards mobile devices.</td>
        </tr>
      </table>
</td>
  </tr>
  <tr>
    <td>Physically structure the application using the Three-Tier Deployment pattern.</td>
    <td>Since this system must be accessed from a web browser (CON-5)
where (CON-3) and (CON-4) will be considered.
</td>
  </tr>
  <tr>
    <td>Deploy the application using Heroku Deployment. </td>
    <td>Access to the application is obtained via a web browser (CON-5).
This technology also facilitates (CON-1).
</td>
  </tr>
</table>

## Step 5: Instantiate Architecture Elements, Allocate Responsibilities, and Define Interfaces
The instantiation design decisions considered and made are summarized in the following table: 
| Design Decision and Location                                                                        | Rationale                                                                                                                                                                                        |
|-----------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Create a module that facilitates express endpoints in the business layer within the Web Application | The application facade component from the reference architecture is updated to include express endpoints. This will facilitate QA-1 and QA-2 and will help with UC-2, UC-5, UC-6, UC-7, and UC-8 |
| Within the Three-Tier Deployment, there will be a module implemented using Handlebars for users     | A component is added to the reference architecture to help GUI. This will facilitate QA-1 and QA-4 as well as will help with UC-6.                                                               |
| In the data layer, there is a module in the Web Application using Heroku as the main data source    | A component from the reference architecture is updated to allow access to Heroku, a hosting application. Facilitates all quality attributes, as well as constraints.                             |

## Step 6: Sketch Views and Record Design Decisions
| Element              | Responsibility                                                                                                                                                                                         |
|----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Presentation Layer   | This layer contains modules that control user interaction and use case-control.                                                                                                                        |
| User Interface       | This module renders the user interface and receives user inputs.                                                                                                                                       |
| Handlebars           | Templating engine, which takes information from server-side and prints it to the presentation layer.                                                                                                   |
| Business Layer       | This layer contains modules that perform business logic operations that can be executed to the business layer.                                                                                         |
| Express.js Endpoints | This is used for endpoints, allowing to build a REST-based project. It allows for defining GET and POST methods. It also lets us send messages between requests and send responses back to the client. |
| Business Workflow    | These components are responsible for managing (long-running) business processes, which may involve the execution of multiple use cases.                                                                |
| Business Components  | These components are responsible for retrieving and processing application data and applying business rules to this data.                                                                              |
| Business Entities    | These components represent the entities from the business domain and their associated business logic.                                                                                                  |
| Data Layer           | This layer contains modules that are responsible for data persistence and for communication with the time server.                                                                                      |
| Heroku               | This module is responsible for the persistence of business entities into the relational database.                                                                                                      |
| Service Agents       | These components abstract communication mechanisms used to transfer data to external services.                                                                                                         |
| Crosscutting         | Modules are applied to the whole system.                                                                                                                                                               |
| Security             | These components include cross-cutting functionality that handles security aspects such as authorization and authentication.                                                                           |
| Communication        | These components include cross-cutting functionality that handles communication mechanisms across layers and physical tiers.                                                                           |
| Operation Management | These components include cross-cutting functionality such as exception management, logging, and instrumentation, and validation.                                                                       |
<p align="center">
  <img src="https://i.ibb.co/2ssYYky/iteration-1-architecture.jpg">
</p>

## Step 7: Perform Analysis of Current Design and Review Iteration
| Not Addressed | Partially Addressed | Completely Addressed | Design Decisions Made During this Iteration                                                                                     |
|---------------|---------------------|----------------------|---------------------------------------------------------------------------------------------------------------------------------|
|               |         UC-1        |                      | Selected reference architecture establishes modules that will support this functionality.                                       |
|               |         UC-2        |                      | Selected reference architecture establishes modules that will support this functionality.                                       |
|               |         UC-6        |                      | Selected reference architecture establishes modules that will support this functionality.                                       |
|               |         UC-9        |                      | Selected reference architecture establishes modules that will support this functionality.                                       |
|               |         QA-1        |                      | Addition of modules within the reference architecture in the data layer to store new users. The details have not been defined.  |
|               |         QA-3        |                      | Supported with the inclusion of the Heroku development. But no further details were given.                                      |
|               |         QA-4        |                      | Introduction of three-tier deployment using handler bars. Further details will be provided in later iterations.                 |
|               |         QA-5        |                      | Addition of data source using Heroku. But no further details were given.                                                        |
|               |        CON-3        |                      | Support with the three developments.                                                                                            |
|               |        CON-4        |                      | No relevant decisions were made.                                                                                                |
|               |                     |         CON-5        | Selection of reference architecture architectures and deployment patterns.                                                      |

## Contributors:
* Sujeev Uthayakumar - 100744194
* Zirak Mughal - 100749132
* Yash Patel - 100746810
* Kalapan Kannathasan - 100759041
