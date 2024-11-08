# ShiftReg
This project is aimed at building a Universal Shift Register(USR) that consumes less power and operates at high speed than the usual USR.
# **Contents**
* [What is a Universal Shift Register](https://github.com/AmirthaThenappan/ShiftReg/edit/main/README.md#what-is-a-universal-shift-register)
* [Block Diagram of modified USR IP](https://github.com/AmirthaThenappan/ShiftReg/edit/main/README.md#block-diagram-of-modified-usr-ip)
* [Circuit Diagram of USR](https://github.com/AmirthaThenappan/ShiftReg/edit/main/README.md#circuit-diagram-of-usr)
* [Performance parameters](https://github.com/AmirthaThenappan/ShiftReg/edit/main/README.md#performance-parameters)
* [Open source tools used](https://github.com/AmirthaThenappan/ShiftReg/edit/main/README.md#open-source-tools-used
)
* [Installation in Ubuntu](https://github.com/AmirthaThenappan/ShiftReg/edit/main/README.md#installation-in-ubuntu)
   - [esim Installation](https://github.com/AmirthaThenappan/ShiftReg/edit/main/README.md#esim-installation)
   - [Ngspice Installation](https://github.com/AmirthaThenappan/ShiftReg/edit/main/README.md#ngspice-installation)
   - [SkyWater PDK Installation](https://github.com/AmirthaThenappan/ShiftReg/edit/main/README.md#skywater-pdk-installation)
* [Installation in Windows](https://github.com/AmirthaThenappan/ShiftReg/edit/main/README.md#skywater-pdk-installation)
   - [esim Installation](https://github.com/AmirthaThenappan/ShiftReg/edit/main/README.md#esim-installation-1)
* [Schematic and Simulation](https://github.com/AmirthaThenappan/ShiftReg/edit/main/README.md#schematic-and-simulation)
* [Contributors](https://github.com/AmirthaThenappan/ShiftReg/edit/main/README.md#contributors)
* [Acknowledgment](https://github.com/AmirthaThenappan/ShiftReg/edit/main/README.md#acknowledgment)
* [Contact Information](https://github.com/AmirthaThenappan/ShiftReg/edit/main/README.md#contact-information)
# What is a Universal Shift Register
# Block Diagram of modified USR IP
# Circuit Diagram of USR
# Performance parameters
# Open source tools used
* **eSim**
eSim is a free, open-source electronic design automation (EDA) tool for circuit design, simulation, analysis, and PCB design. It's an alternative to commercial software like OrCAD, Xpedition, and HSPICE. Esim can be downloaded from the website:[](https://esim.fossee.in/downloads)
* **Ngspic**
Ngspice is a free, open-source circuit simulator for electronic and electric circuits. Ngspice can be downloaded from the website:[](http://ngspice.sourceforge.net/download.html)
# Installation in Ubuntu
## esim Installation
Please refer to the following links for proper installation of eSim
* [](https://static.fossee.in/esim/installation-files/Install_eSim_on_Windows.pdf)
* [](https://github.com/FOSSEE/eSim/blob/master/INSTALL)
## Ngspice Installation
* Please refer to the following links for proper installation of Ngspice
[](http://ngspice.sourceforge.net/download.html)
## SkyWater PDK Installation
In Ubuntu In terminal, execute the following commands
* To download the repository into the current working directory
$ git clone git://opencircuitdesign.com/open_pdks
* Go to open_pks directory
$ cd open_pdks
* Configure and install
$ ./configure --enable-sky130-pdk
$ make
$ sudo make install
# Installation in Windows
* The eSim Software is currently available for Windows 7, 8 and 10 and Ubuntu 16.04 LTS and above
* Ngspice and SkyWater PDK are installed when eSim is installed in Windows OS.
## esim Installation
* Download eSim for Windows OS from "https://esim.fossee.in/". Disable the antivirus (if any).
* Now double click on eSim installer and then follow the instruction to install eSim.
* After the installation is completed, please download and add the following file to the esim home directory(FOSSEE\eSim\ folder): [](https://github.com/FOSSEE/eSim/blob/master/src/frontEnd/TerminalUi.ui#L6)
Please download and add the following executable to the nghdl folder(FOSSEE\eSim\nghdl\src location):[](https://drive.google.com/file/d/17MNCCq9cG6A7fnIH-4KMUMY-yb4rW9s4/view?usp=sharing)
# Schematic and Simulation
# Contributors
* Amirtha Thenappan
# Acknowledgment
* Kunal Ghosh, Director, VSD Corp. Pvt. Ltd.
* Sumanto kar, Assistant Project Manager, FOSSEE
# Contact Information
* Amirtha Thenappan, PSG Institue of Technology and Applied Research [mail_id](21l104@psgitech.ac.in)
* Kunal Ghosh, Director, VSD Corp. Pvt. Ltd. [mail.id](kunalghosh@gmail.com)
* Sumanto kar, Assistant Project Manager, FOSSEE [linkden_profile](https://www.linkedin.com/in/sumanto-kar-0424391a9/)
