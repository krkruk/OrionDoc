.. This is a template for the Minutes of Meeting document that should be created during each offical meeting

--------------------------------------------------------------------------------
Verification Test Prodcedures
--------------------------------------------------------------------------------

+------------------------+-----------------------------------------------------+
| Date:                  | 2019-05-02                                          |
+------------------------+-----------------------------------------------------+
| Project:               | Orion Project                                       |
+------------------------+-----------------------------------------------------+
| Place:                 | Lublin HQ, Nadbystrzycka                            |
+------------------------+-----------------------------------------------------+
| Prepared by:           | Krzysztof K.                                        |
+------------------------+-----------------------------------------------------+

Introduction
================================================================================

The aim of this document is to provide a set of integration tests.

The set of test is a framework necessary to verify the following:

* The rover fulfills all stated requirements
* The rover is assembled in a reliable way
* The rover itself is reliable
* All possible defects are found before the ERC so no in-field fixes will be required

Acronyms
================================================================================

.. A list of acronyms. If you have to add a new one, please add it into the included table

.. include:: /common/acronyms/acronyms_table.rst

Terms and definitions
================================================================================

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

   * - [ERC-2019]
     - European Rover Challenge 2019 - STUDENT Rules
     - Rules and formula of ERC2019

        

Procedures
================================================================================

This chapter defines a set of tests the rover must pass in order to be considered
reliable enough to participate in ERC. Even though a strict Verification Test
Procedures document is not required by ERC, the Orion Team publishes it to
follow standards found in the industry.

Template
--------------------------------------------------------------------------------

A template defines a test algorithm. A Table below provides an example.

+---------------------------+--------------------------------------------------+
| Test Code: TST-ELEC-01    | Short description                                |
+---------------------------+--------------------------------------------------+
| Initial conditions        | Fully charged batteries                          |
+---------------------------+--------------------------------------------------+
| Environmental conditions  | Any                                              |
+---------------------------+--------------------------------------------------+
| Test goals                | Win it all!                                      |
+---------------------------+--------------------------------------------------+
| Corresponding requirements| REQ-SAFE-0010                                    |
+----------------+----------+------------------------------+-------------------+
| Code           | Test description                        | Pass criterion    |
+----------------+-----------------------------------------+-------------------+
| TST-ELEC-01/01 | Connect the batteries                   | N/A               |
+----------------+-----------------------------------------+-------------------+
| TST-ELEC-01/02 | Wait until the system boots up          | N/A               |
+----------------+-----------------------------------------+-------------------+
| TST-ELEC-01/03 | Drive                                   | N/A               |
+----------------+-----------------------------------------+-------------------+
| TST-ELEC-01/04 | Hit the emergency button                | The rover stops,  |
|                |                                         | Network conn dies |
+----------------+-----------------------------------------+-------------------+

Safety tests
--------------------------------------------------------------------------------


TST-SAFE-01 - Emergency Button: stop a vehicle
................................................................................

+---------------------------+--------------------------------------------------+
| TST-SAFE-01               | Test the Emergency Button by stopping a vehicle  |
+---------------------------+--------------------------------------------------+
| Initial conditions        | Fully charged batteries                          |
+---------------------------+--------------------------------------------------+
| Environmental conditions  | Any                                              |
+---------------------------+--------------------------------------------------+
| Test goals                | Prove the rover is safe for crowds               |
+---------------------------+--------------------------------------------------+
| Corresponding requirements| REQ-SAFE-0010 to REQ-SAFE-0015                   |
+----------------+----------+------------------------------+-------------------+
| Code           | Test description                        | Pass criterion    |
+----------------+-----------------------------------------+-------------------+
| TST-SAFE-01/01 | Connect the batteries                   | N/A               |
+----------------+-----------------------------------------+-------------------+
| TST-SAFE-01/02 | Wait until the system boots up          | N/A               |
+----------------+-----------------------------------------+-------------------+
| TST-SAFE-01/03 | Drive                                   | N/A               |
+----------------+-----------------------------------------+-------------------+
| TST-SAFE-01/04 | Hit the emergency button                | The rover stops,  |
|                |                                         | Network conn dies |
+----------------+-----------------------------------------+-------------------+

TST-SAFE-02 - Emergency Button: stop a manipulator
................................................................................

