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

Scope of the document
--------------------------------------------------------------------------------

.. Describe briefly each chapter and what are final results of this document e.g. whether an assumed aim has been achieved.

The document identifies a set of system requirements to be considered as a main guidline in a rover design process. The guideline is based on ERC rules, URC rules and Team's considerations discovered in an analysis phase.

The document presents requirements in the following sections:
   * Safety requirements
   * Teleoperations and telemetry requirements
   * General rover requirements
   * Robotic arm maneuverability requirements
   * Power consumption requirements
   * Mission-related requirements:
      * Scientific mission requirements
      * Maintenance mission requirements
      * Collection mission requirements
      * Autonomous traversal requirements


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

.. list-table:: Applicable documents
   :header-rows: 1

   * - Reference ID
     - Title
     - Short document description

   * - [ERC-2018]
     - European Rover Challenge 2018 - STUDENT Rules
     - Rules and formula of ERC2018


Requirements
================================================================================

.. note:: 
   Consider split the requirements identified below into groups

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
     - The stop button shall cut the power circuit and keep it in such state until the rover is reset. The only exception is batteries installed in laptops that are not mandatory to be separated.

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


[TELE] Teleoperation and telemetry requirements
--------------------------------------------------------------------------------

.. list-table:: Teleoperation and telemetry requirements
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


[GNRL] General rover requirements
--------------------------------------------------------------------------------

.. list-table:: General rover requirements
   :header-rows: 1

   * - ID
     - Requirement
     - Description

   * - REQ-GNRL-0010
     - A rover shall be a standalone, mobile platform.
     - No thethers are allowed

   * - REQ-GNRL-0020
     - The mass of the rover should not exceed 50-60kg
     - The heavier rover will be penalized and lighter one rewarded.

   * - REQ-GNRL-0030
     - It should be possible to inscribe the rover into an envelope shape of 0.75m diameter
     - General advise when building a rover

   * - REQ-GNRL-0040
     - The maximum speed of the rover shall not exceed 0.5 m/s
     - Real Mars rovers move even slower. Speed of 0.5 m/s provides additional safety margin in case the rover is out of control

   * - REQ-GNRL-0050
     - The rover shall keep its connection with a ground control facility at up 100m distance
     - General terrain conditions that can occur during the Challenge

   * - REQ-GNRL-0060
     - The Team shall be ready to deploy an antenna mast in a distance of 20m out of the ground control facility
     - Ground control facilities are unknown til the Challenge is started

   * - REQ-GNRL-0070
     - The rover shall withstand temperatures between 15 and 30 degrees Celcius
     - Usual temperatures in September in Poland

   * - REQ-GNRL-0080
     - The rover shall withstand wind gusts, light drizzle and high sunlight levels
     - The Challenge site may be outdoor

   * - REQ-GNRL-0090
     - The rover shall be able to traverse sandy, non-cohesive soil, hard and dry terrain as well as cobbled roads or other industrial surface types.
     - It expected the rover shall operate in off-road conditions as well as in industrial ones.

   * - REQ-GNRL-0100
     - The rover shall transmit video signal to the ground control for tele-operation purposes
     - Video feedback is essential to perform reliable, robust, human-driven, in-field scenarios
       

[ARMM] Robotic arm maneuverability requirements
--------------------------------------------------------------------------------

.. list-table:: Robotic arm maneuverability requirements
   :header-rows: 0

   * - ID
     - Requirement
     - Description

Mission-related requirements:
--------------------------------------------------------------------------------


