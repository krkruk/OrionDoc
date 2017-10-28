=======================
Orion Tools
=======================

Introduction
============
This document describe a set of auxiliary tools created by the Orion Team to boost the workflow.

Virtual Machine
===============
The team provides a virtual machine that supports software development especially for LV2 and LV3. The host system is Antergos [#]_\ - an Arch Linux based distribution. Antergos is selected due to ease of configuration and compatibility with Arch, which provides compatibility with software developed especially for on-board computers.

The following folder structure is present for a freshly installed VM::

    .
    ├── Desktop
    │   ├── run_documentation_server.desktop
    │   └── run_drive_module.desktop
    ├── ORION
    │   └── OrionPi             // executables here
    │       ├── lib
    │       │   ├──             // libraries here
    │       ├── OrionEarthBase
    │       ├── OrionPiOnboard
    │       └── tests           // compiled tests here
    │           ├── apps
    │           └── tst
    ├── protobuf_source         // protobuf sources
    │   └── v3.3.0.tar.gz
    ├── source
    │   ├── docs
    │   │   └── OrionDoc        // documentation
    │   │       ├── build
    │   │       ├── make.bat
    │   │       ├── Makefile
    │   │       └── source
    │   ├── install_repos.sh
    │   ├── lv2_apps            // LV2-related apps
    │   │   ├── build
    │   │   └── Qt-OrionPi      // LV2, LV3 source code
    │   ├── run_drive_module.sh
    │   └── start_documentation_sphinx_server.sh
    └── xboxdrv                 // xboxdrv compiled package
        └── xboxdrv-0.8.8-3-x86_64.pkg.tar

General
-------
All required environmental variables are set in *~/.bashrc* so a user is not forced to run *set_environment_variables.sh* script.

In order to develop software in *QtCreator* a user is expected to do the folowing steps:
    * Press CTRL+ALT+T to open a terminal
    * Enter *qtcreator*, all environmental variables are set
    * Start development

A user has to configure git for his/her own and provide ssh keys. To do so, follow commands [#]_\:

.. code-block:: bash

    $ git config --global user.name "John Doe"
    $ git config --global user.email johndoe@example.com

To configure SSH connection follow the steps provided by `GitHub <https://help.github.com/articles/connecting-to-github-with-ssh/>`_\.

Desktop
-------
The virtual machine provides convenience shortcuts to run apps.
    * run_documentation_server.desktop - runs sphinx-autobuild tool and provides real-time HTTP updates on *localhost:8000*
    * run_drive_module.desktop - runs 2 apps: OrionPiOnboard and OrionEarthBase. The former discovers all available UART devices and provides an LV2 server. The latter is a client application that connects over TCP to LV2 app, reads commands from a gamepad and sends them to OrionPiOnboard.

ORION
-----
ORION directory holds all compiled libraries and applications.

source
------
This directory holds files that can be found in the repositories.

install_repos.sh
''''''''''''''''
The script conveniently downloads repositories and places it in the right places. To run it enter the following command:

.. code-block:: bash
    
    $ source ./install_repos.sh
    

run_drive_module.sh
'''''''''''''''''''
The script 2 application: OrionPiOnboard and OrionEarthBase. The most convenient way to run is to double-click a proper icon in the Desktop. Otherwise run it as:

.. code-block:: bash

    $ source ./run_drive_module.sh
    
    
start_documentation_sphinx_server.sh
''''''''''''''''''''''''''''''''''''
The script runs *sphinx-autobuild* tool. If the script is executed, it starts a server under *localhost:8000*. Any change to a documentation file will result in re-making the documentation and presenting it in under the address. The most convenient way to run it is to double-click a proper icon in the Desktop. Otherwise run it as:

.. code-block:: bash

    $ source ./start_documentation_sphinx_server.sh

lv2_apps
--------
This directory holds repositories that are related to LV2 applications and its *\*.o* files in build directories.

xboxdrv
-------
The directory holds a source code of xboxdrv and its build package. Just in case...

.. rubric:: Reference documents

.. [#] https://antergos.com/
.. [#] https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup