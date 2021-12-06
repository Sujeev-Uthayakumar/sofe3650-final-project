# SOFE 3650 Final Project Iteration 3: Addressing Quality Attribute Scenario Driver (QA-3)
In this iteration, additional architecture elements are revised and quality attribute scenarios ares addressed.<br/>

In this section, the results of the activities performed in each of the steps in the third iteration of the design process are presented. This iteration is used to build off of the fundamental decisions made in iteration 1 and 2, which leads to an important quality attribute scenario.

## Table of Contents:
- [Iteration 3 PDF](https://github.com/Sujeev-Uthayakumar/sofe3650-final-project/blob/master/Iteration%203/Project%20Deliverable%203%20Iteration%203.pdf)
- [Step 2: Establish Iteration Goal by Selecting Drivers](#Step-2-Establish-Iteration-Goal-By-Selecting-Drivers)
- [Step 3: Choose One or More Elements of the System to Refine](#Step-3-Choose-One-or-More-Elements-of-the-System-to-Refine)
- [Step 4: Choose One or More Design Concepts That Satisfy the Selected Drivers](#Step-4-Choose-One-or-More-Design-Concepts-That-Satisfy-the-Selected-Drivers)
- [Step 5: Instantiate Architectural Elements, Allocate Responsibilities, and Define Interfaces](#Step-5-Instantiate-Architectural-Elements-Allocate-Responsibilities-and-Define-Interfaces)
- [Step 6: Sketch Views and Record Design Decisions](#Step-6-Sketch-Views-and-Record-Design-Decisions)
- [Step 7: Perform Analysis of Current Design and Review Iteration Goal and Achievement of Design Purpose](#Step-7-Perform-Analysis-of-Current-Design-and-Review-Iteration-Goal-and-Achievement-of-Design-Purpose)
- [Contributors:](#Contributors)

## Step 2: Establish Iteration Goal By Selecting Drivers:
For this iteration, the architect focuses on the QA-3 scenario which sends location coordinates but shifts it slightly for privacy reasons.

## Step 3: Choose One or More Elements of the System to Refine:
For this availability scenario, the elements that will be refined are the physical nodes that were identified during the second iteration:
- GeoLocation

## Step 4: Choose One or More Design Concepts That Satisfy the Selected Drivers:
The design concepts used in this iteration are the following:
| Design Decisions and Location | Rationale and Assumptions |
| --- | --- |
| Introduce the ability to shift user location based on the graphic data taken from GeoLocation | By refining the element system can have increased security as the user location direct location will not be revealed to the other users within the chat app. |

## Step 5: Instantiate Architectural Elements, Allocate Responsibilities, and Define Interfaces: 
The instantiation design decisions are summarized in the following table: 
| Design Decisions and Location                | Rationale                                                                                                                                                                                                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Deploy a method that will shift the location | The user's location will be taken by the user pressing a button. The location will be processed by GeoLocation MDN, and the geographical coordinates will be shifted. The coordinate will be processed through google's map API and print within the chat |

## Step 6: Sketch Views and Record Design Decisions:
The figure below shows a refined deployment diagram that includes the introduction of redundancy in the system.
<p align="center">
  <img src="https://i.ibb.co/4NTS2g1/iteration-3-deployment.jpg">
<p align="center"><b>Figure 4.1 - Final deployment diagram based off of decisions made in iteration 3, including the GeoLocation API</b></p>
</p>

## Step 7: Perform Analysis of Current Design and Review Iteration Goal and Achievement of Design Purpose:
| Not Addressed | Partially Addressed | Completely Addressed | Design Decisions Made During this Iteration                                                                                                                                    |
|---------------|---------------------|----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|               |         QA-1        |                      | No relevant decisions were made.                                                                                                                                               |
|               |                     |         QA-3         | By shifting the location obtained by Geolocation we are able to hide the user's direct location. Thus, giving the user's relative location as opposed to an absolute location. |
|               |         QA-4        |                      | No relevant decisions were made.                                                                                                                                               |
|               |         QA-5        |                      | No relevant decisions were made.                                                                                                                                               |
|               |        CON-3        |                      | No relevant decisions were made.                                                                                                                                               |
|               |        CON-4        |                      | No relevant decisions were made.                                                                                                                                               |
|               |        CON-5        |                      | No relevant decisions were made.                                                                                                                                               |
|               |        CRN-2        |                      | No relevant decisions were made.                                                                                                                                               |
|               |        CRN-3        |                      | No relevant decisions were made.                                                                                                                                               |
|               |        CRN-4        |                      | No relevant decisions were made.                                                                                                                                               |

## Contributors:
* Sujeev Uthayakumar - 100744194
* Zirak Mughal - 100749132
* Yash Patel - 100746810
* Kalapan Kannathasan - 100759041
