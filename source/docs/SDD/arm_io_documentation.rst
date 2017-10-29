:orphan:

.. _arm-controller-api-doc:

========================
Orion Arm Controller API
========================

The following defines full public API for the arm controller.

Primary arm controller has **ID** equal 32. This key should exist in every sent and received JSON object.

+-----------------+---------+------+-------------+---------------------------------------------------+
| ID              | I/O     | Key  | Value range | Description                                       |
+=================+=========+======+=============+===================================================+
| LV1-MM-001-JSON | IN/OUT  | ID   | 32          | ID of primary arm controller                      |
+-----------------+---------+------+-------------+---------------------------------------------------+

.. note::
    JSON object with **ID** key will be sent periodically after bootup, until arm controller will receive first command.

Arm has control modes. **MODE** key value describes the **DATA** key structure in both input and output JSON's.

+-----------------+--------+------+-------------+----------------------+
| ID              | I/O    | Key  | Value range | Description          |
+=================+========+======+=============+======================+
| LV1-MM-002-JSON | IN/OUT | MODE | [0, 2]      | Arm controller mode  |
+-----------------+--------+------+-------------+----------------------+
| LV1-MM-003-JSON | IN/OUT | DATA | N/A         | The data             |
+-----------------+--------+------+-------------+----------------------+

Controller input
================

Modes list
~~~~~~~~~~

+---------+---------------------+
| Mode ID | Description         |
+=========+=====================+
| 0       | Invalid mode        |
+---------+---------------------+
| 1       | Direct control mode |
+---------+---------------------+
| 2       | Command mode        |
+---------+---------------------+

In *direct control mode* the **DATA** should be an object containing the data for arm motors.

In *command mode* the **DATA** should be an integer (*note: this can change to an object at some point*) with command number.

Direct control mode data
~~~~~~~~~~~~~~~~~~~~~~~~

The **DATA** key value in direct control mode should be an object containing keys described below.

.. note::
    Values out of bounds will be treated like marginal values (e.g if we will send -1000 value, and minimal value will be -400, the value will be set to -400).

.. tip::
    Sending only the changed inputs is recommended, to shorten data parsing, because the controller will remember the last state of a motor.

+-----------------+------+-----+-------------+---------------------------------------------------------------------------+
| ID              | I/O  | Key | Value range | Description                                                               |
+=================+======+=====+=============+===========================================================================+
| LV1-MM-101-JSON | IN   | TRM | [-400, 400] | Turntable motor speed, positive value mean clockwise movement             |
+-----------------+------+-----+-------------+---------------------------------------------------------------------------+
| LV1-MM-102-JSON | IN   | LAA | [-1, 1]     | Lower arm actuator, negative value means retraction                       |
+-----------------+------+-----+-------------+---------------------------------------------------------------------------+
| LV1-MM-103-JSON | IN   | UAA | [-1, 1]     | Upper arm actuator, negative value means retraction                       |
+-----------------+------+-----+-------------+---------------------------------------------------------------------------+
| LV1-MM-104-JSON | IN   | AEM | [-400, 400] | Arm extending motor speed, positive value mean expansion                  |
+-----------------+------+-----+-------------+---------------------------------------------------------------------------+
| LV1-MM-105-JSON | IN   | GVM | [-400, 400] | Grasper vertical movement motor speed, positive value mean "move up"      |
+-----------------+------+-----+-------------+---------------------------------------------------------------------------+
| LV1-MM-106-JSON | IN   | GRM | [-400, 400] | Grasper rotation motor speed, positive value mean clockwise movement      |
+-----------------+------+-----+-------------+---------------------------------------------------------------------------+
| LV1-MM-107-JSON | IN   | GHS | [-180, 180] | Grasper horizontal servo position [deg], positive value mean "move right" |
+-----------------+------+-----+-------------+---------------------------------------------------------------------------+

Command mode data
~~~~~~~~~~~~~~~~~

To invoke a command, send command mode ID as **MODE** and command ID as **DATA**. Arm has the following commands available:

+----+-----------------------------------------+
| ID | Description                             |
+====+=========================================+
| 0  | Invalid command                         |
+----+-----------------------------------------+
| 1  | Stop the arm movement                   |
+----+-----------------------------------------+
| 2  | Completely fold the arm (for transport) |
+----+-----------------------------------------+
| 3  | Unfold the arm to default position      |
+----+-----------------------------------------+

