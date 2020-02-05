.. This is a generic template to create a space-industry documentation for Orion Project

--------------------------------------------------------------------------------
Technical & Management Proposal
--------------------------------------------------------------------------------

Introduction
================================================================================

Purpose of the document
--------------------------------------------------------------------------------
.. Describe briefly what is to be expected from reading of this document.

The purpose of this document is to raise Orion Team's willingness to participate in European Rover Challenge 2020. Thus, the document provides an analysis of ERC requirements and proposes a solution, which is a complete Mars rover. Moreover, it presents a management methodology and expected time and financial costs.


Scope of the document
--------------------------------------------------------------------------------

.. Describe briefly each chapter and what are final results of this document e.g. whether an assumed aim has been achieved.

The document has been divided into three main chapters:
   #. Technical Proposal
   #. Management Proposal
   #. Time And Financial Costs Proposal

The document is meant to draft an overall process to design, construct and manage the interplanetary, Mars rover project that is to be undertaken by the Orion Team.

.. mention here that the documentation can be easily accessed and read by the means of readthedocs.io

Acronyms
--------------------------------------------------------------------------------

.. A list of acronyms. If you have to add a new one, please add it into the included table

.. include:: /common/acronyms/acronyms_table.rst

Terms and definitions
--------------------------------------------------------------------------------

.. A list of terms that require explanation to the reader.

.. include:: /common/terms/terms_table.rst

Applicable documents
================================================================================

.. A list of applicable documents to be placed as a reference to the project.
   For some of the documents this part is non-mandatory.

.. list-table:: Applicable documents
   :header-rows: 1

   * - Reference ID
     - Title
     - Short document description

   * - [ERC-2020]
     - European Rover Challenge 2020 - STUDENT Rules
     - Rules and formula of ERC2020


Technical proposal
================================================================================

.. A short presentation of the proposed (initial) solution to the challenge. That should state your initial compliance with the rules (understood here as the ERC rules), and clearly present achievable (within the project timeline) ideas, initial project assumptions and an analysis of challenge tasks (including scientific aspects of the Science task). Focus on showing that you read the rules and you know exactly what is required from you. Regarding achievable results, show how advanced your project is planned to be (in reference to what is required) and what is your planned way to achieve such state within the project timeline. Remember to first focus on critical requirements - those which are a must to take part in challenges (e.g. having robust emergency circuit with emergency button), then think about the rest of requirements (e.g. limitation of rover weight can give you more points but is not critical). Even if you are not going to present it at the proposal level, remember about traceability chain: requirement (the rule book based)-->assumption/compliance-->test methodology-->test plan, that will help you to create requirements that are easily verifiable and unitary/atomic. As you see from traceability chain, you need to track your requirements during the progress of the project and between the documents, so it is recommended to give them unique ID.  The assumptions/compliance column should contain a comment how requirement is going to be fulfilled in the design and final system (e.g. ‘relevant emergency circuit will be designed using industrial grade element’) or/and present any problems/discrepancies that are foreseen regarding particular requirement (e.g. ‘no drilling tool is foreseen due to schedule constraints’). The assumptions section should present any further assumptions that are not directly required by rules but are important to present on this level to show quality of the solution you are going to present during ERC. No need for details (e.g. what components will be used etc.) at this stage - you need to assure us that your project is well thought and can fit within the timeline. Consider quick analysis of each challenge task and short description on how your system is going to solve it. Do not forget about managerial aspects like preliminary schedule or project management methodologies.


Task analysis and resulting requirements
--------------------------------------------------------------------------------

* Science task

**ADD LATER** 

* Maintenance task

**ADD LATER** 

* Collection task

**ADD LATER** 

* Autonomous task

**ADD LATER** 

* Rover safety

--------------------------------------------------------------------------------

.. list-table:: Compilance matrix
   :header-rows: 0

   * - REQ-ID
     - Requirement name
     - Description
     - Bidder's comment


Proposed solution
--------------------------------------------------------------------------------


**ADD STUFF AND PICTURES, LOTS AND LOTS OF PICTURES WHEN I GET THEM**

* Mechanical solution

