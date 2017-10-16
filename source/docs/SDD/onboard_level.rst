====================================
(LV2) On-board level software design
====================================

Introduction
------------

This documents sets prerequisites for software development for any computer that is installed onboard.


Motivation
==========

On-board computers liaise between Earth-base station and *uC*\ s. Their main purpose is to decode commands received from the remote source and apply it to the specific microcontrollers.

Moreover, some of these computers may perform additional tasks. For instance, *Drive module* is expected to compute basic *SLAM* procedures in order to navigate autonomously.


System overview
---------------

An idea is to send a command from an Earth-base station wirelessly so that a robot responds and sends back feedback. The system comprises of the elements as *uC*\ s, on-board computers and Earth-base computers, which relates to the level\ *ish* software structure.

In general, a user enters a command from an Earth-base station. A command message is encoded and sent wirelessly. The message is then received by the rover placed in a remote location and decoded by one of the on-board computers. Then, the computer has to create an another message so it suits the API provided by the *uC*\ s. The message is sent to the *uC* and decoded there. Finally, a message pipeline results in an execution of the command.

The feedback data uses a very similar pipeline. One of the *uC*\ s create a message that is received by an on-board computer. The computer stores the most recent data into its memory. The feedback data can be sent periodically or requested by a remote client. In any case, the data is wrapped with protocol metadata and forwarded to the Earth-base computers.

.. note::
    Add a graphics related to the pipeline


System requirements
-------------------

Reference table
===============
.. note::
    ID code description:
        * LV? - software level e.g. LV2
        * MODULE - module code e.g DM
        * NNN - reference number
        * T - requirement type e.g. S - *S*\ oftware



+---------------+---------+-------------------------------------+------------+
| #             | Priority| Description                         | Basis      |
+===============+=========+=====================================+============+
| **General Feature**                                                        |
+---------------+---------+-------------------------------------+------------+
| LV2-GF-001-S  | HIGH    | Provide reliable wireless connection|            |
|               |         | using TCP/IP stack                  |            |
+---------------+---------+-------------------------------------+------------+
| LV2-GF-002-S  | HIGH    | Support Serial Port                 |            |
+---------------+---------+-------------------------------------+------------+
| LV2-GF-003-S  | HIGH    | Discover ID of the *uC*             |            |
+---------------+---------+-------------------------------------+------------+
| LV2-GF-004-S_ | HIGH    | Provide on-board telemetry logging  |            |
|               |         | system based on SQLite              |            |
+---------------+---------+-------------------------------------+------------+


Description of selected requirements
====================================

This sections handles requirements that cannot be fully described in a reference table. Each of the following subsections comprises of the *ID code* and a concise description.

LV2-GF-004-S
++++++++++++
The logging system is a universal system to store sensor data on-board. It is required to provide following features:
    #. Store any key-value pair in a database with a timestamp    
    #. Secure the database against unexpected power loss (only last second of data logging can be lost)    
    #. Provide a separate dynamically loaded library for reusability
    #. Provide easy to use lookup methods
    #. Provide a simple database viewer for the Earth-base station
    #. Trololololol1
