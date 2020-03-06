--------------------------------------------------------------------------------
ERC 2020 Preliminary Report
--------------------------------------------------------------------------------

Introduction
================================================================================

Purpose of the document
--------------------------------------------------------------------------------

Purpose of this document is to create core documentation of Orion III rover for European Rover Challenge competition

Scope of the document
--------------------------------------------------------------------------------

This document contains
    #. Technical requirements definitions, with ways to fullfill them and test plans
    #. Project assumptions - compared with proposal, if changed.
    #. Technologies which are, or will be, used in project
    #. Pre-final system breakdown structure
    #. Safety systems description
    #. Preliminary financial planning
    #. Present problems and issues, and how we are planning to solve them
    
Additionally, pre-final radio frequency form will be added to final preliminary report as appendix.

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

.. list-table:: Applicable document
   :header-rows: 1

   * - Reference ID
     - Title
     - Short document description
   * - [ERC-2020]
     - European Rover Challenge 2020 - STUDENT rules
     - Rules and formula of ERC2020

Technical requirements definitions
================================================================================

Mechanics
--------------------------------------------------------------------------------

.. list-table:: General requirements
   :header-rows: 1
   :widths: 25 40 15 10 50

   * - Abbreviation
     - Description
     - [ERC-2020] page
     - Test Methodology
     - Assumptions/solutions/testing.
   * - REQ-MECH-GEN-001
     - Environmental resistance (mostly dust and humidity)
     - 6
     - Review
     - Proper shell will be prepared. It will be able to withstand the elements.  

.. list-table:: Chassis requirements
   :header-rows: 1
   :widths: 25 40 15 10 50

   * - Abbreviation
     - Description
     - [ERC-2020] page
     - Test Methodology
     - Assumptions/solutions/testing.
   * - REQ-MECH-CHAS-001
     - Driving on dry, loose surface (sand, gravel)
     - 5, 6, 17, 19, 22, 23
     - Test
     - The rover will  be tested on multiple surfaces including sand, clay, gravel.
   * - REQ-MECH-CHAS-002
     - Driving on hard, dry sufrace (concrete, grass)
     - 5, 6, 17, 19, 22, 23
     - Test
     - The rover will  be tested on multiple surfaces including concrete, tiles, synthetic paneling, grass.
   * - REQ-MECH-CHAS-003
     - Rotation in place
     - 5, 6, 17, 19, 22, 23
     - Test
     - Tests will include driving in an arc, rotating in place and maneuvers in tight spaces.
   * - REQ-MECH-CHAS-004
     - Driving onto an inclined surface (around 30-40 degrees)
     - 5, 6, 17, 19, 22, 23
     - Test
     - The rover will be driven around the university campus which is full of steep hills, depressions and moderately hard terrain.
   * - REQ-MECH-CHAS-005
     - Driving parallel to an inclined surface, having part of chassis slopped (by around 30-40 degrees)
     - 5, 6, 17, 19, 22, 23
     - Test
     - The rover will be driven around the university campus which is full of steep hills, depressions and moderately hard terrain.
   * - REQ-MECH-CHAS-006
     - Driving over off-road faults (minor bumps and holes)
     - 5, 6, 17, 19, 22, 23
     - Test
     - The rover will be driven over small rocks, sharp small inclines, onto and down from curbs and stairs.

.. list-table:: Manipulator requirements
   :header-rows: 1
   :widths: 33 50 17

   * - Abbreviation
     - Description
     - [ERC-2020] page
   * - REQ-MECH-MAN-001
     - Rock sample collection, with a minimum weight of 25g
     - 17, 35
   * - REQ-MECH-MAN-002
     - Soil sample collection, with a minimum weight of 25g
     - 17, 35
   * - REQ-MECH-MAN-003
     - Picking up an irregularly shaped object, with a minimum weight of 300g
     - 22, 39
   * - REQ-MECH-MAN-004
     - Switching a switch
     - 21, 38
   * - REQ-MECH-MAN-005
     - Rotating knob to specific position
     - 21, 38
   * - REQ-MECH-MAN-006
     - Measurement of force
     - 21, 38
     
Electronics
--------------------------------------------------------------------------------     
.. list-table:: Manipulator requirements
   :header-rows: 1
   :widths: 33 50 17

   * - Abbreviation
     - Description
     - [ERC-2020] page
   * - REQ-ELEC-MAN-001
     - Measurement of voltage between 1V and 24V with 0.5V accuracy   
     - 21, 38
     
Safety
--------------------------------------------------------------------------------
.. list-table:: Safety requirements
   :header-rows: 1
   :widths: 33 50 17

   * - Abbreviation
     - Description
     - [ERC-2020] page
   * - REQ-SAFE-STOP-001
     - Accesible red emergency stop button
     - 7
   * - REQ-SAFE-STOP-002
     - Battery cutoff  
     - 7
   * - REQ-SAFE-STOP-003
     - Mechanical robustness of button
     - 7
   * - REQ-SAFE-BATT-001
     - Battery voltage and temperature measurement 
     - 7
   * - REQ-SAFE-BATT-002
     - Mitigation of fire risk  
     - 7
   * - REQ-SAFE-INDI-001
     - Rover equipped with yellow, orange or red indicator lamp visible from at least 10m
     - 7
   * - REQ-SAFE-INDI-002
     - Indicator light must activate 5 seconds before any rover movement
     - 7
   * - REQ-SAFE-AUTO-001
     - Autonomous operation must activate 5 seconds after issuing the command
     - 7
   * - REQ-SAFE-AUTO-002
     - Rover must safely handle command overflow
     - 7
     
Communication
--------------------------------------------------------------------------------     
.. list-table:: Communication requirements
   :header-rows: 1
   :widths: 33 50 17
   
   * - Abbreviation
     - Description
     - [ERC-2020] page
   * - REQ-COMM-BAND-001
     - The system must use legally available frequencies
     - 7
   * - REQ-COMM-BAND-002
     - The system must allow band switching 
     - 9
   * - REQ-COMM-FORM-001
     - The team must provide an RF form with relevant information 
     - 10     

Technical requirements fullfillment plan
================================================================================

Test plans
================================================================================

Used technologies
================================================================================

Chassis
--------------------------------------------------------------------------------

We have decided to use standard 4-wheel chassis made of aluminum and policarbonate sheets, which gave us rigid and relatively light base for the rest of rover.
Every wheel has it's own BLDC motor taken from electric hoverboard. This ensures formidable torque, speed control and high efficiency. The speed of the rover is limited by software.

Chasis is splitten into two separate, independent parts, connected to each other with a shaft. This kind of solution made whole chassis much more flexible in terms of overcoming bumps in the field, ensuring that at least two wheels at the same time will have traction.

Pre-final system breakdown structure
================================================================================

Safety systems description
================================================================================

Preliminary financial planning
================================================================================

Present problems and issues
================================================================================

.. list-table:: Present problems and potential solutions
   :header-rows: 1

   * - Problem
     - Descrption
     - Solution
   * - Management issues
     - There is not enough specialists in the project to effectively push it forward, and make constant progress. We have a lot of rookies which want to learn, but not enough time and people to teach them everything they need to know in order to work in project.
     - We need to find and recruit more specialists, with particular emphasis on programmers and electronics.
   * - Hardware stability issues
     - We are still not able to run all the tests properly, because our hardware (mostly power drivers) is failing in random places due to the bad engineering decisions made because of a hurry.
     - Re-create hardware the right way, utilizing PCB, COTS parts, and minimizing "garage engineering" factor to necessary miniumum. Regular testing is also required.
