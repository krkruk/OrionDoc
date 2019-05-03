.. This is a generic template to create a space-industry documentation for Orion Project

--------------------------------------------------------------------------------
Technical & Management Proposal
--------------------------------------------------------------------------------

Introduction
================================================================================

Purpose of the document
--------------------------------------------------------------------------------
.. Describe briefly what is to be expected from reading of this document.

The purpose of this document is to raise Orion Team's willingness to participate in European Rover Challenge 2019. Thus, the document provides an analysis of ERC requirements and proposes a solution, which is a complete Mars rover. Moreover, it presents a management methodology and expected time and financial costs.


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

   * - [ERC-2018]
     - European Rover Challenge 2018 - STUDENT Rules
     - Rules and formula of ERC2018


Technical proposal
================================================================================


Analysis of the requirements
--------------------------------------------------------------------------------


.. list-table:: Compilance matrix
   :header-rows: 0

   * - REQ-ID
     - Requirement name
     - Description
     - Bidder's comment


Proposed solution
--------------------------------------------------------------------------------


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
     - Veteran of ERC (2 times), Master of Electronic Engineering, employed as a assistant professor at LUT

   * - Krzysztof K.
     - Project Manager, Sofware Developer
     - Veteran of ERC (2 times), Bachelor of Biomedical Engineering, employed as a software developer in space industry, division of Payload Data Processing

   * - Wojciech O.
     - Vice Project Manager, Software Developer
     - Veteran of ERC (1 time), a student of Software Engineering, interests in statically typed, compiled, programming languages

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

.. Use of COTS such as Arduino's and Raspberry Pi-s allows reducing overall prices of the robot
   Cheap robots can be considered as a disposable device just like medicine treats most of the sugical tools
   Thus, providing a cheap solution, as our rover, can be considered a great pros for the market. Moreover, free and *libre* software we developed can used by anyone who wants. This may not result in a pile of money but may end up with a kick to other projects.
