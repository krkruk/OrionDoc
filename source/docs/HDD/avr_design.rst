====================================
(LV2) On-board low-level AVR modules
====================================

Introduction
------------

This documents lists low level AVR microcontroller modules present 



+----------------+-----------------+-----------------------------+--------------------------------------------+
| #              | Location        | Description                 | Short functionality                        |
+================+=================+=============================+============================================+
| **General Feature**                                                                                         |
+----------------+-----------------+-----------------------------+--------------------------------------------+
| AVR-1 to AVR-4 | Motor driver    | Control of                  | Set direction and speed, count rotations   |
|                |                 | main propulsion motor 0-3   | monitor and forward RPM, current,          |
|                |                 |                             | temperature, handle hardware malfunctions  |
+----------------+-----------------+-----------------------------+--------------------------------------------+
| AVR-5          | Main arm turret | Control of main arm motors  | Set direction and speed, position          |
|                |                 | including first six degrees | the joints, monitor and forward current,   |
|                |                 | of freedom                  | angles, handle hardware malfunctions       |
+----------------+-----------------+-----------------------------+--------------------------------------------+
| AVR-6          | Gripper         | Control of gripper motors   | Open and close the jaws, monitor the force |
|                |                 | and sensor feedback         | of the gripper, current, distance from     |
|                |                 |                             | surface, relative position versus ground,  |
|                |                 |                             | meaure voltage and current, operate lights,|
|                |                 |                             | lasers and additional servo actuator       |
+----------------+-----------------+-----------------------------+--------------------------------------------+
| AVR-7          | Chassis         | Rover position feedback     | Measure and forward the distance from 8    |
|                |                 |                             | ultrasonic sensors, get data from 3 DOF    |
|                |                 |                             | sensor including accelerometer, gyroscope, |
|                |                 |                             | magnetometer, obtain and forward relative  |
|                |                 |                             | rotation of the main chassis segments      |
+----------------+-----------------+-----------------------------+--------------------------------------------+
| AVR-8          | Battery bay     | Power cell management       | Measure and forward the voltage, current   |
|                |                 |                             | and temperature from power cells. Handle   |
|                |                 |                             | powerups and powerdowns. Handle safety for |
|                |                 |                             | LiPo cells in case of improper parameters. |
|                |                 |                             | Accept powerdown commands from main CPU.   |
+----------------+-----------------+-----------------------------+--------------------------------------------+
| AVR-9          | LIDAR turret    | LIDAR operation             | Provide control for LIDAR motors both in   |
|                |                 |                             | horizontal and vertical planes. Forward    |
|                |                 |                             | the measurements from scanning terrain.    |
|                |                 |                             | Set horizontal and vertical limits.        |
|                |                 |                             | Change precision and angles.               |
+----------------+-----------------+-----------------------------+--------------------------------------------+
| AVR-10         | Zoom camera     | 8X zoom camera operation    | Provide control for camera motors both in  |
|                | turret          |                             | horizontal and vertical planes. Control    |
|                |                 |                             | the light for camera and signaling.        |
|                |                 |                             | Calibrate tht motors.                      |
+----------------+-----------------+-----------------------------+--------------------------------------------+
| AVR-11         | Gripper bracket | AVIOMARIN module operation  | Provide control for camera roataion motor. |
|                |                 |                             | Calibrate the camera travel. Quickly set   |
|                |                 |                             | camera position around the gripper.        |
|                |                 |                             | DO MOAR STUFF WE FORGOT SOMEWHERE ON GRIP  |
+----------------+-----------------+-----------------------------+--------------------------------------------+
| AVR-12         | Science arm     | Science arm sensors         | Turn the sensors on and off. Obtain data   |
|                | module          | data aquisition             | from gas, temperature and other sensors.   |
|                |                 |                             | Forward the measurements.                  |
+----------------+-----------------+-----------------------------+--------------------------------------------+
| AVR-13         | Science arm     | Science arm PH and Geiger   | Turn the sensors on and off. Obtain data   |
|                | module??        | sensor aquisition           | from sensors. Forward the measurements.    |
+----------------+-----------------+-----------------------------+--------------------------------------------+
| AVR-14         | Science box     | Science box sample analysis | Open and close boxes. Measure parameters   |
|                | module          |                             | including weight AND WHAT? from sensors.   |
|                |                 |                             | Operate the microscope conveyor belt and   |
|                |                 |                             | sample backlighting.                       |
+----------------+-----------------+-----------------------------+--------------------------------------------+
