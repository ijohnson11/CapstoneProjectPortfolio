## Capstone Project Portfolio

**Description**: This is the project portfolio for my Senior Project, spanning two semesters.  

For this project, I was tasked by my employer to develop a new web-based user interface to operate a scanner that utilizes quantitative transmisson ultra sound to aid in the detection of breast cancer.  

Though there were many challenges in developing this new version of a user interface, the final result shows a significant improvement in both asthetic and performance when compared to the previous interface.  


### Current Version  
--------
The current version of the interface was written using Qt and C++, which was the easiest way for the company to develop a functioning application for their embedded system, however, there were several issues with this version:  

  * The backend and frontend of the application were tightly coupled.
    * An issue with the frontend or backend will result in failure of the interface.
  * The interface looks outdated.
    * While serving it's purpose, the interface does not do a great job of presenting information in a more modern format.
  * Exception-handling within the application is sub-par.
    * When an exception is thrown, a splash dialog will appear, but will give a stack trace of where the error occured. This is not a user-friendly way to display an error to the scanner operator.
    * A user will be barred from using the rest of the interface, even if an exception does not affect other parts of the scanner.
  * Messaging between the different parts of the scanner was messy, and difficult to add to or modify.
    * Using a propietary messaging format, different nodes within the scanner had to send information to other nodes, but the method in which they were sent made it difficult to replicate in the case of future advancements.  
    
##### Current UI Screenshots:

Exam Management            |  Tank Statuses
:-------------------------:|:-------------------------:
![](https://github.com/ijohnson11/CapstoneProjectPortfolio/blob/master/images/Current%20UI/exam_management.png)  |  ![](https://github.com/ijohnson11/CapstoneProjectPortfolio/blob/master/images/Current%20UI/tank_statuses.png)  

Current Scan Information          |  New Exam Creation
:-------------------------:|:-------------------------:
![](https://github.com/ijohnson11/CapstoneProjectPortfolio/blob/master/images/Current%20UI/current_exam.png)  |  ![](https://github.com/ijohnson11/CapstoneProjectPortfolio/blob/master/images/Current%20UI/new_exam.png)

### New Version
--------
The new version of the interface is written in React for the front-end, which gives the following benefits:
 * Reuse of Components to allow for efficiency in design
   * Common principle of software development is DRY (Don't repeat yourself)
 * Use of react libraries allows easy imports of tools that are needed in the application
   * No need to reinvent the wheel
 * Re-rendering of individual components only occurs when its state changes
   * Optimizes effiency of the webpage, updates nearly instantaneously
 * Use of react-redux allows for multiple components to update based on changes to the application's state
   * No need to pass props all the way down from a parent component to a great-great-great grandchild component  
   
The new version's backend utilizes the javascript MqttBroker.js library for sending messages to and from the interface. Advantages:
 * The interface can subscribe to topics of the broker and change whenever information is updated
 * The broker can subscribe to topics and react accordingly whenever a message is received from the interface
 * The facilitation of data between the different nodes in the embedded system can now be sent in JSON format, which increases readability for developers, as well as modification of messages
 * The interface can act accordingly to errors based on where the error occured, allowing the user to access parts of the interface that were not affected
 
 ##### New UI screenshots  
 
 Exam Management            |  Tank Statuses
:-------------------------:|:-------------------------:
![](https://github.com/ijohnson11/CapstoneProjectPortfolio/blob/master/images/New%20UI/new_ui_exam_management.PNG)  |  ![](https://github.com/ijohnson11/CapstoneProjectPortfolio/blob/master/images/New%20UI/new_ui_tank_statuses.PNG)  

Current Scan Information          |  New Exam Creation
:-------------------------:|:-------------------------:
![](https://github.com/ijohnson11/CapstoneProjectPortfolio/blob/master/images/New%20UI/new_ui_current_scan.PNG)  |  ![](https://github.com/ijohnson11/CapstoneProjectPortfolio/blob/master/images/New%20UI/new_ui_new_exam.PNG)  

--------
### React in Action
The ease of creating common components is greatly increased thanks to react. For example, when rendering the buttons on the Exam Management container, the following code snippet generates all of them accordingly:  

```
 <div>
  <ExamManagementButton id="exam-manager-process" icon={faRedo} text="Process"/>
  <ExamManagementButton id="exam-manager-reprocess" icon={faRedo} rotation={180} text="Reprocess"/>
  <ExamManagementButton id="exam-manager-cancel" icon={faBan} text="Cancel" 
   disabled={selectedExams.length > 1 ? true : false}/>
  <ExamManagementButton id="exam-manager-edit" icon={faPencilAlt} text="Edit" 
   disabled={selectedExams.length > 1 ? true : false}/>
  <ExamManagementButton id="exam-manager-copy" icon={faCopy} text="Copy"/>
  <ExamManagementButton id="exam-manager-delete" icon={faTrash} text="Delete"/>
 </div>
```
### Design Process
--------
Throughout the creation of the new version, many steps were taken to ensure transparency between the team as well as a reference for the overall architecture. Some of the design processes used include:  
 * **Functional Requirements Documentation:**  
 
     ![](https://github.com/ijohnson11/CapstoneProjectPortfolio/blob/master/images/Documentation/function_req.PNG)  
 * **Flow Chart Diagrams:**  
 
     ![](https://github.com/ijohnson11/CapstoneProjectPortfolio/blob/master/images/Documentation/examTableFlowchart.png)  
 * **Block Diagrams:**  
 
     <img src="https://github.com/ijohnson11/CapstoneProjectPortfolio/blob/master/images/DocumentationBlockDiagram.png" style="height: 450px" />  
 * **Utilized agile SCRUM methodology to clearly communicate with development team including:**  
   * Daily Standups
   * Sprint planning
   * Retrospectives
   * Product Backlogs  
   
### Final Screencast  
--------

Below you can see the screencast of the final version of the user interface:  

<a> <img style="max-width:300px;" src="https://cdn.loom.com/sessions/thumbnails/717b8a2c71704afda4842e5c8cc24a12-with-play.gif"> </a>

 