[SCIE] Scientific mission requirements
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. list-table:: Scientific mission requirements
   :header-rows: 1

   * - ID
     - Requirement
     - Description

   * - REQ-SCIE-0010
     - The rover shall retrieve several types of geological samples
     - This is to complete an extensive geological trial

   * - REQ-SCIE-0011
     - The rover shall retrieve 3 surface samples
     - The sample can be either a hard rock or loose soil

   * - REQ-SCIE-0012
     - The rover shall excavate a trench
     - The trench may reveal some interesting geological structure

   * - REQ-SCIE-0013
     - The trench shall have minimum 30cm length, 5cm depth and a steep wall that clearly presents soil layers
     - The trench may reveal some interesting geological structure

   * - REQ-SCIE-0020
     - The rover shall be equiped with a set of containers
     - In order to store a speciment it is required to provide reliable, sealed containers

   * - REQ-SCIE-0021
     - A container shall be sealed
     - The sealed container is a must to prevent a speciment from contaminating

   * - REQ-SCIE-0022
     - The container shall provide capacity for at least 25g of a specimen. Preferably, 150g of speciment should be a goal
     - The greater amount of the speciment, more scientific trials can be performedo

   * - REQ-SCIE-0023
     - The container shall provide quality container sealing
     - Each container must provide sufficient quality of sealing to prevent contamination

   * - REQ-SCIE-0024
     - The rover shall be equipped with at least one specimen container
     - Otherwise, the rover will not be able to complete a task

   * - REQ-SCIE-0025
     - The design of a container should be designed to keep real mission requirements in mind
     - The design shall correspond real mission requirements so the construction possibly can be reused in a Mars mission

   * - REQ-SCIE-0026
     - The rover shall be equipped with at least 4 specimen containers
     - This is required to complete the task (3 superficial samples)) + 1 extra slot as a backup

   * - REQ-SCIE-0030
     - The rover shall retrieve a deep soil sample
     - The deep soil sample is a must to fully verify geological traits of Mars

   * - REQ-SCIE-0031
     - The rover shall retrieve the sample from 35cm below the surface
     - The deep soil sample is a must to fully verify geological traits of Mars

   * - REQ-SCIE-0032
     - The rover shall be prepared to retrieve a deep soil sample from the soil of various consistency
     - The soil may very from loose soil to hard gypsum. Hard nuggets can be expected.

   * - REQ-SCIE-0033
     - The speciment should be undisturbed, umixed, presenting clearly layered structure.
     - This is to provide maximum information e.g. layer stucture in terms of geological requirements

   * - REQ-SCIE-0034
     - The deep soil sample should be retrieved without exposure to the external conditions such as atmosphere
     - This prevents the sample to release its, presumably, gases

   * - REQ-SCIE-0040
     - The rover shall collect scientific-relevant data
     - This is the purpose of the mission...

   * - REQ-SCIE-0041
     - The rover shall collect photographic documentation of each sample
     - Photographic documentation is a key to an in-depth scientific analysis
       
   * - REQ-SCIE-0042
     - The rover shall collect photographic documentation of a sampling area
     - Collecting photographic documentation of a vicinity where a sample is collected is as much important as collecting the sample itself

   * - REQ-SCIE-0043
     - The rover shall collect images in resolution minimum 800x600 pixels.
     - The specimen should occupy a major part of image

   * - REQ-SCIE-0044
     - The rover should perform in-situ sample analysis
     - The more in-situ measurements is performed, the better. Weight, volume others parameters

   * - REQ-SCIE-0044
     - The rover should provide several measureable parameters of the sampling area
     - Weather may influence on conditions in which the sample is collected. Any measurement that may help determine wheather conditions is of a great help for scientists.
       
   * - REQ-SCIE-0045
     - The rover shall preserve all logs and documentation
     - Unstructured and preferably structured data is a must to perform scientific trials

   * - REQ-SCIE-0045
     - Ground control software may be customized to efficiently prepare a mission raport based on the collected data
     - This is to present a clear raport to jury.

   * - REQ-SCIE-0046
     - The rover should prevent shocks, vibrations caused by sample retriving activities to convey to the rover trunk
     - Separation of torque/forces acting on the rover trunk make the rover trunk makes it more reliable so more scientific trials can be performed


