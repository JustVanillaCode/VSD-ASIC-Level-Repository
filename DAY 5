
Delay Tables -

The file "sky130_inv.mag" located in the "vsdstdcelldesign" directory contains important information such as port information, logic, and PG. However, since OpenLANE is a PnR tool, it doesn't need the whole information present in the .mag file. The only details that OpenLANE requires are the boundary, power, and ground rails, as well as the input and output information. To extract this information, we use .lef files. Thus, our next objective is to extract the LEF file from the MAGIC file and integrate it into the picorv32a design.

When creating a standard cell, it's important to follow certain guidelines, such as ensuring that the input and output ports intersect with the horizontal and vertical tracks. This makes sure that the routes can reach the ports. Additionally, the width and height of the standard cell must be odd multiples of the track's horizontal and vertical pitch, respectively.

Tracks refer to the horizontal and vertical metal layers on which routing occurs. The intersection of horizontal and vertical tracks creates a routing grid, which is also known as a routing matrix.The intersection of horizontal and vertical tracks creates a routing grid, which is also known as a routing matrix.

The file- ~/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/openlane/sky130_fd_sc_hd/tracks.info contains track information. This is it before and after changing the grid values.

![image](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/b267b408-aaf2-40c0-864a-6251822f4564)

![image](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/2454c88f-b65a-4d18-aeb4-0f281303f4ac)

Now, we can satisfy the guidelines.  

Timing libs and New cell synthesis-
The lib directory has the timing files for SKY130 PDK, It has the timing and parameters for each cell. It can vary it could be slow or fast or typical depending on the supply voltage which is Pvt. The library named Sky130_fd_sc_hd__ss_025C_1v80 represents the  PVT corner as ss(slow-slow).

Spice Deck -
The SPICE deck is a file that contains information about how the different electronic components in a circuit are connected to each other. It specifies which inputs need to be provided and which outputs need to be monitored. The values of components are also specified in the file. For instance, the PMOS (positive channel metal oxide semiconductor) has a channel length of 0.25 microns and a channel width of 0.375 microns. Ideally, the width of the PMOS should be 2 to 3 times wider than that of the NMOS (negative channel metal oxide semiconductor). This is because the PMOS hole carrier is slower than the NMOS carrier, and to achieve matched rise and fall times, we need to reduce the resistance by increasing the width of the PMOS. After this, the nodes in the circuit are identified and named.

![image](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/f0efb43a-3051-4832-b936-daa8060b567d)

The SPICE deck netlist syntax for PMOS and NMOS is as follows: [component name] [drain] [gate] [source] [substrate] [transistor type] W=[width] L=[length]. It's important to note that all components in a netlist are described based on their node and values.

For example, the syntax for a PMOS component with a plate number of 1, connected to VDD as drain, gate, and source, with a width of .375u and a length of .25u would be as follows: M1 OUT IN VDD VDD PMOS W=.375u L=.25u.

Spice Simulation for CMOS Inverter
To start the SPICE simulation, we will use '.op' where Vin will be varied from 0 to 2.5 in steps of 0.05V. The model file, 'tsmc_025um_model.mod', contains all the technological parameters for the 0.25µm NMOS and PMOS.

![image](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/c6fd7be7-b6e8-4f1e-936e-7c05b30c92b4)


To run the SPICE simulation, follow these steps:

1. Open the NGSPICE simulator.
2. Use the 'source' command to source the circuit file.
3. Execute the simulation using the 'run' command.
4. Use the 'setplot' command to view any plots possible from the simulations specified in the SPICE deck. It will give you a choice for which simulation to be run.
5. Type 'display' to see a choice of nodes to be plotted. When 'plot out vs in' is typed, it will be plotted on a graph.

![image](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/d225aa46-f358-46dc-8536-4fd5e2928003)

Switching Threshold Vm
![image](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/0dfe78bb-24fa-4499-a7fd-98a5c0c335db)

Important Points:
- The shapes of the graphs for CMOS devices are almost the same, indicating that they are robust.
- The robustness of CMOS devices depends on two parameters: the switching threshold and the propagation delay.
- The switching threshold is the point where the input voltage is equal to the output voltage, and both the PMOS and NMOS are in the saturation region. When these are turned on, there is a high chance of leakage, and current flows directly from VDD to GND. This can cause short circuits.

![image](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/31233021-3493-4827-a7a3-a515fa88492a)

SKY130 Layers Layout and LEF using Inverter
![image](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/5fd789e4-51a9-40cf-86fb-166479fb64c4)

In the sky130A technology, the first layer used is the local interconnect (LDD) layer, followed by the m1 and m2 layers. The power and ground lines are placed in the m1 layer. The placement of the polysilicon layer determines whether an NMOS or PMOS transistor is created, depending on whether it crosses over an n-diffusion or p-diffusion layer. The layout output is provided in the form of a LEF file, which is used by the router in APR to determine the location of standard cell pins for proper routing. Therefore, it serves as an abstract representation of the layout of a standard cell.

