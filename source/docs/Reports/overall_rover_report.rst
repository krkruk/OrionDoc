======================================
Overall Rover Report
======================================

Technical requirements
-----------------------

General
********

+------------+---------------------------------------------+----------------------------+
| #ID        | Description                                 | Justification              |
+============+=============================================+============================+
| TR-G-0001  | Provide a standalone, mobile platform       | Rules/General requirements |
+------------+---------------------------------------------+----------------------------+
| TR-G-0002  | Do not exceed 50kg mass per Task            | Rules/System weight        |
+------------+---------------------------------------------+----------------------------+
| TR-G-0003  | Do not exceed 0.5m/s (1.8km/h) max velocity | Rules/Rover control and op.|
+------------+---------------------------------------------+----------------------------+
| TR-G-0004  |                                             |                            |
+------------+---------------------------------------------+----------------------------+
| TR-G-0005  | Provide >=100m operational range            | Rules/Rover control and op.|
+------------+---------------------------------------------+----------------------------+
| TR-G-0006  | Provide >=20m of tether at ground control   | Rules/Rover control and op.|
+------------+---------------------------------------------+----------------------------+
| TR-G-0007  | Sustain temperature in range [+10..+30]°C   | Rules/Rover control and op.|
+------------+---------------------------------------------+----------------------------+
| TR-G-0008  | Provide at least 1 physical emergency button| Rules/Emergency stop       |
+------------+---------------------------------------------+----------------------------+
| TR-G-0009  | Provide an off-the-shelf red, stop button   | Rules/Emergency stop       |
+------------+---------------------------------------------+----------------------------+
| TR-G-0010  | Stop button withstands hard hit by hand     | Rules/Emergency stop       |
+------------+---------------------------------------------+----------------------------+
| TR-G-0011  | Stop button disconnects batteries from      | Rules/Emergency stop       |
|            | the rover                                   |                            |
+------------+---------------------------------------------+----------------------------+
| TR-G-0012  | Avoid remote killing of the rover           | Rules/Emergency stop       |
+------------+---------------------------------------------+----------------------------+
| TR-G-0013  | Provide an activity indicator: a lamp       | Rules/Activity indicator   |
+------------+---------------------------------------------+----------------------------+
| TR-G-0014  | Activity indicator is visible at >10m       | Rules/Activity indicator   |
|            | distance                                    |                            |
+------------+---------------------------------------------+----------------------------+
| TR-G-0015  | Introduce >5s delay before execution of any | Rules/Activity indicator   |
|            | operation. Light activity indicator         |                            |
+------------+---------------------------------------------+----------------------------+
| TR-G-0015  | Activate the activity indicator when the    | Rules/Activity indicator   |
|            | rover is ready to move (any of its part)    |                            |
+------------+---------------------------------------------+----------------------------+
| TR-G-0017  | Provide wireless standard one of: Radio     | Rules/Comm. requirements   |
|            | Amateur bands, WiFi (2.4, 5GHz), ISM        |                            |
+------------+---------------------------------------------+----------------------------+
| TR-G-0018  | Wireless comm. shall comply with power and  | Rules/Comm. requirements   |
|            | frequency requirements according to the     |                            |
|            | Rules and Polish law                        |                            |
+------------+---------------------------------------------+----------------------------+
| TR-G-0019  | Provide Radio Frequency Form                | Rules/Comm. requirements   |
+------------+---------------------------------------------+----------------------------+
| TR-G-0020  | Provide RF Spectrum measurements            | Rules/Comm. requirements   |
+------------+---------------------------------------------+----------------------------+


Autonomy predicates
*******************

