# ShiftReg
This project is aimed at building a Universal Shift Register(USR) that consumes less power and operates at high speed than the usual USR.
# **Contents**
* [What is a Universal Shift Register](https://github.com/AmirthaThenappan/ShiftReg/edit/main/README.md#what-is-a-universal-shift-register)
* [Proposed USR Design with high speed and low power convention](https://github.com/AmirthaThenappan/ShiftReg/edit/main/README.md#proposed-usr-design-with-high-speed-and-low-power-convention)
* [Block Diagram of modified USR IP](https://github.com/AmirthaThenappan/ShiftReg/edit/main/README.md#block-diagram-of-modified-usr-ip)
* [Circuit Diagram of modified USR](https://github.com/AmirthaThenappan/ShiftReg/edit/main/README.md#circuit-diagram-of-usr)
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
The universal shift register is another general-purpose digital circuitry that provides the facility of left or right shifting apart from parallel data loading. It can perform a variety of operations such as serial and parallel data input and output. It finds wide applications in different types of digital systems. The term “universal” itself designates multi-operation capability, which includes holding the data statically along with shifting in both directions. Normally, the universal shift register is designed by using digital ICs such as 74291 and 74395 in order to obtain full functionality within digital circuits.
## Working of USR
A universal shift register operates in any of three modes: according to the control signals. If the “Shift Left” control signal is active, there is a shift in data one position to the left, while the leftmost bit is lost and the rightmost bit is replaced from the serial input. In “Shift Right,” the data moves right with the loss of the rightmost bit and loading of the leftmost from the serial input. “Parallel Load” allows the simultaneous loading of data from all input lines. For this, the register retains its current data if none of the control signals have been activated. Internally, their obvious external interface is implemented by using multiplexers and flip-flops: the bits are held by a flip-flop, while a multiplexer acts for the input source at each operation.
## n-Bit Universal Shift Register
A n-bit universal shift register consists of n flip-flops and n 4×1 multiplexers. All the n multiplexers share the same select lines(S1 and S0)to select the mode in which the shift register operates. The select inputs select the suitable input for the flip-flops.

![image](https://github.com/user-attachments/assets/281abf2e-3d2f-43db-becd-23a6c1c3b702)

> Basic connections
* The first input (zeroth pin of multiplexer) is connected to the output pin of the corresponding flip-flop.
* The second input (first pin of multiplexer) is connected to the output of the very-previous flip flop which facilitates the right shift.
* The third input (second pin of multiplexer) is connected to the output of the very-next flip-flop which facilitates the left shift.
* The fourth input (third pin of multiplexer) is connected to the individual bits of the input data which facilitates parallel loading.
The working of the Universal shift register depends on the inputs given to the select lines. The register operations performed for the various inputs of select lines are as follows

![image](https://github.com/user-attachments/assets/d2bf2591-c937-48fd-87c1-114ae8c95bfd)

## Advantages of Universal Shift Register
* Multifunctionality: left and right shifts, parallel load, and static hold can all be performed.
* Flexibility: can be used in many different digital systems.
* Efficient: reduces the hardware to manipulate the data.
## Disadvantages of Universal Shift Register
* Complexity: More complex and expensive as compared to the simple shift registers.
* Slower Operations: Sometimes additional control logic makes them slower.
* Higher Cost: Additional functionalities raise the cost of implementation.
source of the above information : https://www.geeksforgeeks.org/universal-shift-register-in-digital-logic/
# Proposed USR Design with high speed and low power convention
* In conventional USR with D Flip-Flop (DFF), the Q output is identical to the D input except with one pulse time delay. Therefore, there will be a delay, i.e. it will take one clock pulse to transfer the bit to next flip flop. Therefore we **use Hold Mode Flip Flop (HM FF) for the design to attain high speed performance.**

![image](https://github.com/user-attachments/assets/50124050-6779-4da8-a5c9-ac2442d98b8f)

![image](https://github.com/user-attachments/assets/9150bfa4-a6c8-4ec1-86d7-f5603e39ce30)
> the above idea was proposed in the paper Single Cycle Access Structure for Logic Test
by Tobias Strauch & DESIGN AND ANALYSIS OF HIGH SPEED SHIFT REGISTER USING SINGLE CLOCK PULSE METHOD by A. Rajaram,P. Premalatha,R. Sowmiya , S. Saravanan, R. Vijaysai
* To achive low power consumption  a novel clock pulse generation scheme, called as Multiplexer based Clock Pulse Generator (MCPG) is used to minimize the power consumption and reduce the silicon area occupation of the shift register by reconstructing the clock distribution network using MCPG.As it was found that the major contribution for the power utilization is caused by the clock distribution network.
![image](https://github.com/user-attachments/assets/cfb6b1a4-f538-4a8b-b4aa-8e97b96bed32)
> The above idea was proposed in the paper  Performance analysis of clock pulse generators and design of low power area efficient shift register using multiplexer based clock pulse generatorR. Murugasamia,∗,U.S.Ragupathy

> and here in this work we are going to combine the above two novel methods and obtain a highly efficient USR in terms of Speed and Power Consumption
# Block Diagram of modified USR IP
Block Diagram of the modified USR is
![image](https://github.com/user-attachments/assets/2ad56eb6-84b0-4289-a6b9-4603dafba6f0)
# Circuit Diagram of modified USR
* Before simulating the actaul modified USR , I first simuted parts of it and then combined them together
* First was to simulate a D-Flip Flop and to get accoustomed with the tool
  ![image](https://github.com/user-attachments/assets/42fae38b-cd55-434b-8fbb-95316475fc52)
* Later I simulated the actal USR without any improvements
 ![image](https://github.com/user-attachments/assets/860cab0e-7588-4e51-852e-9eb961c5f0f8)
# Performance parameters
Yet to be recorded and analysed
# Open source tools used
* **eSim**
eSim is a free, open-source electronic design automation (EDA) tool for circuit design, simulation, analysis, and PCB design. It's an alternative to commercial software like OrCAD, Xpedition, and HSPICE. Esim can be downloaded from the website: https://esim.fossee.in/downloads
* **Ngspic**
Ngspice is a free, open-source circuit simulator for electronic and electric circuits. Ngspice can be downloaded from the website: http://ngspice.sourceforge.net/download.html
# Installation in Ubuntu
## esim Installation
Please refer to the following links for proper installation of eSim
* https://static.fossee.in/esim/installation-files/Install_eSim_on_Windows.pdf
* https://github.com/FOSSEE/eSim/blob/master/INSTALL
## Ngspice Installation
* Please refer to the following links for proper installation of Ngspice
http://ngspice.sourceforge.net/download.html
## SkyWater PDK Installation
In Ubuntu In terminal, execute the following commands
* To download the repository into the current working directory
> $ git clone git://opencircuitdesign.com/open_pdks
* Go to open_pks directory
> $ cd open_pdks
* Configure and install
> $ ./configure --enable-sky130-pdk
> $ make
> $ sudo make install
# Installation in Windows
* The eSim Software is currently available for Windows 7, 8 and 10 and Ubuntu 16.04 LTS and above
* Ngspice and SkyWater PDK are installed when eSim is installed in Windows OS.
## esim Installation
* Download eSim for Windows OS from https://esim.fossee.in/. Disable the antivirus (if any).
* Now double click on eSim installer and then follow the instruction to install eSim.
* After the installation is completed, please download and add the following file to the esim home directory(FOSSEE\eSim\ folder): https://github.com/FOSSEE/eSim/blob/master/src/frontEnd/TerminalUi.ui#L6
Please download and add the following executable to the nghdl folder(FOSSEE\eSim\nghdl\src location): https://drive.google.com/file/d/17MNCCq9cG6A7fnIH-4KMUMY-yb4rW9s4/view?usp=sharing
# Schematic and Simulation
* For the D-Flip Flop schematic that i have attached previously the below are the results that i obtained , though they are bnot the expected output i a working on it

![image](https://github.com/user-attachments/assets/5e7d106f-b525-40dd-b151-6751e381e4ae)

![image](https://github.com/user-attachments/assets/f697b780-91ab-47df-9b5a-a514ba9673d9)

![image](https://github.com/user-attachments/assets/4064802c-19aa-4d4d-bef4-6fa0ffb41f1f)
* As i progress with the design , will update the repo
# Contributors
* Amirtha Thenappan
# Acknowledgment
* Kunal Ghosh, Director, VSD Corp. Pvt. Ltd.
* Sumanto kar, Assistant Project Manager, FOSSEE
# Contact Information
* Amirtha Thenappan, PSG Institue of Technology and Applied Research 21l104@psgitech.ac.in
* Kunal Ghosh, Director, VSD Corp. Pvt. Ltd. kunalghosh@gmail.com
* Sumanto kar, Assistant Project Manager, FOSSEE https://www.linkedin.com/in/sumanto-kar-0424391a9/
