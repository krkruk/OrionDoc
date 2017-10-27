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


Drive module
============
...


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
| LV3-GF-008-S-SR_  | HIGH    | Support input devices                     |                  |
+-------------------+---------+-------------------------------------------+------------------+
| LV3-GF-009-S-SR_  | HIGH    | Provide dynamic input device key binding  |                  |
+-------------------+---------+-------------------------------------------+------------------+
| `Drive module - System Requirements`_                                                      |
+-------------------+---------+-------------------------------------------+------------------+
| LV3-DM-001-SG-SR_ | HIGH    | Provide default key binding               |                  |
+-------------------+---------+-------------------------------------------+------------------+
| LV3-DM-002-SG-SR_ | HIGH    | Provide customizable key binding          |                  |
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
An API of any class must be explicitly described by a unit test. Program-related logic and other functionalies must be design in a way it is testable and verifyable. Preferably, the developer designs a valid interface so mock objects can be created.

LV3-GF-005-S-SR
'''''''''''''''
Each of the applications should provide a logging funtionality. A detailed description can be found in LV2-GF-004-S. An application may assume all received data is needed to be stored.

LV3-GF-006-S-SR
'''''''''''''''
An application provides an interface for creating automation scripts of the rover. These scripts will allow the robot to perform repetetive tasks without user's participation in the process.

LV3-GF-007-S-SR
'''''''''''''''
An application loads an automation script and sends it to the robot. A form of the script shall follow a general pattern found in LV3-GF-003-S-SR_\.

LV3-GF-008-S-SR
''''''''''''''''
An application supports the following inputs: a keyboard, a computer mouse, a gamepad, a joystick.

Each function should be represented by command abstraction so the system scales easily. The following states can be distinguished:
    * Analog axis input is converted into a range of commands e.g. speed
    * Pressing the button triggers an event
    * A pairs of buttons increments/decrements a value
    * Analog axis can be replaced with a pair of increment/decrement buttons

LV3-GF-009-S-SR
''''''''''''''''
Each pair of (command, input) can be modified.
    * command - a functionality defined by the structure of classes that executes a hard-coded task.
    * input - a key/button/axis the command is feed with. A user must be able to change it, so the gamepad control supports one's needs


Drive module - System Requirements
==================================

.. note::
    * SG - Software, General (Applicable for both SD and SW)
    * SD - Software, Direct (connection)
    * SW - Software, Wireless (connection)



LV3-DM-001-SG-SR
''''''''''''''''
An application is supplied with a default and documented key binding for a keyboard, a gamepad and a joystick.

LV3-DM-002-SG-SR
''''''''''''''''
An application provides an input dialog that binds keys of the a given input devices to functionalities of the rover.

Assume the rover is controlled with a keyboard. Then binding should look like this:
    * FORWARD -> W
    * BACKWARD -> S
    * LEFT -> A
    * RIGHT -> D

These values can be modified by the user and stored. Only the latest configuration should be applied. The previous settings should be discarded.

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

+-----------------------------+-------------------------------------------+-------------------+
| #                           | Description                               | Reference         |
+=============================+===========================================+===================+
| `General Feature - Project Assumptions`_                                                    |
+-----------------------------+-------------------------------------------+-------------------+
| LV3-GF-001-S-PA             | Tools: C++(11|14), Qt, protobuf, xboxdrv  | General           |
+-----------------------------+-------------------------------------------+-------------------+
| LV3-GF-002-S-PA_            | Unit testing framework: Qt Unit Tests     | General           |
+-----------------------------+-------------------------------------------+-------------------+
| LV3-GF-003-S-PA             | Supply code in dynamically loaded libs    |                   |
|                             | if it allows reusing the lib in submodules|                   |
+-----------------------------+-------------------------------------------+-------------------+
| LV3-GF-004-S-PA_            | Provide 1-1 wireless connection           | LV3-GF-002-S-SR_  |
+-----------------------------+-------------------------------------------+-------------------+
| LV3-GF-005-S-PA_            | Use protocol-buffers by Google            | LV3-GF-003-S-SR_  |
+-----------------------------+-------------------------------------------+-------------------+
| LV3-GF-006-S-PA_            | Send commands to the LV2                  | LV3-GF-002-S-SR_  |
+-----------------------------+-------------------------------------------+-------------------+
| LV3-GF-007-S-PA_            | Select telemetry update mode              |                   |
+-----------------------------+-------------------------------------------+-------------------+
| LV3-GF-008-S-PA_            | Support input devices                     | LV3-GF-008-S-SR_  |
+-----------------------------+-------------------------------------------+-------------------+
| LV3-GF-009-S-PA_            | Support key binding                       | LV3-GF-009-S-SR_  |
+-----------------------------+-------------------------------------------+-------------------+
| LV3-GF-010-S-PA_            | Generate automation scripts               | LV3-GF-006-S-SR_  |
+-----------------------------+-------------------------------------------+-------------------+
| `Drive module - Project Assumptions`_                                                       |
+-----------------------------+-------------------------------------------+-------------------+
| LV3-DM-001-SG-PA_           | Modes: user-controlled, scripting, auto   | General           |
+-----------------------------+-------------------------------------------+-------------------+
| LV3-DM-002-SG-PA            | Default binding                           | LV3-GF-009-S-PA_  |
+-----------------------------+-------------------------------------------+-------------------+
| LV3-DM-003-SG-PA_           | Display feedback values in nice widgets   | LV3-DM-004-SG-SR_ |
+-----------------------------+-------------------------------------------+-------------------+
| LV3-DM-001-SW-PA_           | Scripting                                 | LV3-DM-004-SG-SR_ |
+-----------------------------+-------------------------------------------+-------------------+



General Feature - Project Assumptions
=====================================

LV3-GF-002-S-PA
'''''''''''''''
Each functionality is covered by a set of unit tests. Any reported SPR must be documented and solved in tests.