Our rover solution is based on a four wheeled chassis divided longitudinally into two sections connected by a free axle. The front section will be a base for the arm. The back section will house the main computer, measurement equipment, networking and batteries. The RF antenna, emergency power button and indicator light will be mounted on a straight vertical mast no higher than one meter. The arm and the manipulator will include six separate axes of movement, including one for rotation of the whole assembly, two to drive first and second stages and three for the manipulator.

The chassis propulsion will consist of four BLDC motors and motor drivers from hoverboards. The motors and drivers are rated 36V 10A. This solution is self-contained, provides simple maintenance, high efficiency due to the lack of gearing, is easily replacable and offers significant torque. 

* Electronics solution

**ADD LATER** 

* Communication solution

**ADD LATER** 

* Safety solution

**ADD LATER** 

* Data and measurements solution

**ADD LATER** 

* Navigation solution

**ADD LATER** 


Feasibility study and integration plan
--------------------------------------------------------------------------------

.. define how to accomplish tasks enumerated above. Moreover, present how the Team is going to integrate submodules into a single working system (propose CI, just like in software buisness)

Schedule and deliveries
--------------------------------------------------------------------------------

.. list-table:: Schedule
   :header-rows: 1

   * - Milestone ID
     - Name
     - Time
     - Description

   * - SCH-MLST-0010
     - Milestone 1: Chassis
     - :math:`T_0` + 2 months
     - By the end of the milestone the rover shall move freely and reliably as a remotely controlled vehicle. Software shall be capable of registering logs, including power consumption and angular velocities of each wheels. A preliminary PID controller for each wheel shall be implemented.
     
   * - SCH-MLST-0020
     - Milestone 2: Manipulator
     - :math:`T_0` + 4 months
     - The rover shall be equipped with a fully functional manipulator, capable of grasping objects and operate safely and reliably. The ground control shall retrieve feedback data such as position of each of robotic arm segments, crushing strength of the gripper. A basic automation, e.g. deploying an arm into an initial operation position, shall be implemented.

   * - SCH-MLST-0030
     - Milestone 3: Science, collection, maintenance tasks
     - :math:`T_0` + 6 months
     - The rover shall be able to store specimens samples and perform basic scientific trials. The rover shall be also to collect a cache object fulfiling the requirements. The rover shall be able to all defined 3 tasks with a user intervention. Rover automation shall be improved to the degree some manipulation operations will be done automatically such as approaching to an object. The rover shall be able to recognize, categorize and label basic maintenance-related objects.

   * - SCH-MLST-0040
     - Milestone 3: Autonomy task
     - :math:`T_0` + 8 months
     - The rover shall be able to traverse the terrain in a semi-autonomous manner. Path routing and hazard categorization based on simple conditions shall be implemented. The rover shall traverse automatically a designated path, without obstacle finding abilities. The Team shall have a solid basis and undestanding in using IMU and VO to further improve autonomy.

   * - SCH-MLST-0050
     - Milestone 3: Autonomy task
     - :math:`T_0` + 11 months
     - The rover shall be a well equipped robotic platform capable of performing several geological task, help an astronaut, collect cache objects and traverse terrain in at least semi-automated manner. All tests defined in VTP shall be successfully completed.


.. list-table:: List of deliverables
   :header-rows: 1

   * - Name
     - Type
     - Deliverable
     - Delivery date
     - Notes

   * - PROP
     - Document
     - Proposal
     - Initial submission
     - Announcing willingness to participate in ERC

   * - PREP
     - Document
     - Preliminary Report
     - Initial submission + 6months
     - Part of Team's admission process

   * - CDRV
     - Video
     - Critical Design Review video
     - T - 3 months
     - Part of Team's admission process

   * - FREP
     - Document
     - Final Report
     - T - 2months
     - Final part of Team's admission process

   * - VTP
     - Document
     - Verification Test Procedure
     - Along with FREP
     - A set of test descriptions.

   * - TPR
     - Document
     - Test Procedure Report
     - Along with FREP
     - Final results of tests defined in VTP


Technical and non-technical risks
--------------------------------------------------------------------------------

