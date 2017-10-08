===============================
Software Design Document
===============================

Introduction
------------

Software in any robotic project is probably the most important part. It defines the way the rover *is* and works.

There are three levels of software required for the project.

#. Low level software - (LV1)
    The software developed in this level interacts with the hardware directly. This also includes implementation of controllers such as *PID*. The software publishes an API that allows controlling the harware and receive feedback.
#. On-board level software - (LV2)
    The software developed in this level is responsible for interaction between the ob-board hardware and an Earth-base computers. It translates commands send from Earth and forwards it to the microcontrollers. Moreover, it handles high level tasks such as inverse kinematics and computer vision.
#. Earth-base level software - (LV3)
    The software developed in this level takes direct input from the user. It receives control commands, packs it into a datagrams (or any format) and sends it to the rover. It also displays feedback data sent by the robot.


Modules
-------
Whenever the text references to one of the following modules the module is meant as:
    
    Drive module (DM)
        hardware and software that allows the robot to move. It includes software, uCs, on-board computers, cameras etc.
        
    Manipulator module (MM)
        hardware and software that allows the robot to grasp objects, dig etc. Think of as a human arm and hand. It includes software, uCs, on-board computers, cameras etc.
        
    Lab module (LM)
        hardware and software that allows the robot to perform various scientific tests. It includes software, cameras, sensors etc.
        
    General feature (GF)
        hardware or software feature that is related to at least 2 of the modules.
        
    Miscellaneous (MISC)    
        hardware and software that cannot be categorized into one of the previous modules. It includes mostly experimental features that are attached *ad hoc*.


Levels
------

.. toctree::
    :maxdepth: 2
    
    low_level
    onboard_level
    earthbase_level

Glossary
--------

.. glossary::

    uC
        a microcontroller, a computer within a single integrated circuit
        
    ID
        ID is a unique number, integer, hardcoded in the *uC* that allows identifying the device and assign a role to it.

    SLAM
        Simulataneous Locationing and Mapping
        