+---------------------------+--------------------------------------------------+
| TST-SAFE-02               | Test the emergency button by stopping the        |
|                           | manipulator                                      |
+---------------------------+--------------------------------------------------+
| Initial conditions        | Fully charged batteries                          |
+---------------------------+--------------------------------------------------+
| Environmental conditions  | Any                                              |
+---------------------------+--------------------------------------------------+
| Test goals                | Prove the rover is safe for crowds               |
+---------------------------+--------------------------------------------------+
| Corresponding requirements| REQ-SAFE-0010 to REQ-SAFE-0015                   |
+----------------+----------+------------------------------+-------------------+
| Code           | Test description                        | Pass criterion    |
+----------------+-----------------------------------------+-------------------+
| TST-SAFE-02/01 | Connect the batteries                   | N/A               |
+----------------+-----------------------------------------+-------------------+
| TST-SAFE-02/02 | Wait until the system boots up          | N/A               |
+----------------+-----------------------------------------+-------------------+
| TST-SAFE-02/03 | Order actuators to move                 | N/A               |
+----------------+-----------------------------------------+-------------------+
| TST-SAFE-02/04 | Hit the emergency button                | The rover stops,  |
|                |                                         | Network conn dies |
+----------------+-----------------------------------------+-------------------+

TST-SAFE-03 - Activity indicator: delay rover operation
................................................................................

+---------------------------+--------------------------------------------------+
| TST-SAFE-03               | Verify assumptions of the activity indicator     |
+---------------------------+--------------------------------------------------+
| Initial conditions        | Fully charged batteries                          |
+---------------------------+--------------------------------------------------+
| Environmental conditions  | Any                                              |
+---------------------------+--------------------------------------------------+
| Test goals                | Prove the rover is safe for crowds               |
+---------------------------+--------------------------------------------------+
| Corresponding requirements| REQ-SAFE-0020 to REQ-SAFE-0025                   |
+----------------+----------+------------------------------+-------------------+
| Code           | Test description                        | Pass criterion    |
+----------------+-----------------------------------------+-------------------+
| TST-SAFE-03/01 | Connect the batteries                   | N/A               |
+----------------+-----------------------------------------+-------------------+
| TST-SAFE-03/02 | Wait until the system boots up          | N/A               |
+----------------+-----------------------------------------+-------------------+
| TST-SAFE-03/03 | Order the rover to drive forward        | The lamp blinks,  |
|                |                                         | The rover does not|
|                |                                         | move              |
+----------------+-----------------------------------------+-------------------+
| TST-SAFE-03/04 | The rover moves after ~3 seconds after  | The rover moves   |
|                | the first command issued                |                   |
+----------------+-----------------------------------------+-------------------+
| TST-SAFE-03/05 | The lamp blinks while the rover stays   | The lamp blinks   |
|                | operational                             |                   |
+----------------+-----------------------------------------+-------------------+


Chassis and traversing tests
--------------------------------------------------------------------------------

TST-CHSS-01 - Drive at full speed
................................................................................

+---------------------------+--------------------------------------------------+
| TST-CHSS-01               | Check reliability of the integrated chassis      |
+---------------------------+--------------------------------------------------+
| Initial conditions        | Fully charged batteries & connected              |
+---------------------------+--------------------------------------------------+
| Environmental conditions  | Dry;grass/loose soil field;at least 200m of space|
+---------------------------+--------------------------------------------------+
| Test goals                | * Prove the driving capabilities are reliable    |
|                           | * Test the robustness of H-bridges               |
+---------------------------+--------------------------------------------------+
| Corresponding requirements| REQ-SAFE-0020 to REQ-SAFE-0025                   |
+----------------+----------+------------------------------+-------------------+
| Code           | Test description                        | Pass criterion    |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-01/01 | Start rover                             | N/A               |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-01/02 | Wait until the system boots up          | N/A               |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-01/03 | Drive 200m forward at full speed        | The rover reaches |
|                |                                         | the destination   |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-01/04 | Drive back 200m to the start site       | The rover reaches |
|                | backwards                               | the destination   |
+----------------+-----------------------------------------+-------------------+

TST-CHSS-02 - Climb a 30 degree hill
................................................................................

+---------------------------+--------------------------------------------------+
| TST-CHSS-02               | Climb a 30 degree hill                           |
+---------------------------+--------------------------------------------------+
| Initial conditions        | * Fully charged batteries & connected            |
|                           | * The rover is headed towards a hill             |
+---------------------------+--------------------------------------------------+
| Environmental conditions  | Dry;grass/loose soil filed;30deg inclination hill|
+---------------------------+--------------------------------------------------+
| Test goals                | * Prove the driving capabilities are reliable    |
|                           | * Test the robustness of H-bridges               |
|                           | * Test stability of the chassis                  |
|                           | * Test suspension limits                         |
+---------------------------+--------------------------------------------------+
| Corresponding requirements|                                                  |
+----------------+----------+------------------------------+-------------------+
| Code           | Test description                        | Pass criterion    |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-02/01 | Start rover                             | N/A               |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-02/02 | Wait until the system boots up          | N/A               |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-02/03 | Climb up the hill                       | The rover reaches |
|                |                                         | the destination   |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-02/04 | Climb down the hill                     | The rover reaches |
|                |                                         | the destination   |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-02/05 | Repeat TST-CHSS-02/03 and TST-CHSS-02/04| Each test is      |
|                | two more times                          | successfull       |
+----------------+-----------------------------------------+-------------------+