+------------+---------------------------------------------+----------------------------+
| #ID        | Description                                 | Justification              |
+============+=============================================+============================+
| TR-AI-001  | Provide automation for extra scoring for    | Rules/Rover autonomy       |
|            | all tasks                                   |                            |
+------------+---------------------------------------------+----------------------------+
| TR-AI-002  | Implement (at least) the following set      | Rules/Rover autonomy       |
|            | commands: *start, working, wait, waiting,*  |                            |
|            | *resume, stop*                              |                            |
+------------+---------------------------------------------+----------------------------+
| TR-AI-002/1| Extend the set of commands defined in       | Rules/Rover autonomy       |
|            | TR-AI-002 if required.                      |                            |
+------------+---------------------------------------------+----------------------------+
| TR-AI-002/2| Sending any other command but one defined   | Rules/Rover autonomy       |
|            | in TR-AI-002 is prohibited                  |                            |
+------------+---------------------------------------------+----------------------------+
| TR-AI-003  | Provide telemetry                           | Rules/Rover autonomy       |
+------------+---------------------------------------------+----------------------------+
| TR-AI-003/1| Record telemetry data to allow open access  | Rules/Rover autonomy       |
|            | sharing                                     |                            |
+------------+---------------------------------------------+----------------------------+
| TR-AI-004  | Provide compliance with safety precautions  | Rules/Rover autonomy       |
|            | defined in `General`_                       |                            |
+------------+---------------------------------------------+----------------------------+
| TR-AI-004/1| Delay >5s any autonomous command execution  | Rules/Automatic functional.|
+------------+---------------------------------------------+----------------------------+
| TR-AI-004/2| Avoid immediate and rapid movements         | Rules/Automatic functional.|
+------------+---------------------------------------------+----------------------------+





Field Trials
************

+-------------+---------------------------------------------+-------------------------------+
| #ID         | Description                                 | Justification                 |
+=============+=============================================+===============================+
| TR-FT-0001  | Ensure the rover is safe to the surroundings| Rules/Field trials/General-a  |
+-------------+---------------------------------------------+-------------------------------+
| TR-FT-0002  | Provide (optionally) a modular rover design | Rules/Field trials/General-b  |
+-------------+---------------------------------------------+-------------------------------+
| TR-FT-0003  | Provide compliance with technological       | Rules/Field trials/General-d  |
|             | priorities according to the task description|                               |
+-------------+---------------------------------------------+-------------------------------+
| TR-FT-0004  | Ensure the rover and operators perform      | Rules/Field trials/General-f  |
|             | at utmost capabilities                      |                               |
+-------------+---------------------------------------------+-------------------------------+
| TR-FT-0005  | Ensure a ground control operator is well    | Rules/Field trials/General-f:g|
|             | trained                                     |                               |
+-------------+---------------------------------------------+-------------------------------+
| TR-FT-0006  | Ensure the rover can operate both indoor    | Rules/F.T/Challenge site d.-a |
|             | and outdoor                                 |                               |
+-------------+---------------------------------------------+-------------------------------+
| TR-FT-0007  | Sustain the following weather conditions    | Rules/F.T/Challenge site d.-b | 
|             | (outdoors):                                 |                               |
|             |                                             |                               |
|             |  * temperature: [15..30]°C                  |                               |
|             |  * wind: moderate gusts                     |                               |
|             |  * rain: drizzle                            |                               |
|             |  * insolation: [weak..string] sunlight      |                               |
+-------------+---------------------------------------------+-------------------------------+
| TR-FT-0008  | The rover traverses multiple types of       | Rules/Challenge site details-b|
|             | surface: sandy, non-cohesive sold; hard     |                               |
|             | terrain; industrial surface (e.g. concrete) |                               |
+-------------+---------------------------------------------+-------------------------------+
| TR-FT-0009  | The rover is capable of fulfilling tasks    | Rules/F.T/Operations-a        | 
+-------------+---------------------------------------------+-------------------------------+
| TR-FT-0010  | The rover is immune to initial conditions   | Rules/F.T/Operations-b        | 
|             | of the task (e.g. heading, position)        |                               |
+-------------+---------------------------------------------+-------------------------------+
| TR-FT-0011  | The rover completes the task within 25min.  | Rules/F.T/Operations-d        |
+-------------+---------------------------------------------+-------------------------------+
| TR-FT-0012  | The video can be streamed unless the        | Rules/F.T/Operations-h        |
|             | requirements state differently              |                               |
+-------------+---------------------------------------------+-------------------------------+
| TR-FT-0013  | The rover does not interfere with systems of| Rules/F.T/Operations-k        |
|             | other teams                                 |                               |
+-------------+---------------------------------------------+-------------------------------+

