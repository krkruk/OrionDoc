=======================================
(LV3) Earth-base level software design
=======================================

Introduction
------------

This documents sets prerequisites for software development that runs a mission from the Earth base.

The document describes 2 types of software to be implemented.
    #. `Direct communication`_
    #. `Wireless communication`_


Overview
--------


Direct communication
====================

This type of application assumes a *direct* connection to the device. It means the serial device has to be connected to the PC present at the Earth base with a cable. The software has to provide convenient way to send command data to a microcontroller or an on-board computer. Moreover, the feedback data should be presented in a *neat* way.

Any app provides a debug functionalities that allows detecting any foreseen abnormalities that are described in LV1 paragraph.


Wireless communication
======================

The aim of wireless communication is to establish a reliable connection between the Earth-base station and the rover placed remotely.

The communication is held with one of the protocols chosen and described in LV2. The on-board framework provides a universal set of commands, which stands for an internal communication protocol. The messages are conveyed in a bidirectional way.

System Requirements
-------------------

.. note::
    ID code description:
        * LV? - software level e.g. LV2
        * MODULE - module code e.g DM
        * NNN - reference number
        * T - requirement type e.g. S - *S*\ oftware
        * -SR - System Requirement



+-------------------+---------+-------------------------------------------+------------------+
| #                 | Priority| Description                               | Basis            |
+===================+=========+===========================================+==================+
| `General Feature - System Requirements`_                                                   |
+-------------------+---------+-------------------------------------------+------------------+
| LV3-GF-001-S-SR_  | HIGH    | Reuse code for LV2 and LV3                |                  |
+-------------------+---------+-------------------------------------------+------------------+
| LV3-GF-002-S-SR_  | HIGH    | Provide reliable wireless connection      | LV2-GF-001-S-SR  |
|                   |         | using TCP/IP stack                        |                  |
+-------------------+---------+-------------------------------------------+------------------+
| LV3-GF-003-S-SR_  | HIGH    | Create standarized set of commands        |                  |
+-------------------+---------+-------------------------------------------+------------------+
| LV3-GF-004-S-SR_  | HIGH    | Unit testing a key part of design         |                  |
+-------------------+---------+-------------------------------------------+------------------+
| LV3-GF-005-S-SR_  | HIGH    | Store logs into to the database           |                  |
+-------------------+---------+-------------------------------------------+------------------+
| LV3-GF-006-S-SR_  | HIGH    | Generate automation scripts               |                  |
+-------------------+---------+-------------------------------------------+------------------+
| LV3-GF-007-S-SR_  | HIGH    | Send automation scripts to LV2            | LV3-GF-003-S-SR_ |
+-------------------+---------+-------------------------------------------+------------------+
| `Drive module - System Requirements`_                                                      |
+-------------------+---------+-------------------------------------------+------------------+
| LV3-DM-001-SG-SR_ | HIGH    | Support input devices                     |                  |
+-------------------+---------+-------------------------------------------+------------------+
| LV3-DM-002-SG-SR_ | HIGH    | Support dynamic key bingind               |                  |
+-------------------+---------+-------------------------------------------+------------------+
| LV3-DM-003-SG-SR_ | HIGH    | List available sensors                    |                  |
+-------------------+---------+-------------------------------------------+------------------+
| LV3-DM-004-SG-SR_ | HIGH    | Display sensor values in widgets          |                  |
+-------------------+---------+-------------------------------------------+------------------+
| LV3-DM-001-SD-SR_ | HIGH    | Connect to the device                     |                  |
+-------------------+---------+-------------------------------------------+------------------+




General Feature - System Requirements
=====================================

LV3-GF-001-S-SR
'''''''''''''''
The code must be maximally reusable. Separation of the hardcore back-end and the front-end is a must. The back-end part must be done in a way it is fairly easy to combine it with LV2 and/or LV3.

LV3-GF-002-S-SR
'''''''''''''''
Wireless communication must support both TCP and UDP protocols.

LV3-GF-003-S-SR
'''''''''''''''
Each of the modules provides a set of commands. These shall have the same structure for all comunication nodes.

LV3-GF-004-S-SR
'''''''''''''''
An API of any class must be explicitly described by a unit test. Program-related logic and other functionalies must be design in a way it is testable and verifyable. Preferably, the developer designs a valid interface so a mock objects can be created.

LV3-GF-005-S-SR
'''''''''''''''
Each of the applications should provide a logging funtionality. A detailed description can be found in LV2-GF-004-S. An application may assume all received data is needed to be stored.

LV3-GF-006-S-SR
'''''''''''''''
An application provides an interface for creating automation scripts of the rover. These scripts will allow the robot to perform repetetive tasks without user's participation in the process.

LV3-GF-007-S-SR
'''''''''''''''
An application loads an automation script and sends it to the robot. A form of the script shall follow a general pattern found in LV3-GF-003-S-SR_\.


Drive module - System Requirements
==================================

.. note::
    * SG - Software, General (Applicable for both SD and SW)
    * SD - Software, Direct (connection)
    * SW - Software, Wireless (connection)


LV3-DM-001-SG-SR
''''''''''''''''
An application supports the following inputs: a keyboard, a computer mouse, a gamepad, a joystick.

LV3-DM-002-SG-SR
''''''''''''''''
An application provides an interface that allows a user to change key binding for at least gamepads
and joystick. Any hard-coded binding must be properly documented in a form of the appendix and a contextual help menu.

LV3-DM-003-SG-SR
''''''''''''''''
Lists all available sensors provided by the platform.

LV3-DM-004-SG-SR
''''''''''''''''
Create a widget for all sensors listed in LV3-DM-002-SG-SR_. The widget must be interactive and beautiful to look at. See it more as a gage rather than a standard text label. The widgets must be placed in a proper positions so it simulates their real placement in the rover. See Hardware Design Document for more details.

LV3-DM-001-SD-SR
''''''''''''''''
Discover an ID of the device and connect to it. The connection is handled by the protocol described in the related parts in LV1-DM-\*.


Project Assumptions
-------------------

.. note::
    ID code description:
        * LV? - software level e.g. LV2
        * MODULE - module code e.g DM
        * NNN - reference number
        * T - requirement type e.g. S - *S*\ oftware
        * -PA - Project Assumptions

+-----------------------------+-------------------------------------------+------------------+
| #                           | Description                               | Reference        |
+=============================+===========================================+==================+
| `General Feature - Project Assumptions`_                                                   |
+-----------------------------+-------------------------------------------+------------------+
| LV3-GF-001-S-PA_            | Provide 1-1 wireless connection           | LV3-GF-002-S-SR_ |
+-----------------------------+-------------------------------------------+------------------+
| LV3-GF-002-S-PA_            | Use protocol-buffers by Google            | LV3-GF-003-S-SR_ |
+-----------------------------+-------------------------------------------+------------------+
| `Drive module - Project Assumptions`_                                                      |
+-----------------------------+-------------------------------------------+------------------+



General Feature - Project Assumptions
=====================================

LV3-GF-001-S-PA
'''''''''''''''
On the regular basis, each module can be accessed by a single remote device such as an Earth-base station PC. A protocol can be dynamically changed whether TCP or UDP is more reliable at the given moment.

LV3-GF-002-S-PA
'''''''''''''''
Each of the modules uses protocol-buffers [#]_\.


Drive module - Project Assumptions
==================================

.. rubric:: Reference documents

.. [#] https://developers.google.com/protocol-buffers/