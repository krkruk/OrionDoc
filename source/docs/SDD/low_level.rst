=================================
(LV1) Low level software design
=================================

Introduction
------------

This documents sets prerequisites for software development for any *uC* that is part of the rover.

*uC* identification
-------------------

Every single *uC* installed in the rover is required to publish an **ID**.

The following table defines possible ranges for each of sub-modules related to low level software:

+---+--------------------+----------+-------------------------------------------------------+
| # | Sub-module category| Range    | Description                                           |
+===+====================+==========+=======================================================+
| 1 | Drive module       | [0..31]  | These IDs are assigned to the drive module only.      |
+---+--------------------+----------+-------------------------------------------------------+
| 2 | Manipulator module | [32..63] | These IDs are assigned to the manipulator module only.|
+---+--------------------+----------+-------------------------------------------------------+
| 3 | Lab module         | [64..95] | These IDs are assigned to the lab module only.        |
+---+--------------------+----------+-------------------------------------------------------+
| 4 | Control Panel      | [96..100]| These IDs are assigned to the Control Panel module.   |
+---+--------------------+----------+-------------------------------------------------------+
| 5 | Miscellaneous      |[101..255]| Miscellaneous. This values can be used but one should |
|   |                    |          | reference higher levels of software first.            |
+---+--------------------+----------+-------------------------------------------------------+



JSON dictionaries
-----------------

.. note::
    ID code description:
        * LV? - software level e.g. LV2
        * MODULE - module code e.g DM
        * NNN - reference number
        * T - requirement type e.g. JSON - JSON Keys

    Key:
        * JSON key
    
    I/O:
        * IN - input
        * OUT - output
    
Drive module
############

The following values define full public API of the motor controllers.

+-----------------+------+------+-------------+----------------------------------------------------------+
| ID              | I/O  | Key  | Value range | Description                                              |
+=================+======+======+=============+==========================================================+
| LV1-DM-001-JSON | IN   | ROT  | [10, 200]   | Angular velocity in degrees/second [deg/s].              |
+-----------------+------+------+-------------+----------------------------------------------------------+
| LV1-DM-002-JSON | OUT  | ROT  | [10, 200]   | Angular velocity feedback in degrees/second [deg/s].     |
+-----------------+------+------+-------------+----------------------------------------------------------+
| LV1-DM-003-JSON | OUT  | TEMP | [0, 125]    | Temperature of the keying transistor in Centigrades [°C] |
+-----------------+------+------+-------------+----------------------------------------------------------+
| LV1-DM-004-JSON | OUT  | CUR  | [0, 20]     | Current usage in Amps [A].                               |
+-----------------+------+------+-------------+----------------------------------------------------------+
| LV1-DM-005-JSON | OUT  | PWM  | [0, 255]    | Current PWM in 8-bit value.                              |
+-----------------+------+------+-------------+----------------------------------------------------------+

Arm module
##########

The arm module description is here: :ref:`arm-controller-api-doc`.