Science task 
************

+------------+---------------------------------------------+----------------------------+
| #ID        | Description                                 | Justification              |
+============+=============================================+============================+
| TR-ST-001  | Technological priorities:                   | Rules/Science task         |
|            |                                             |                            |
|            |  * drilling                                 |                            |
|            |  * sample caching                           |                            |
|            |  * in-situ sample analysis/processing       |                            |
|            |  * scooping                                 |                            |
+------------+---------------------------------------------+----------------------------+
| TR-ST-002  | Reach sampling areas accurately             | Rules/S.T/Task-a)          |
+------------+---------------------------------------------+----------------------------+
| TR-ST-003  | Provide a set of sealed containers          | Rules/S.T/Gen. req./f:g)   |
+------------+---------------------------------------------+----------------------------+
| TR-ST-003/1| Design a container to maximally meet sample | Rules/S.T/Gen. req./i)     |
|            | caching requirements                        |                            |
+------------+---------------------------------------------+----------------------------+
| TR-ST-003/2| Provide insertion method that meets the best| Rules/S.T/Gen. req./i)     |
|            | caching requirements                        |                            |
+------------+---------------------------------------------+----------------------------+
| TR-ST-003/3| Provide storing conditions similar to       | Rules/S.T/description      |
|            | environmental ones                          |                            |
+------------+---------------------------------------------+----------------------------+
| TR-ST-003/4| Isolate a sample from changing environment  | Rules/S.T/description      |
|            | conditions                                  |                            |
+------------+---------------------------------------------+----------------------------+
| TR-ST-003/5| Preserve a sample from cross-contamination  | Rules/S.T/description      |
+------------+---------------------------------------------+----------------------------+
| TR-ST-004  | Cache subsurface sample                     | Rules/S.T/Task-b)          |
+------------+---------------------------------------------+----------------------------+
| TR-ST-004/1| Drill a sample in a material of varying     | Rules/S.T/Gen. req./c)     |
|            | hardness (from loose soil to gypsum)        |                            |
+------------+---------------------------------------------+----------------------------+
| TR-ST-004/2| Drill a sample from the surface to the      | Rules/S.T/Exp.results/a.2  |
|            | possibly deepest reaching point             |                            |
+------------+---------------------------------------------+----------------------------+
| TR-ST-004/3| Provide an unmixed, undisturbed sample      | Rules/S.T/Gen. req./c)     |
|            | with visible layer structure                |                            |
+------------+---------------------------------------------+----------------------------+
| TR-ST-004/4| Store freshly drilled specimen into         | Rules/S.T/Add. info/f)     |
|            | a container                                 |                            |
+------------+---------------------------------------------+----------------------------+
| TR-ST-004/5| Isolate the deep sample from above-surface  | Rules/S.T./Add. info/g)    |
|            | condition when leaving the excavation area  |                            |
+------------+---------------------------------------------+----------------------------+
| TR-ST-005  | Cache surface sample                        | Rules/S.T/Task-b)          |
+------------+---------------------------------------------+----------------------------+
| TR-ST-005/1| Sample multiple types of loose soil         | Rules/S.T/Gen. req./b)     |
+------------+---------------------------------------------+----------------------------+
| TR-ST-005/2| Sample is stored in a sealed container      | TR-ST-0003                 |
+------------+---------------------------------------------+----------------------------+
| TR-ST-006  | Prepare photographic documentation of       | Rules/S.T/Task-c)          |
|            |                                             |                            |
|            |  * sampling area                            |                            |
|            |  * sample                                   |                            |
+------------+---------------------------------------------+----------------------------+
| TR-ST-006/1| Capture quality photographic documentation  | Rules/S.T/Gen. req./j)     |
|            | in min. 800x600px resolution                |                            |
+------------+---------------------------------------------+----------------------------+
| TR-ST-006/2| Capture an image so the specimen occupies   | Rules/S.T/Gen. req./j)     |
|            | the major part of the image                 |                            |
+------------+---------------------------------------------+----------------------------+
| TR-ST-006/3| Provide different perspectives of the sample| Rules/S.T/Exp.results/c    |
|            | and the area                                |                            |
+------------+---------------------------------------------+----------------------------+
| TR-ST-006/4| Store the photographic documentation at     | Rules/S.T/Gen. req./k)     | 
|            | the ground control facility                 |                            |
+------------+---------------------------------------------+----------------------------+
| TR-ST-007  | Provide in-situ measurements                | Rules/S.T/Exp.results/b    |
+------------+---------------------------------------------+----------------------------+
| TR-ST-007/1| Provide automatic measurement acquisition   | Rules/S.T/Exp.results/b    |
+------------+---------------------------------------------+----------------------------+
| TR-ST-007/2| Provide permanent storage of received data  | Rules/S.T/Gen. req./k)     | 
+------------+---------------------------------------------+----------------------------+
| TR-ST-008  | Sample at least 25g of specimen (50-100g    | Rules/S.T/Expected Results |
|            | preferable)                                 |                            |
+------------+---------------------------------------------+----------------------------+
| TR-ST-009  | Dig a trench: min. 30cm length, 5cm deep    | Rules/S.T/Gen. req./j)     |
+------------+---------------------------------------------+----------------------------+
| TR-ST-009/1| Present a layered structure of soil in the  | Rules/S.T/Gen. req./j)     |
|            | dug trench                                  |                            |
+------------+---------------------------------------------+----------------------------+
| TR-ST-009/2| Provide a photographic documentation        | TR-ST-0006                 |
+------------+---------------------------------------------+----------------------------+
| TR-ST-010  | Mitigate reaction forces to the rover body  | Rules/S.T/Gen. req/m)      |
+------------+---------------------------------------------+----------------------------+

