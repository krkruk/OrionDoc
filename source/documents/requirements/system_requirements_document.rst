.. This is a generic template to create a space-industry documentation for Orion Project

--------------------------------------------------------------------------------
System Requirements Document
--------------------------------------------------------------------------------

Introduction
================================================================================

Purpose of the document
--------------------------------------------------------------------------------

.. Describe briefly what is to be expected from reading of this document.

The aim of this document is to enumerate a set of system requirements.

Executive summary
--------------------------------------------------------------------------------

.. Describe briefly each chapter and what are final results of this document e.g. whether an assumed aim has been achieved.

The document identifies a set of system requirements to be considered as a main guidline in a rover design process. The guideline is based on ERC rules, URC rules and Team's considerations discovered in an analysis phase.

The document presents requirements in the following sections:
   * Safety requirements
   * Teleoperations and telemetry requirements
   * General rover requirements
   * Scientific mission requirements
   * Terrain traversal requirements
   * Blind traversal requirements
   * Power consumption requirements


Acronyms
================================================================================

.. A list of acronyms. If you have to add a new one, please add it into the included table

.. include:: /common/acronyms/acronyms_table.rst

Terms
================================================================================

.. A list of terms that require explanation to the reader.

.. include:: /common/terms/terms_table.rst


Requirements
================================================================================

General information
--------------------------------------------------------------------------------

Whenever the document mentions a *word*, it supposed to be mean the following:
   * **shall** - any requirement that contains the word *shall* is considered to be mandatory.
   * **should** - any requirement that contains the word *should* is considered to be optional yet expected in the final implementation.
   * **may** - any requirement that contains the word *may* is considered to be a nice to have feature but not critical for the overall mission.

Each identified requirement shall be given a unique identifier that follows the pattern:

.. code:: perl

   (?<REQ>\w{3})-(?<CATEGORY>\w{4})-(?<NUMBER>\d{4})(/(?<TASK>\w{4}))?


Group label definitions:   
   * REQ - the group is a keyword for 'Requirement', denoted as 'REQ'
   * CATEGORY - the group accepts 4-character category name
   * NUMBER - the group accepts 4-digit identification number
   * TASK - the optional group that assigns the requirement into a specific subgroup

.. note:: Examples:
   :name: Examples

   - **REQ-SAFE-0010**: Requirement - Safety requirements - ID 10
   - **REQ-SCIE-0010/GEOL**: Requirement - Scientific mission requirements - ID 10 / GEOLogical task

[SAFE] Safety requirements 
--------------------------------------------------------------------------------

.. list-table:: Safety requirements table
   :header-rows: 1

   * - ID
     - Requirement
     - Description

   * - REQ-SAFE-0010
     - The rover shall be equipped with an emergency stop button
     - The stop button shall provide the very basic level of safety in case of the rover is out of control

   * - REQ-SAFE-0011
     - The emergency stop button shall be red
     - The red stop button is the industry-known standard for marking safety buttons

   * - REQ-SAFE-0012
     - The emergency stop button shall be Commercial, Off-The Shelf component
     - The COTS stop button provides the greatest reliabilty

   * - REQ-SAFE-0013
     - The emergency stop button shall isolate the batteries from the system by single button hit.
     - The stop button shall cut the power circuit and keep it in such state until the rover is reset. The only exception are batteries installed in laptops that are not mandatory to be separated.

   * - REQ-SAFE-0014
     - The emergency stop button shall be installed in an easily accessible location. The location shall not inflict any injurers to anyone who hits the button.
     - The requirement is to provide minimal safety standard to anyone who has to kill the rover abruptly.

   * - REQ-SAFE-0015
     - The emergency stop button shall withstand hard hit
     - Anytime the button is hit, anyone who hits it must be assured the button acts correctly.

   * - REQ-SAFE-0020
     - The rover shall be equipped with an activity indicator
     - The activity indicator informs everyone in the vicinity the rover is operational and may/may not cause injuries to the people around.

   * - REQ-SAFE-0021
     - The activity indicator shall be visible in radius of 10m
     - The activity indicator warns people around the rover is operational.

   * - REQ-SAFE-0022
     - The activity indicator shall blink or flash
     - Non-continuous visual signals are easily noticable by humans thus safer.

   * - REQ-SAFE-0023
     - The activity indicator should be of either yellow, orange or red color
     - These colors are usually associated with danger and keep people vigilant.

   * - REQ-SAFE-0024
     - The activity indicator should be COTS
     - This is to provide reliability

   * - REQ-SAFE-0025
     - The activity indicator should be active 5 seconds before the rover performs any action.
     - During this time the rover should remain still.


[TELE] Teleoperations and telemetry requirements
--------------------------------------------------------------------------------

.. list-table:: Safety requirements table
   :header-rows: 1

   * - ID
     - Requirement
     - Description

   * - REQ-TELE-0010
     - The rover shall use one of the following wireless communication systems: Radio amateur bands, WiFi 2.4GHz, WiFi 5GHz, ISM bands, Other frequencies if an appropriate license is acquired
     - The Team shall meet communication requirements

   * - REQ-TELE-0020
     - The Team shall prepare a Radio Frequency Form.
     - The From shall provide wireless system information, frequencies used and RF spectrum.

   * - REQ-TELE-0030
     - Telemetry data should be stored for further evaluation
     - Logs such as power parameters, accelerations, send/received commands can become handy for further rover development and debugging.

   * - REQ-TELE-0040
     - Team may be asked to provide access to power circuits in non-invasive manners to measure power consumption of the rover independently by the jury.
     - This is to provide an exteral logging system.