.. For your initial risk’s assessment think about general aspects of the project from project management, technical and other points of view. Do not go too deep at this stage - if you have some detailed risk on your mind try to capture it in more general but meaningful way. Focus on the project related risks and show that you know what to expect and what might be a problem to deliver on quality and on time. In mitigation put simple advice for yourself what to remember about or how to act to prevent risk occurrence. Additionally, you can add some description/analysis to the table highlighting areas of high risk and other sources and mitigation actions that were not captured in the table.>

.. list-table:: Major risks table
   :header-rows: 0

   * - Risk ID
     - Description
     - Likelihood
     - Severity/impact
     - Mitigation actions

     
Management proposal
================================================================================

Background
--------------------------------------------------------------------------------

.. Information about past projects and experience in rover development
   Results in past ERCs

Orion Team participated in European Rover Challenge twice.

Project Organization
--------------------------------------------------------------------------------

.. focus on skills and other projects elements that are useful for good quality project for ERC. Chose only few most important aspects, projects, experiences. Regarding key persons most important is what they bring to the project in terms of experience and skills. Do not forget to mention professionals/companies who advises you in a project

.. Present the primary management scheme in the project
   And justify why it is worth letting us to attend the ERC even though the team
   is quite small.

.. Define project management, how it is going to achieve milestones and reach the
   final goal, which is to complete and participate in the ERC. Enumerate
   several means how management is going to supervise the project


Key Personnel
--------------------------------------------------------------------------------


.. list-table:: Key Personnel
   :header-rows: 1

   * - Name
     - Function
     - Experience

   * - Marcin M.
     - Supervisor, MacGyver
     - Veteran of ERC (2 times), PhD Eng. of Electronic Engineering, employed as a assistant professor at LUT
     
   * - Wojciech O.
     - Project Manager, Software Developer
     - Veteran of ERC (1 time), a student of Software Engineering, interests in statically typed, compiled, programming languages
   
   * - Przemysław M.
     - Vice Project Manager, Software Developer
     - PLACEHOLDER HERE

   * - Krzysztof K.
     - External Expert
     - Veteran of ERC (2 times), Bachelor of Biomedical Engineering, employed as a software developer in space industry, division of Payload Data Processing

**ADD MORE DATA AND EXPERIENCE TO THE TEAM**

**ADD FINANCIAL SOURCES (ORION, EMBIQ, POLLUB)**

Time And Financial Costs Proposal
================================================================================

.. Time assumption is just a guess for this moment. Please just update it.

.. list-table:: Time costs
   :header-rows: 1

   * - REQ-ID
     - Task description
     - Time estimation (hours)

   * - CST-TIME-0010
     - Preparation of documentation
     - 120 (24h per document)

   * - CST-TIME-0020
     - Preparation of CDRV
     - 30 (shooting + editing, 3 working days)

.. list-table:: Financial estimation
   :header-rows: 1

   * - ID
     - Item name
     - Category
     - Price estimation in Euro (:math:`{\pm\sigma}`)

   * - CST-EURO-0010
     - Aluminum and welding
     - Structure components
     - 250 :math:`{\pm}` 50

   * - CST-EURO-0020
     - Motors and transmission
     - Propulsion
     - 300 :math:`{\pm}` 50


Project Commercialization
================================================================================

Development of BLDC driven mobile platforms for use in exploration, transportation, industry and recreation.

.. Use of COTS such as Arduino's and Raspberry Pi-s allows reducing overall prices of the robot
   Cheap robots can be considered as a disposable device just like medicine treats most of the sugical tools
   Thus, providing a cheap solution, as our rover, can be considered a great pros for the market. Moreover, free and *libre* software we developed can used by anyone who wants. This may not result in a pile of money but may end up with a kick to other projects.
   
Project Evolution
================================================================================
.. <recommendation: The last required and really important aspect of the proposal is how your project is going to evolve. Present a plan that you are going to start implementing in parallel to preparations for challenge. Show that your project is not going to be finished and forgotten after challenge. Realise the potential of your project (in all aspects) in terms of further people involvement, research or/and business. Think about how you can use the project to get involved into fruitful research or provide product/service to the others. This should be a realistic (may be ambitious) plan within the next 5 years with potential for further evolution and with reference to market/environment conditions, needs and forecasts. It does not to be a single aspect/idea. Use this exercise to start a movement and do not only describe it on paper but bring it to life!>