Maintenance task
*****************

+------------+---------------------------------------------+----------------------------+
| #ID        | Description                                 | Justification              |
+============+=============================================+============================+
| TR-MT-001  | Technological priorities:                   | Rules/Maintenance task     |
|            |                                             |                            |
|            |  * tele-operation                           |                            |
|            |  * task automation                          |                            |
|            |  * end-effector                             |                            |
|            |  * manipulator performance                  |                            |
+------------+---------------------------------------------+----------------------------+
| TR-MT-002  | Reach a destination                         | Rules/M.T/Task Scen./1)    |
+------------+---------------------------------------------+----------------------------+
| TR-MT-003  | Operate controls at height [0.2..1.5]m      | Rules/M.T/Gen. req./d)     |
|            | above the ground level                      |                            |
+------------+---------------------------------------------+----------------------------+
| TR-MT-003/1| Provide intuitive and ergonomic UI          | Rules/M.T/Description      |
|            | at ground control                           |                            |
+------------+---------------------------------------------+----------------------------+
| TR-MT-003/2| Provide immersive tele-operator interface   | Rules/M.T/Description      |
+------------+---------------------------------------------+----------------------------+
| TR-MT-003/3| Provide a set of sensors to build spatial   | Rules/M.T/Description      |
|            | awareness to the user                       |                            |
+------------+---------------------------------------------+----------------------------+
| TR-MT-003/4| Provide manipulator force feedback data     | Rules/M.T/Description      |
+------------+---------------------------------------------+----------------------------+
| TR-MT-003/5| Detect AR/QR tags and measure distance      | Rules/M.T/Add. info/2)     |
|            | between each of them                        |                            |
+------------+---------------------------------------------+----------------------------+
| TR-MT-003/6| Uncover MLI-like materials (Multi-Layer     | Rules/M.T/Gen. req./k)     |
|            | Insulation) e.g. Velcro without damaging it |                            |
+------------+---------------------------------------------+----------------------------+
| TR-MT-003/7| Provide a set of tools adequate for the task| Rules/M.T/Tech. Prior./3a) |
+------------+---------------------------------------------+----------------------------+
| TR-MT-004  | Set state of switches                       | Rules/M.T/Task Scen./1a)   |
+------------+---------------------------------------------+----------------------------+
| TR-MT-004/1| Operate on industrial grade elements        | Rules/M.T/Gen. req./b)     |
+------------+---------------------------------------------+----------------------------+
| TR-MT-004/2| Switch a lever switch                       | Rules/M.T/Gen. req./c)     |
+------------+---------------------------------------------+----------------------------+
| TR-MT-004/3| Rotate a knob                               | Rules/M.T/Gen. req./c)     |
+------------+---------------------------------------------+----------------------------+
| TR-MT-005  | Set value with a knob                       | Rules/M.T/Task Scen./2b)   |
+------------+---------------------------------------------+----------------------------+
| TR-MT-005/1| Provide a camera that is capable of reading | Rules/M.T/Gen. req./h)     |
|            | a value from the display in distance <15cm  |                            |
|            | from the knob                               |                            |
+------------+---------------------------------------------+----------------------------+
| TR-MT-006  | Measure voltage                             | Rules/M.T/Task Scen./1b)   |
+------------+---------------------------------------------+----------------------------+
| TR-MT-006/1| Voltage range: [1.0.. 24.0] VDC             | Rules/M.T/Gen. req./f)     |
+------------+---------------------------------------------+----------------------------+
| TR-MT-006/2| Measurement accuracy: 0.5 VDC               | Rules/M.T/Gen. req./g)     |
+------------+---------------------------------------------+----------------------------+
| TR-MT-006/3| Slot shape: German type F plugs and sockets | Rules/M.T/Gen. req./e)     |
+------------+---------------------------------------------+----------------------------+
| TR-MT-007  | Grasp a high-power plug and plug it         | Rules/M.T/Task Scen./3)    | 
+------------+---------------------------------------------+----------------------------+
| TR-MT-007/1| Handle IEC 60309 plug with max.10cm diameter| Rules/M.T/Gen. req./i)     |
+------------+---------------------------------------------+----------------------------+
| TR-MT-008  | **PREVENT FROM DAMAGING ANY OBJECT!**       | Rules/M.T/Exp. results/d)  |
+------------+---------------------------------------------+----------------------------+
| TR-MT-009  | Implement task automation                   | Rules/M.T/Description      |
+------------+---------------------------------------------+----------------------------+
| TR-MT-009/1| Detect spacial parameters                   | Rules/M.T/Tech. Prior./2a) |
+------------+---------------------------------------------+----------------------------+
| TR-MT-009/2| Suggest an action for the detected element  | Rules/M.T/Tech. Prior./2a) |
|            | (e.g. toggle button switch)                 |                            |
+------------+---------------------------------------------+----------------------------+
| TR-MT-009/3| Provide data (images, numerics) of detected | Rules/M.T/Add. info/3a)    | 
|            | parameters (e.g. distance from button,      |                            |
|            | desired action etc.)                        |                            |
+------------+---------------------------------------------+----------------------------+ 
| TR-MT-009/4| Store, track, recover telemetry data with   | Rules/M.T/Add. info/3a:c)  |
|            | spacial parameters                          |                            |
+------------+---------------------------------------------+----------------------------+
| TR-MT-009/5| Provide automatic approach to the element   | Rules/M.T/Add. info/3d)    |
|            | and return to the idle state (min. 20cm from|                            |
|            | the panel surface)                          |                            |
+------------+---------------------------------------------+----------------------------+