Steps to create STD CELL LAYOUT and Extract SPICE NETLIST.
To do this, we can enter the following commands in TCKON-
1. `extract all`
2.` ext2spice cthresh 0 rthresh 0`
3. `ext2spice`

![image](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/8cab03f1-d508-47a2-a35a-bdec7ac484a0)

   ![image](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/9f881cea-7ef7-4022-94c3-5be6aa4c4374)

We can modify the previous file to plot a transient response. This will then create a final SPICE deck by editing like in the image given below - 

![image](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/8377a7fc-39a7-417c-98a1-c9a5cf7b888a)

To insert this in NGSPICE we can type `ngspice sky130A_inv.spice`
After typing the command, you will get the result like shown in the image- 

![image](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/f9955a00-466e-4281-b311-ae3417813f6f)

Now, if you want to generate a plotted graph, type- `plot y vs time a`. It will look like this- 

![image](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/064b0534-0bd7-4975-b177-def37acd6394)

NOTE : The cell is plotted with analysis occurring at 27 degrees celsius. 
Using this, 
1. We can describe the properties of a cell through four distinct parameters. One of these parameters is the value of rise transition, which denotes the time required for an output waveform to transition from a value of 20% of the maximum value to 80% of the maximum value, where the maximum value is equal to vdd, which is 3.3V. To calculate this parameter, we need to locate the points on the waveform where the voltage is 20% and 80% of the maximum value (i.e. 0.66V and 2.64V, respectively), and record their corresponding x and y values in the terminal.

2. The value of fall transition refers to the time taken for an output waveform to transition from 80% to 20% of its maximum value. Similarly, the difference between 4.06818ns and 4.04073ns is 0.02745ns.

3. The fall cell delay is basically the diff or delay between the 50% of the input and 50% of the output. Like 4.05402 nanoseconds - 4.0501 nanoseconds = 0.00392 nanoseconds

4. The value of rise cell delay is the time diff or delay between 50% of the input and 50% of the output. Which means the time which is taken for the o/p to rise 50% and i/p to fall 50%. like - 2.18381 nanoseconds - 2.15003 nanoseconds = 0.03378 nanoseconds.

![image](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/cd422425-5c68-4742-b331-7cd4d626855d)

Intro To SKY130A PDK
Now,  for labs, we can download the lab files by command `wget`
To extract these, type `tar xfz drc_tests.tgz`

![image](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/fd921a7b-3d41-4d18-a925-45b130ac8d73)

Then we will change the directory by `cd drc_tests` and then type `ls -al` and to open magic type `magic -d XR`
Then click on File and select met3.mag

![image](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/18c4f192-92dc-4028-86b5-82fcf2393680)

Exercise -

![image](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/7711cb26-d065-4098-86a9-1dbc47490c21)

Now, let us concentrate on the poly 9 rule which means that the poly resistor spacing to poly or no overlap to diff/tap should be a minimum of 0.48 um. Look at the image below, now the error must be fixed. 

![image](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/842e8597-e2f3-4a8b-bbe4-87d93f2fad6a)

IThe directory pdks/sky130A/libs.ref/sky130_fd_sc_hd/lib/ contains the liberty timing files for the PDK with plate number 1. These files contain timing and power parameters for each cell needed in STA. The library includes three PVT corners - slow, typical, and fast - with different supply voltages (1v80, 1v65, 1v95). The library named sky130_fd_sc_hd__ss_025C_1v80 describes the slow-slow PVT corner, which means the delay is maximum, at 25° Celsius temperature, and at 1.8V power supply. 

The timing and power parameters of a cell are obtained by simulating the cell in different operating conditions, or corners, and the data is represented in the liberty file. This file characterizes all cells and is used during ABC mapping in the synthesis stage, which maps the generic cells to the actual standard cells available in the liberty file.

To proceed with the task, you need to copy the extracted lef file named sky130_vsdinv.lef and the liberty files named sky130.lib* from the repository /openlane/vsdstdcelldesign/libs to the src directory of picorv32a.

![image](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/cbd38304-dfd1-4f42-a45e-407ca0e5326b)

Now, we can add the _config.tcl_ file inside the picorv32a directory.
After this, Enter the docker command and prepare picorv32a. Add the new lef file into OpenLane. You can do this from the following commands- 
1. docker
2. ./flow.tcl -interactive
3. package require openlane 0.9
4. prep -design picorv32a
5. set lefs [glob $::env(DEESIGN_DIR)/src/*.lef]
6. add_lefs -src $lefs


Then run synthesis and check so that the sky130_vsdinv cell is included in the design.
