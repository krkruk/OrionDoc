--------------------------------------------------------------------------------
ERC 2019 Preliminary Report
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
   * - [ERC-2019]
     - European Rover Challenge 2019 - STUDENT rules
     - Rules and formula of ERC2019

Technical requirements definitions
================================================================================

Mechanics
--------------------------------------------------------------------------------

.. list-table:: General requirements
   :header-rows: 1
   :widths: 33 67

   * - Abbreviation
     - Descrption
   * - REQ-MECH-GEN-001
     - Environmental resistance (mostly dust and humidity)

.. list-table:: Chassis requirements
   :header-rows: 1
   :widths: 33 67

   * - Abbreviation
     - Descrption
   * - REQ-MECH-CHAS-001
     - Driving on dry, loose surface (sand, gravel)
   * - REQ-MECH-CHAS-002
     - Driving on hard, dry sufrace (concrete, grass)
   * - REQ-MECH-CHAS-003
     - Rotation in place
   * - REQ-MECH-CHAS-004
     - Driving onto an inclined surface (around 30-40 degrees)
   * - REQ-MECH-CHAS-005
     - Driving parallel to an inclined surface, having part of chassis slopped (by around 30-40 degrees)
   * - REQ-MECH-CHAS-006
     - Driving over off-road faults (minor bumps and holes)

.. list-table:: Manipulator requirements
   :header-rows: 1
   :widths: 33 67

   * - Abbreviation
     - Descrption
   * - REQ-MECH-MAN-001
     - Rock sample collection, with a minimum weight of 100g
   * - REQ-MECH-MAN-002
     - Soil sample collection, with a minimum weight of 200g
   * - REQ-MECH-MAN-003
     - Picking up an irregularly shaped object, with a minimum weight of 200g
   * - REQ-MECH-MAN-004
     - Switching a switch
   * - REQ-MECH-MAN-005
     - Rotating knob to specific position
   * - REQ-MECH-MAN-006
     - Measurement of force

Technical requirements fullfillment plan
================================================================================

Test plans
================================================================================

Used technologies
================================================================================

Chassis
--------------------------------------------------------------------------------

We have decided to use standard 4-wheel chassis made of aluminum and plywood, which gave us rigid and relatively light base for the rest of rover.
Every wheel has it's own DC motor taken from electric screwdriver, coupled with the wheel using worm gear. This effectively restricted maximum rover speed below 10m/s, while greatly increasing torque which is much more important.

Chasis is splitten into two separate, independent parts, connected to each other with gear. This kind of solution made whole chassis much more flexible in terms of overcoming bumps in the field, ensuring that at least two wheels at the same time will have traction.

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
