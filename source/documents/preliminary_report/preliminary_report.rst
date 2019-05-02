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

   * - Abbreviation
     - Descrption
   * - REQ-MECH-GEN-001
     - Environmental resistance (mostly dust and humidity)

.. list-table:: Chassis requirements
   :header-rows: 1

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
     - Measurement of force applied by grasper
