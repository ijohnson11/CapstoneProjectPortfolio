## Capstone Project Portfolio

**Description**: This is the project portfolio for my Senior Project, spanning two semesters.  

For this project, I was tasked by my employer to develop a new web-based user interface to operate a scanner that utilizes quantitative transmisson ultra sound to aid in the detection of breast cancer.  

Though there were many challenges in developing this new version of a user interface, the final result shows a significant improvement in both asthetic and performance when compared to the previous interface.  

### Current Version  
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
    
#### Current UI Screenshots:

Exam Management            |  Tank Statuses
:-------------------------:|:-------------------------:
![](https://github.com/ijohnson11/CapstoneProjectPortfolio/blob/master/images/exam_management.png)  |  ![](https://github.com/ijohnson11/CapstoneProjectPortfolio/blob/master/images/tank_statuses.png)  

Current Scan Information          |  New Exam Creation
:-------------------------:|:-------------------------:
![](https://github.com/ijohnson11/CapstoneProjectPortfolio/blob/master/images/current_exam.png)  |  ![](https://github.com/ijohnson11/CapstoneProjectPortfolio/blob/master/images/new_exam.png)