[MNTC] Maintenance mission requirements
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. list-table:: Maintenance mission requirements
   :header-rows: 1

   * - ID
     - Requirement
     - Description

   * - REQ-MNTC-0010
     - The rover shall be able to perform maintenance tasks
     - Definition of the mission

   * - REQ-MNTC-0011
     - The rover shall be able to a state of a switch
     - Switches are industrial grades

   * - REQ-MNTC-0011
     - The rover shall be able to rotate a knob
     - Knobs set values presented/displayed in a display nearby (no further than 15cm from the knob)

   * - REQ-MNTC-0012
     - The rover shall be plug a high power plug IEC 60309
     - One of the possible task to be performed on Mars

   * - REQ-MNTC-0013
     - The rover shall be able to probe voltage
     - Voltage is expected to be in range of 1.0VDC to 24.0VDC

   * - REQ-MNTC-0014
     - Voltage measurement accuracy shall be no greater than 0.5V DC
     - Measurement should not exceed 5% of tolerance

   * - REQ-MNTC-0020
     - The rover shall be able to access switches/buttons/knobs that are installed in any position
     - Final position of an item is unknown

   * - REQ-MNTC-0021
     - The rovel shall be able to operate on control items located in range [.2; 1.5]m above the ground level
     - General requirement

   * - REQ-MNTC-0030
     - The rover shall be able to detach protection lids/covers.
     - Some of the items that control maintenance panel can be covered

   * - REQ-MNTC-0030
     - The rover shall automate some of the tasks
     - The rover is a tool to be used by an astronaut. It should allow performing tasks with the least required astronaut's attention. Thus, automatization is expected.

   * - REQ-MNTC-0031
     - The rover should automatically retract the arm to the 'ready' position
     - This is relieve an astronaut of simple, tiring tasks

   * - REQ-MNTC-0032
     - The rover should automatically retract the arm to the 'transport' position
     - This is relieve an astronaut of simple, tiring tasks

   * - REQ-MNTC-0040
     - The rover shall provide augmented reality features
     - .

   * - REQ-MNTC-0041
     - The rover shall recognize elements found in the maintenance panel
     - It is a part of the augmented reality

   * - REQ-MNTC-0042
     - The rover shall suggest actions based on the detected features (buttons/switches/knobs...)
     - It is a part of the augmented reality

   * - REQ-MNTC-0043
     - The rover should automaticaly perform switching action
     - The rover is expected to change a state of a switch

   * - REQ-MNTC-0044
     - The rover should automatically press a button
     - As stated

   * - REQ-MNTC-0045
     - The rover should provide spacial awareness information
     - The rover should send distance data to the nearest obstacle on the movement path of the robotic arm

   * - REQ-MNTC-0045
     - The rover should track elements visible in the panel
     - This is to keep attention to the most important items in FOV

   * - REQ-MNTC-0050
     - The rover shall provide feedback information such as forces exerted on the robotic arm
     - This is to assure the rover does not destroy any equipment

   * - REQ-MNTC-0060
     - The rover shall use an adequate set of tools to perform each of the task
     - This is to assure the rover does not destroy any equipment and to perform the action robustly

   * - REQ-MNTC-0070
     - The HMI shall be ergonomic, user-friendly 
     - User experience is a part that facilitates any operation action. Well designed HMI reduced operator's training time


[COLL] Collection mission requirements
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

The mission assumes the rover serves as a Simple Fetching Rover (SFR). The rover is meant to collect an object, e.g. a box with a speciment, and automatically deliver the cargo to the ground control. Since time on Mars is precious, special emphasis is put on task automation.


.. list-table:: Maintenance mission requirements
   :header-rows: 1

   * - ID
     - Requirement
     - Description

   * - REQ-COLL-0010
     - A rover shall be equipped with a manipulator or other manipulator devices capable of catching, holding, stashing an cache object
     - For more details of the robotic arm requirements please refer to `[ARMM] Robotic arm maneuverability requirements`_

   * - REQ-COLL-0011
     - The rover shall be retrieve the object that can be partially covered with soild or buried
     - This is to simulate Mars weather that may cover any object in dust/soil

   * - REQ-COLL-0020
     - The rover shall be capable of reaching a destination where the object is located
     - For more details of the robotic platform please refer to `[GNRL] General rover requirements`_

   * - REQ-COLL-0030
     - The rover shall be equipped with a container capable of storing a predefined cache object
     - The purpose of the container is prevent the cache object from damage

   * - REQ-COLL-0031
     - The rover shall be equipped with at least 4 cache containers
     - This is required to complete the task (3 object to be cached) + 1 extra slot as a backup

   * - REQ-COLL-0032
     - The container should keep a cache object vertically
     - General rule

   * - REQ-COLL-0033
     - The container shall immobilize a cache object
     - This is to keep the object safe

   * - REQ-COLL-0034
     - The container shall be able to store a cylinder as described in the [ERC-2018]
     - General rule

   * - REQ-COLL-0035
     - The design of the container should be focused on facilitation if the object insertion
     - This is to reduce a risk of loosing and/or destroying the object when placing in the container

   * - REQ-COLL-0040
     - The rover should provide some task automation
     - This is to provide robust performance of the rover

   * - REQ-COLL-0041
     - The rover should automatically detect the cache object
     - This is a part of rover's augmented reality to relieve an astronaut in tele-operation

   * - REQ-COLL-0042
     - The rover should automatically approach the cache object
     - This is to automate simple tasks and relieve an astronaut/operator in tele-operation

   * - REQ-COLL-0043
     - The rover should automatically pick up the cache object
     - This is to automate simple tasks and relieve an astronaut/operator in tele-operation


Integration, verification and other requirements
================================================================================