LV3-GF-004-S-PA
'''''''''''''''
On the regular basis, each module can be accessed by a single remote device such as an Earth-base station PC. A protocol can be dynamically changed whether TCP or UDP is more reliable at the given moment.

LV3-GF-005-S-PA
'''''''''''''''
Each of the modules uses protocol-buffers [#]_\. All proto-files create a reliable and robust way to support communication between instances of LV2 and LV3. A design of the communication follows a standard way of client-server queries. 

LV2 applications act as servers. They provide telemetry data. The applications can be also updated with data e.g. control commands.

LV3 applications act as clients. They query the servers and update them with control commands.

.. warning:: Provide a standardized client-server templates for protocol buffers.

LV3-GF-006-S-PA
'''''''''''''''
Any application will send commands to LV2 apps directly.

LV3-GF-007-S-PA
'''''''''''''''
A user can choose the way telemetric data will be retreived from the LV2:

    #. Continuous manner
            LV2 applications automatically schedules telemetry updates and sends it to the client.

    #. On demand
            LV3 applications or a user decide when to ask for telemetry data.

LV3-GF-008-S-PA
'''''''''''''''
Use Qt Gamepads to provide support for any plug&play input device. A module should be highly customizable and shared as a dynamically loaded library.


LV3-GF-009-S-PA
'''''''''''''''
Provide a dialog that allows a user to enter a new command-input pair. The dialog then stores modified values (re-writes the whole settings) and applies the values to the input engine.

LV3-GF-010-S-PA
'''''''''''''''
Any application should send and generate scripts unless requirements state differently. A set of scripting functionalities ought to be shared in a form of a dynamically loaded library.

A design of the library must take under consideration the following issues:
    * First command starts in time *0*
    * Any further commands are executed in time *0+time_started* and ended in time *0+time_ended*. The time is given in milliseconds
    * The scripting engine should register multiple inputs at the time.
    * There are no limits in terms of the form the scripting language should look like. It can be an off-the-shelf solution or a custom one that resembles COLOBOT [#]_\.
    * A set of registered commands should be handled with protobuf unless there is a good justification to do otherwise
    * The ouput file can be text or binary

Drive module - Project Assumptions
==================================

LV3-DM-001-SG-PA
''''''''''''''''
An application supports the following modes:

    * user-controlled
        A user controls the rover remotely or directly using input devices such as a gamepad. These mode is essential for any further development, thus must be completed and as reliable as possible.

    * scripting
        A user may create a script by hand or register the set of instruction while operating the in user-controlled mode.

    * autonomous
        A user loads a map and enters a set of checkpoints to be achieved. Then, these points are converted into a rover-friendly format and sent to the robot and dispatched there. Additional parameters may be required in further stages of development

LV3-DM-003-SG-PA
''''''''''''''''
An application displays telemetry data in neatly organized widgets created in QML.
Some of the important entries should be displayed in a form of list. Custom models prefered to supply these QML widgets with data.

LV3-DM-001-SW-PA
''''''''''''''''
An application supports scripting of the Drive Module.

The following commands should be present:
    * drive(DIRECTION::(FORWARD|BACKWARD), speed_angle_per_second)
    * turn(degrees)     // + value turn left, - value turn right
    * wait(milliseconds)
    * blink( (ON|OFF) ) // signalize the rover reached a desired destination
    * feedback          // 
  

.. rubric:: Reference documents

.. [#] https://developers.google.com/protocol-buffers/
.. [#] https://colobot.info/