Collection Task
++++++++++++++++

The Collection Task is a simulation of the Sample Fetching Rover (SFR). The concept is to provide two types of rovers. One is a mobile laboratory platform that collects a sample and places it into a container. The other rover is a seek-and-pick vehicle that collects containers and delivers them to the on-Mars laboratory or to the Mars Earth Return Vehicle (MERV). The task handles the latter case.

+------------+---------------------------------------------+----------------------------+
| #ID        | Description                                 | Justification              |
+============+=============================================+============================+
| TR-CT-001  | Technological priorities:                   | Rules/Collection task      |
|            |                                             |                            |
|            |  * task automation                          |                            |
|            |  * end-effector performance                 |                            |
|            |  * container and cache design               |                            |
|            |  * manipulator performance                  |                            |
+------------+---------------------------------------------+----------------------------+
| TR-CT-002  | Reach destination of the cache              | Rules/C.T/Task Scen./a)-a  |
+------------+---------------------------------------------+----------------------------+
| TR-CT-003  | Provide a manipulation device that is able  | Rules/C.T/General req./b)  |
|            | to pick up a cache and place it into the    |                            |
|            | container                                   |                            |
+------------+---------------------------------------------+----------------------------+
| TR-CT-003/1| Adjust accuracy and performance of the      | Rules/C.T/Tech. prior./4a:b|
|            | manipulator according to the task           |                            |
|            | requirements                                |                            |
+------------+---------------------------------------------+----------------------------+
| TR-CT-003/2| Dig out/pull a partially buried cache       | Rules/C.T/Add. info/a)     |
+------------+---------------------------------------------+----------------------------+
| TR-CT-004  | Design a container for caches               | Rules/C.T/General req./b)  |
+------------+---------------------------------------------+----------------------------+
| TR-CT-004/1| Provide at least 4 slots for caches         | Rules/C.T/General req./e)  |
+------------+---------------------------------------------+----------------------------+
| TR-CT-004/2| Immobilize a cache when placed in slot      | Rules/C.T/General req./d)  |
+------------+---------------------------------------------+----------------------------+
| TR-CT-004/3| Store a cache in vertical position          | Rules/C.T/General req./d)  |
+------------+---------------------------------------------+----------------------------+
| TR-CT-004/4| Design a slot based on a geometry of the    | Rules/C.T/General req./f)  |
|            | cache (p.20 of the Rules)                   |                            |
+------------+---------------------------------------------+----------------------------+
| TR-CT-004/5| Detach a container when needed              | Rules/C.T/General req./b)  |
+------------+---------------------------------------------+----------------------------+
| TR-CT-004/6| Facilitate placing the cache into the       | Rules/C.T/Tech. prior./3)-a|
|            | container taking into account limited       |                            |
|            | accuracy of the manipulator and             |                            | 
|            | environmental conditions                    |                            |
+------------+---------------------------------------------+----------------------------+
| TR-CT-005  | Provide task automation                     | Rules/C.T/Tech. prior./1)  |
+------------+---------------------------------------------+----------------------------+
| TR-CT-005/1| Detect and localize a cache                 | Rules/C.T/Tech. prior./1)-a|
+------------+---------------------------------------------+----------------------------+
| TR-CT-005/2| Approach to the cache automatically         | Rules/C.T/Tech. prior./1)-b|
+------------+---------------------------------------------+----------------------------+
| TR-CT-005/3| Pick up the cache automatically             | Rules/C.T/Tech. prior./1)-c|
+------------+---------------------------------------------+----------------------------+
| TR-CT-005/4| Place the cache into a container            | Rules/C.T/Description      |
+------------+---------------------------------------------+----------------------------+
| TR-CT-005/5| Detect a partially buried cache             | Rules/C.T/Add. info/b)     |
+------------+---------------------------------------------+----------------------------+
| TR-CT-006  | Prepare photographic documentation of the   | Rules/C.T/Task Scen./a)-c  |
|            | cache location                              |                            |
+------------+---------------------------------------------+----------------------------+
| TR-CT-007  | Detach and place at a desired location      | Rules/C.T/Task Scen./a:b)  |
+------------+---------------------------------------------+----------------------------+


