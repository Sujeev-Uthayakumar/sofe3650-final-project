# Table of Contents:
- [System Requirements PDF](https://github.com/Sujeev-Uthayakumar/sofe3650-final-project/blob/master/System%20Requirements/Project%20Deliverable%203%20-%20System%20Requirements.pdf)
- [System Requirements](#System-Requirements)
- [Contributors](#Contributors)

## System Requirements:

Use Cases:<br>
The following figure showcases the primary use cases of the USChat application, which were derived from our previously discussed requirements.
<p align="center">
  <img src="https://i.ibb.co/D9g4txG/Untitled-Diagram-drawio.png">
<p align="center"><b>Figure 1.1 - Use case model for USChat chat application system</b></p>
</p>


Quality Attributes Scenarios:
| ID   | Quality Attribute | Scenario                                                                                                                            | Associated |
|------|-------------------|-------------------------------------------------------------------------------------------------------------------------------------|------------|
| QA-1 | Scalability       | Create a user and send it to be stored within the server, with an ever-expanding user base.                                         | UC-1, UC-9 |
| QA-2 | Usability         | Users are able to send messages and the timestamps are recorded.                                                                    | UC-2       |
| QA-3 | Security          | Send location coordinates, however an offset will be placed on the coordinates to protect user privacy.                       | UC-8       |
| QA-4 | Performance       | The ability to perform all tasks without comprising real-time functionality. Where messages are seen within a second of being sent. | All        |
| QA-5 | Availability      | Users are able to see other users as well as the admin.                                                                             | UC-6       |

Constraints:
| ID    | Constraints                                                                                                                                    |
|-------|------------------------------------------------------------------------------------------------------------------------------------------------|
| CON-1 | A minimum of 10 users must be supported by the system.                                                                                         |
| CON-2 | Messages should be sent and displayed in less than 1 second on either end.                                                                     |
| CON-3 | Users should be authenticated before joining the room, and after through continuous checking.                                                  |
| CON-4 | Network connection between user and server must have low bandwidth and be reliable.                                                            |
| CON-5 | The system must be accessed through a web browser such as Chrome, Firefox Safari, etc.                                                         |
| CON-6 | Large amount of messages will have to be stored in a single session.                                                                           |
| CON-7 | An existing relation database server must be used. This server must hold the user and room information that will be used to fetch information. |

Architectural Concerns:
| ID    | Concern                                                                                         |
|-------|-------------------------------------------------------------------------------------------------|
| CRN-1 | Establishing an overall initial system structure.                                               |
| CRN-2 | Leverage the team???s knowledge about JSON and dependencies, including handlebars, and socket.io. |
| CRN-3 | Allocate work to members of the development team.                                               |

## Contributors:
* Sujeev Uthayakumar - 100744194
* Zirak Mughal - 100749132
* Yash Patel - 100746810
* Kalapan Kannathasan - 100759041
