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



+----------------+---------+-------------------------------------------+------------+
| #              | Priority| Description                               | Basis      |
+================+=========+===========================================+============+
| `General Feature`_                                                                |
+----------------+---------+-------------------------------------------+------------+
| LV3-GF-001-S_  | HIGH    | Code reusability for LV2 and LV3          |            |
+----------------+---------+-------------------------------------------+------------+
| LV3-GF-002-S_  | HIGH    | Unit testing a key part of design         |            |
+----------------+---------+-------------------------------------------+------------+
| LV3-GF-003-S_  | HIGH    | Logging to database                       |            |
+----------------+---------+-------------------------------------------+------------+
| `Drive module`_                                                                   |
+----------------+---------+-------------------------------------------+------------+
| LV3-DM-001-SD_ | HIGH    | Connect to the device                     |            |
+----------------+---------+-------------------------------------------+------------+
| LV3-DM-002-SD_ | HIGH    | List available sensors                    |            |
+----------------+---------+-------------------------------------------+------------+
| LV3-DM-003-SD_ | HIGH    | Display sensor values in widgets          |            |
+----------------+---------+-------------------------------------------+------------+



General Feature
===============

LV3-GF-001-S
''''''''''''
The code must be maximally reusable. Separation of the hardcore back-end and the front-end is a must. The back-end part must be done in a way it is fairly easy to combine it with LV2 and/or LV3.

LV3-GF-002-S
''''''''''''
An API of any class must be explicitly described by a unit test. Program-related logic and other functionalies must be design in a way it is testable and verifyable. Preferably, the developer designs a valid interface so a mock objects can be created.

LV3-GF-003-S
''''''''''''
Each of the applications should provide a logging funtionality. A detailed description can be found in LV2-GF-004-S. An application may assume all received data is needed to be stored.


Drive module
============

.. note::
    * SD - Software, Direct (connection)
    * SW - Software, Wireless (connection)

LV3-DM-001-SD
'''''''''''''
Discover an ID of the device and connect to it.

LV3-DM-002-SD
'''''''''''''
Lists all available sensors provided by the platform.

LV3-DM-003-SD
'''''''''''''
Create a widget for all sensors listed in LV3-DM-002-SD_. The widget must be interactive and beautiful to look at. See more as a gage rather than a standard text label. The widgets must be placed in a proper positions so it simulates their real placement in the rover. See Hardware Design Document for more details.