TST-CHSS-03 - Parallel traverse to a 30 degrees slope
................................................................................

+---------------------------+--------------------------------------------------+
| TST-CHSS-03               | Test stability of the chassis by traversing      |
|                           | a hill parallel to the slope                     |
+---------------------------+--------------------------------------------------+
| Initial conditions        | * Fully charged batteries & connected            |
|                           | * A side of the rover is headed towards a hill   |
+---------------------------+--------------------------------------------------+
| Environmental conditions  | Dry;grass/loose soil filed;30deg inclination hill|
+---------------------------+--------------------------------------------------+
| Test goals                | * Prove the driving capabilities are reliable    |
|                           | * Test the robustness of H-bridges               |
|                           | * Test stability of the chassis                  |
|                           | * Test suspension limits                         |
+---------------------------+--------------------------------------------------+
| Corresponding requirements|                                                  |
+----------------+----------+------------------------------+-------------------+
| Code           | Test description                        | Pass criterion    |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-02/01 | Start rover                             | N/A               |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-02/02 | Wait until the system boots up          | N/A               |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-02/03 | Drive towards the hill 15m and watch if | The rover reaches |
|                | the rover does not loose the balance    | the destination   |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-02/04 | Drive back backwards                    | The rover reaches |
|                |                                         | the destination   |
+----------------+-----------------------------------------+-------------------+

TST-CHSS-04 - Diagonally climb a 30 degrees slope
................................................................................

+---------------------------+--------------------------------------------------+
| TST-CHSS-04               | Diagonally climb a 30 degrees slope              |
+---------------------------+--------------------------------------------------+
| Initial conditions        | * Fully charged batteries & connected            |
|                           | * A side of the rover is headed towards a hill   |
+---------------------------+--------------------------------------------------+
| Environmental conditions  | Dry;grass/loose soil filed;30deg inclination hill|
+---------------------------+--------------------------------------------------+
| Test goals                | * Prove the driving capabilities are reliable    |
|                           | * Test the robustness of H-bridges               |
|                           | * Test stability of the chassis                  |
|                           | * Test suspension limits                         |
+---------------------------+--------------------------------------------------+
| Corresponding requirements|                                                  |
+----------------+----------+------------------------------+-------------------+
| Code           | Test description                        | Pass criterion    |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-04/01 | Start rover                             | N/A               |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-04/02 | Wait until the system boots up          | N/A               |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-04/03 | Turn 15 degrees left or right to climb  | N/A               |
|                | the hill diagonally                     |                   |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-04/04 | Climb the hill, watch if the rover keeps| The rover reaches |
|                | its balance                             | the destination   |
+----------------+-----------------------------------------+-------------------+

TST-CHSS-05 - Drive over an obstacle
................................................................................

+---------------------------+--------------------------------------------------+
| TST-CHSS-05               | Drive over an obstacle                           |
+---------------------------+--------------------------------------------------+
| Initial conditions        | * Fully charged batteries & connected            |
|                           | * The rover faces a 15cm high obstacle           |
+---------------------------+--------------------------------------------------+
| Environmental conditions  | Dry;grass/loose soil filed;15cm high obstacle    |
+---------------------------+--------------------------------------------------+
| Test goals                | * Prove the driving capabilities are reliable    |
|                           | * Test the robustness of H-bridges               |
|                           | * Test stability of the chassis                  |
|                           | * Test suspension limits                         |
+---------------------------+--------------------------------------------------+
| Corresponding requirements|                                                  |
+----------------+----------+------------------------------+-------------------+
| Code           | Test description                        | Pass criterion    |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-05/01 | Start rover                             | N/A               |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-05/02 | Wait until the system boots up          | N/A               |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-05/03 | Align the rover in a way one of its     | N/A               |
|                | wheels faces the obstacle               |                   |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-05/04 | Drive forward and drive over the        | The rover drives  |
|                | obstacle. Observe if there is any change| over successfully.|
|                | in a heading of the rover.              | The heading stays |
|                | in a heading of the rover.              | the same +/- 5deg.|
+----------------+-----------------------------------------+-------------------+


TST-CHSS-06 - Drive through a pit
................................................................................