Arm output (feedback)
=====================

Arm feedback depends from last command's mode.

Direct control mode
~~~~~~~~~~~~~~~~~~~

In direct control mode, the feedback will be sent after execution of every received incoming JSON.

.. note::
    This behaviour will probably be changed after first tests.
    Potential updated behaviour will send feedback on-demand and/or periodically
    
    Reason: Sending the feedback every time data is sent is inefficient, and potentially does not give more data than sending feedback periodically or on-demand. This is a temporary solution.

The returned JSON object will contain **ID** key, and following data

+-----------------+------+------+----------------+-----------------------------------------------+
| ID              | I/O  | Key  | Value range    | Description                                   |
+=================+======+======+================+===============================================+
| LV1-MM-201-JSON | OUT  | TRMF | Motor feedback | Feedback of the turntable motor               |
+-----------------+------+------+----------------+-----------------------------------------------+
| LV1-MM-202-JSON | OUT  | LAAF | Motor feedback | Feedback of the lower arm actuator            |
+-----------------+------+------+----------------+-----------------------------------------------+
| LV1-MM-203-JSON | OUT  | UAAF | Motor feedback | Feedback of the upper arm actuator            |
+-----------------+------+------+----------------+-----------------------------------------------+
| LV1-MM-204-JSON | OUT  | AEMF | Motor feedback | Feedback of the arm extending motor           |
+-----------------+------+------+----------------+-----------------------------------------------+
| LV1-MM-205-JSON | OUT  | GVMF | Motor feedback | Feedback of the grasper vertical motor        |
+-----------------+------+------+----------------+-----------------------------------------------+
| LV1-MM-206-JSON | OUT  | GRMF | Motor feedback | Feedback of the grasper rotation motor        |
+-----------------+------+------+----------------+-----------------------------------------------+
| LV1-MM-207-JSON | OUT  | GHSF | Motor feedback | Feedback of the grasper horizontal servomotor |
+-----------------+------+------+----------------+-----------------------------------------------+

*Motor feedback* is an JSON array, containing three elements

+-------+----------------------------------+
| Index | Element description              |
+=======+==================================+
| 0     | Actual speed/direction/position  |
+-------+----------------------------------+
| 1     | Actual current draw              |
+-------+----------------------------------+
| 2     | Error flag                       |
+-------+----------------------------------+

.. note::
    This could potentially be reworked to JSON object with keys, but - since performance may be an issue - for now, it will be an array

Command mode
~~~~~~~~~~~~

In command mode, feedback will be sent **only after executing the command**.

.. note::
    As described above, this behaviour will probably be changed to allow on-demand/periodical feedback

For now, there is no way to stop command execution

.. note::
    But, in the future, there will be - execution will be terminated after receiving *ID 1* (Stop the arm movement) command. TODO.

Feedback will contain **ID** key, and flag

+-----------------+------+------+-------------+--------------------------------------------------------+
| ID              | I/O  | Key  | Value range | Description                                            |
+=================+======+======+=============+========================================================+
| LV1-MM-301-JSON | OUT  | CMDF | [0, 1]      | 0 if command failed, 1 if command executed sucessfully |
+-----------------+------+------+-------------+--------------------------------------------------------+


Examples
========

.. note::
    Electric current values in example feedback is not the real current draw; it's just an example

**Bootup JSON sent by arm**

Output:

.. sourcecode:: json

    {
        "ID": 32
    }

**Setting the turret speed to 200 and extending the arm (with both actuators and extending motor)**

Input:

.. sourcecode:: json

    {
        "ID": 32,
	    "MODE": 1,
	    "DATA": {
		    "TRM": 200,
		    "LAA": 1,
		    "UAA": 1,
		    "AEM": 400
	    }
    }

Output:

.. sourcecode:: json

    {
        "ID": 32,
        "MODE": 1,
        "DATA": {
            "TRM": [200, 65, 0],
            "LAA": [1, 50, 0],
            "UAA": [1, 45, 0],
            "AEM": [400, 35, 0]
        }
    }

**Sending "unfold the arm" command**

Input:

.. sourcecode:: json

    {
        "ID": 32,
        "MODE": 2,
        "DATA": 3
    }

Output:

.. sourcecode:: json

    {
        "ID": 32,
        "MODE": 2,
        "DATA": {
            "CMDF": 1
        }
    }