Traverse task
+++++++++++++

.. note::

    Any autonomous task, especially the traverse task, is highly demanding and of high risk. An iterative approach is suggested.

+------------+---------------------------------------------+----------------------------+
| #ID        | Description                                 | Justification              |
+============+=============================================+============================+
| TR-TT-001  | Provide compliance with                     | Rules/T.T/General req./a)  |
|            | `Autonomy predicates`_                      |                            |
+------------+---------------------------------------------+----------------------------+
| TR-TT-002  | Navigate thru terrain without visuals at    | Rules/T.T/Description      |
|            | the ground control                          |                            |
+------------+---------------------------------------------+----------------------------+
| TR-TT-002/1| Provide step-by-step approach:              | Rules/T.T/Description      |
|            |                                             |                            |
|            |  * navigate blindly with an operator in     |                            |
|            |    a control loop                           |                            |
|            |  * eliminate the operator from the control  |                            |
|            |    loop                                     |                            |
+------------+---------------------------------------------+----------------------------+
| TR-TT-002  | Reach 4 way-points + 1 extra one in         | Rules/T.T/Description      |
|            | challenging terrain                         |                            |
+------------+---------------------------------------------+----------------------------+
| TR-TT-003  | Send location data to the ground control    | Rules/T.T/Task Scen./a)    |
+------------+---------------------------------------------+----------------------------+
| TR-TT-003/1| Broadcast only position ([x,y,z]) and       | Rules/T.T/General req./e)  |
|            | orientation data (e. g. quaternion)         |                            |
+------------+---------------------------------------------+----------------------------+
| TR-TT-003/2| Visualize localization data in the most     | Rules/T.T/Add. info/b)     |
|            | operator-friendly manner                    |                            |
+------------+---------------------------------------------+----------------------------+
| TR-TT-004  | Perform planning and compute parameters     | Rules/T.T/Description      |
|            | within the rover system, preferably on-board|                            |
+------------+---------------------------------------------+----------------------------+
| TR-TT-004/1| Perform localization computations on-board  | Rules/T.T/General req./b)  |
|            | using preferably natural terrain features   |                            |
+------------+---------------------------------------------+----------------------------+
| TR-TT-004/2| Apply initial data set: start position and  | Rules/T.T/General req./f)  |
|            | limited heading                             | Rules/T.T/Add. info/a)     |
+------------+---------------------------------------------+----------------------------+
| TR-TT-005  | Apply any navigational technique but GNSS   | Rules/T.T/General req./d)  |
|            | receivers                                   |                            |
+------------+---------------------------------------------+----------------------------+
| TR-TT-006  | Provide a detailed description of applied   | Rules/T.T/Add. info./d)    |
|            | navigational techniques                     |                            |
+------------+---------------------------------------------+----------------------------+
| TR-TT-007  | Store telemetric data                       | Rules/T.T/Exp. results/d)  |
+------------+---------------------------------------------+----------------------------+
| TR-TT-007/1| Visualize stored, telemetric data           | Rules/T.T/Task scen./d)    |
+------------+---------------------------------------------+----------------------------+
| TR-TT-007/2| Compare results (executed route) with a     | Rules/T.T/Task scen./d)    |
|            | computed traverse plan at the beginning     |                            |
+------------+---------------------------------------------+----------------------------+



Glossary
--------

.. glossary::

    Task
        one of the missions to be completed during the Challenge