+---------------------------+--------------------------------------------------+
| TST-CHSS-06               | Drive through a pit                              |
+---------------------------+--------------------------------------------------+
| Initial conditions        | * Fully charged batteries & connected            |
|                           | * The rover faces a wheel size pit               |
+---------------------------+--------------------------------------------------+
| Environmental conditions  | Dry;grass/loose soil filed;wheel size pit        |
+---------------------------+--------------------------------------------------+
| Test goals                | * Prove the driving capabilities are reliable    |
|                           | * Test the robustness of H-bridges               |
|                           | * Test stability of the chassis                  |
|                           | * Test suspension limits                         |
+---------------------------+--------------------------------------------------+
| Corresponding requirements|                                                  |
+----------------+----------+------------------------------+-------------------+
| Code           | Test description                        | Pass criterion    |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-06/01 | Start rover                             | N/A               |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-06/02 | Wait until the system boots up          | N/A               |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-06/03 | Align the rover in a way one of its     | N/A               |
|                | wheels faces the pit                    |                   |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-06/04 | Drive forward through the pit. Observe  | The rover drives  |
|                | if there is any change in a heading of  | thru successfully.|
|                | of the rover.                           | The heading stays |
|                | in a heading of the rover.              | the same +/- 5deg.|
+----------------+-----------------------------------------+-------------------+

TST-CHSS-07 - Wheel failure
................................................................................

+---------------------------+--------------------------------------------------+
| TST-CHSS-07               | Simulate a wheel failure                         |
+---------------------------+--------------------------------------------------+
| Initial conditions        | * Fully charged batteries & connected            |
|                           | * The rover faces a wheel size pit               |
+---------------------------+--------------------------------------------------+
| Environmental conditions  | Dry;grass/loose soil filed;                      |
+---------------------------+--------------------------------------------------+
| Test goals                | * Prove the driving capabilities are reliable    |
|                           | * Test the robustness of H-bridges               |
|                           | * Test stability of the chassis                  |
|                           | * Test suspension limits                         |
|                           | * Test if the rover can continue a mission in    |
|                           |   case of failure                                |
+---------------------------+--------------------------------------------------+
| Corresponding requirements|                                                  |
+----------------+----------+------------------------------+-------------------+
| Code           | Test description                        | Pass criterion    |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-07/01 | Physically disconnect power cables from | N/A               |
|                | one of the wheels. Start the rover      | N/A               |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-07/02 | Wait until the system boots up          | N/A               |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-07/03 | Drive forward 50m. Compensate the drag  | The rover reaches |
|                | manually                                | the destination   |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-07/04 | Drive back to the start location        | The rover reaches |
|                | backwards. Compensate the drag manually | the destination   |
+----------------+-----------------------------------------+-------------------+

TST-CHSS-08 - Lab: Vibration resilience
................................................................................

+---------------------------+--------------------------------------------------+
| TST-CHSS-08               | Test if the rover can endure exosure to          |
|                           | vibrations in a lab environment                  |
+---------------------------+--------------------------------------------------+
| Initial conditions        | * Fully charged batteries & connected            |
|                           | * A vibrator is connected to the chassis         |
+---------------------------+--------------------------------------------------+
| Environmental conditions  | Lab; attached vibration motor                    |
+---------------------------+--------------------------------------------------+
| Test goals                | * Prove all cable connections are made well      |
+---------------------------+--------------------------------------------------+
| Corresponding requirements|                                                  |
+----------------+----------+------------------------------+-------------------+
| Code           | Test description                        | Pass criterion    |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-08/01 | Start the rover                         | N/A               |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-08/02 | Start the vibrator                      | N/A               |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-08/03 | Observe telemetry, especially IMU for   | The rover sends   |
|                | 10 minutes                              | the telemetry info|
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-08/04 | Stop the vibrator                       | The rover stays   |
|                |                                         | functional        |
+----------------+-----------------------------------------+-------------------+

TST-CHSS-09 - Vibration resilience in real environment
................................................................................

+---------------------------+--------------------------------------------------+
| TST-CHSS-09               | Test if the rover can endure exosure to          |
|                           | vibrations in a real environment. A staircase    |
|                           | test                                             |
+---------------------------+--------------------------------------------------+
| Initial conditions        | * Fully charged batteries & connected            |
|                           | * A top floor of the 4-floor building            |
+---------------------------+--------------------------------------------------+
| Environmental conditions  | Four wheel building                              |
+---------------------------+--------------------------------------------------+
| Test goals                | * Prove all cable connections are made well      |
+---------------------------+--------------------------------------------------+
| Corresponding requirements|                                                  |
+----------------+----------+------------------------------+-------------------+
| Code           | Test description                        | Pass criterion    |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-09/01 | Start the rover                         | N/A               |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-09/02 | Drive down a staircase                  | N/A               |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-09/03 | Observe telemetry                       | The rover sends   |
|                |                                         | the telemetry info|
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-09/04 | Check telemetry once the rover reaches  | The rover stays   |
|                | the destination                         | functional        |
+----------------+-----------------------------------------+-------------------+
| TST-CHSS-09/05 | Drive 10m forward, perform in-place     | The rover stays   |
|                | 360deg turns left and right, drive back | functional        |
+----------------+-----------------------------------------+-------------------+
