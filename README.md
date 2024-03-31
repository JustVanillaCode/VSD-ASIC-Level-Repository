    # VSD-ASIC-Level-Repository by Athrv Sharma
This is a repository for the ASIC Level of VLSI course.
It is as follows :-
![image](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/3433742d-b970-472b-b669-62fa0ceef907)
A chip is inside a cover also called a package.
 There are many types of packages, they are also available in many materials like plastic. This package is mounted on a board-like structure. One popular example of a board is the Arduino board. The chip will have various components one of the important components are pads. It can be imagined as a path where signals can come in and out. Signals can be sent inside the chip and the signals can also come out of the chip. The 2 other main parts of the chip are the die and the core. The logic lies solely in the core, logic like gates like and, or, not gates e.t.c, a core usually consists of the SoC, SRam, Adc, Dac, Pill, Spi, and a couple of more components. The pills, ADCS, DAC, and Sram are the "Foundry IPs' " of a chip, gadgets like Mobile Phones, laptops, and their performance are all dependent on the IPs'.Die is just simply the size of the chip. A foundry is a large, extensive, colossal factory that helps manufacturing. It fundamentally manufactures the ICs' (Integrated Circuits) or the chips. An IP stands for 'Intellectual Property ' which means it mandates a particular intelligence to build the particular block. A foundry plays an essential role in the semiconductor industry. One of them is also present in IIT Bombay, India.

Usually, chips are coded in C or C++ languages  as they are more suitable for this process. This code is passed into a compiler and is converted into binary as it is the
only language a computer understands. Let us take an example  of  a  RISC-V, the code is first compiled into it's assembly language program which is nothing but the RISC-V
program, then this assembly language program is converted into machine language(Binary) which  is understood  by  the  computer. This is then executed to get the output. The
flow is -  Architecture --> RTL --> Layout(qFlow)  

There are many apps or application software that we use on a daily basis. They all depend on the chip. The central focus of our consideration hinges on how  it happens. The apps execute a signal to the so-called "System Software" which in turn converts the program to binary language. Majorly, the system software consists of the OS(Operating System), Compiler, and Assembler. It handles the IO operations, Allocates memory, and also helps in low-level system functions. A compiler and assembler convert the program to the chip type program for example if it is a RISC - V chip, Like this - 
![image](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/f167279e-ac62-4120-bb7f-4132f9eb33be)

 the program will be converted into a RISC - V instruction. The abstract interface instruction set architecture can also be called the 'architecture of a computer '.  

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------


![Screenshot 2024-03-20 163324](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/8d0989cc-7061-431b-90d0-567bc146f1ce)

ASIC, 
is made up of 3 crucial elements which are RTL IPs, EDA Tools, and  PDK Data. RTL (Register Transfer Level) is a crucial tool for accurately describing the digital components of a design. There are hundreds of open-source PDK, RTL, and EDA tools and data. For RTL - Github, opencores, librecores are some of them. There are many great EDA Tools, the more popular of them are Qflow, OpenRoad, OpenLane.  Before open source PDK, 
let us understand what is a PDK? -  
In the "age of gods" of integrated circuits or ics' Was tightly integrated with the manufacturing process available within each company those who control the physics they were the ones who control the creative agenda.
Lynn Conway and Carver Mead envisioned the need for separating the design from technology and pioneered the structured design methodology based on the λ(lambda) based rules. They also introduced structure design methodology that laid the basics of modern IC Chip design practices. since that time we have started to see pure play fabs and fabless design companies. PDK is the interface between Fab and the designers The interface  which will refer to as process design kits or PDK.
PDK is process design kit collection of files used to model a fabrication process for the E D A tools used to design a IC. Process design rules DRS LVS, PEX, device model, digital standard cell libraries, I/O libraries.

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------

![image](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/b751e348-f940-472c-90ab-939b7c85d38c)



It was hard for the general public and masses to access the PDK but now Google and Skywater technology have worked out an agreement for a 130-nanometer production pdk which was on June / 30 / 2020 the license  is Apache 2.0. This was the first ever open-source pdk for the Masses. So now we have all the elements for the open-source digital ASIC design for EDL tools: qflow, OpenRoad, and OpenLane. For RTL designs we have librecores, opencores, Github, and finally for PDK we have the agreement of Google and Skywater for the 130-nanometer production PDK. 

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The market share for different types of cutting edge techonology is as follows -

![image](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/abf4bbba-5c43-4673-b512-37b8c8304c01)



However, the market share for 130 nanometers is about 6%, and the  cutting-edge technology right now is about five nanometers. The 6% is about equivalent to $4.5 billion in annual revenue this is mainly due to two reasons because several applications do not need the advanced nodes. The fabrication process for these 130 and 180 nanometers is cheaper than compared to the advanced nodes. The Intel P4EE ran at 3.4 gigahertz and was designed by Intel using the 130-nanometer technology also the OSU team reported that a 327 megahertz post layout clock frequency for a single cycle rv 32 icp was received from a 130-nanometer node. 
The simplified RTL to GDSII to flow starts from the RTL which has the synthesis to floor planning to placement then the PDK which has the clock tree synthesis then the routing then finally the GDSII which is the end of the flow. The synthesis is as follows synthesis converts the rtl to a circuit out of components from the standard cell library (S C L) also known as the gate level synthesis. "Standard" cells have a regular layout, each has a different view or model like electrical, HDL, or spice. Layout ( abstract or detailed). The idea for Floor and power planning Is basically about the area of the silicon chip, die, etc, and the power distribution. Cheap floor planning the partition of the chip dye between different system building blocks takes place and also the placement of IO pads is done in this process. In macro floor planning the pin location, rows definition, dimensions, etc are done/planned. Power pads, power straps, and power rings are constructed in power planning. a gym is powered through many veedy deals and power pads They are constructed parallelly such parallel constructions are there to reduce the resistance and also to address the electromagnetization problem. The power distribution uses the upper metal layers rather than the lower metal layers as the upper metal layers as they are thicker than the lower metal layers and, hence have less resistance. Typically self placement is usually done in two steps global and detailed. In the clock three synthesis we create a clock distribution network to deliver the clock to all sequential elements within minimum skew 0 is hard to achieve and also make it in a good shape usually like a tree shape like a H, X... . Routing implements the nets using interconnection  available from the placed and available metal layers. The Skywater P D K has six layers the lowest one Is the interconnect layer And the titanium matride layer. The rest five layers are toggled into interconnecting layers Or aluminum layers. Enrouting metal tracks for a routing grid The routing grid is huge a divide and conquer approach is used, global routing creates routing guides and detailed routing uses the routing guides to implement the actual wiring. This includes physical verification like design rule checking D R C layout versus schematic l V S and timing verification like S T A or static timing analysis. Since the release of the PDK eFabless has decided to create an open-source asic flow called OpenLane. OpenLane started as an open source flow for a true open source tape out experiment striVe is a family of open everything SoCs like open pdk, open eda, and open rtl. The striVe family has many members they are the original striVe by SkyWater then striVe2 by Google, striVe3 by OpenRoad, striVe5 by efabless then finally the striVe6. The main goal for open lane is to produce clean gds 2 with no human intervention which means no human in the loop. And that too without any violation of LVS, DRC, and Timing Violation.    OpenLane is tuned for 130 nm open PDK. It also supports AFAB180 and GF130g.  It is also containized which means it is functional out of the box. It can be used to harden Macros and Chips. it has two modes of operation autonomous and interactive.                                                                    
When a metal wire segment is fabricated it can act as an antenna. Reactive iron etching causes charge to accumulate on the wire. Transistor gates can be damaged during fabrication. There are two solutions for it the first one is to do bridging which attaches a higher layer intermediary that requires router awareness. Adding antenna diode cells to leak away the charges these cells are provided by the S  C  L. The other solution is to adopt fake and dinner diode next to every cell input after placement then we could run the antenna checker magic on the routed layout if the checker reports a violation on the cell input then we have to replace the fake diode by a real one. Magic is used for designing rules checking and spice extraction from layout. Magic and Netgen are used for L V S.                                             
now let us learn how to define wit and height of core and a dye. First, let us begin with a netlist we have two flip flops and a combinational logic in between them. while defining a chip's dimensions, we mostly depend on the size of the combinational logic or the gates and the flip-flops. Firstly we will give the combinational logic and the flip flops respective breadth and height Then we are mostly interested in the dimensions of these standard cells. Let us take an example that a standard cell has a width and breadth of one unit by one unit thus the area will be one square unit we will calculate this entire area which will determine the width and height and the area of our chip. Let us take we have 2 flip flops and 2 gates each will have a width and height of 1 unit thus each of them has an area of 1 square unit therefore if we place them our total area will be 4 square units. So now we have a rough dimension or the rough area of our chip we are not omissing the wires into this right now. This is the minimum area that will be occupied by the netlist. When the entire area of a core is utilized and no free area is left it is known as 100 percent utilization or utilization factor = 1. The utilization factor is equal to the area occupied by the netlist divided by the total area of the core And the aspect ratio is height divided by width. If the utilization factor is 1 it means the chip is square if it is something like 0.5 it means that the chip is a rectangle.
the next step is to define the locations of the preplaced cells. To understand what is a preplaced cell let us first assume that we have a combinational logic and that the combinational logic has some amount of function. like it is the multiplier half adder full adder etc. First, we will remove a part of our main circuit, cut it in half, and place the two pieces on a block. Finally, we will connect the two blocks using wires. Next, we will extend the IO pins. we will black box these boxes. Then we will separate the black boxes into different IP modules. Similarly, there are other IPs' also available for example we have Memory, Clock Gating Cells, comparator, mux, etc. The arrangement of these IPs' in a chip is referred to as Floorplanning. These IPs'/blocks have user-defined locations, and hence are placed in a chip before automated placement and routing and are called - pre-placed cells. Automated placement and routing tools place the design's remaining logical cells onto one chip. Once they are placed, their location is fixed they're permanent, The further steps will not touch their location. There is also one more important thing that we have to book which is to surround the preplaced cells with Decoupling capacitors. Consider capacitance to be zero for the discussion RDD, RSS, IDD, and LSS are well-defined values. During switching operation a circuit demands switching current which means peak current or "Ipeak", now due to the presence of RDD and LDD there will be a voltage drop across them, and the voltage at node A would be VDD' instead of VDD. If VDD' goes below the noise margin, due to RDD and LDD, the logic one at the output of the circuit won't be detected as logic one at the input of the circuit following this circuit.  
The next important step is to bind netlist with physical cells. We will give each component of the netlist their own dimensions. These are present in shelves and let us call that a library. A library can be of two types one that contains the shape and the other that contains the information.  A library is a place where the standard cells are kept. Standard cells contain gates like - and gate, or gate, buffer, inverter, dff, latch, ICG, flip flops, etc.
There are two types of transistors CMOS and NMOS, to create a CMOS transistor we first select the substrate is selected usually a P-type Substrate is selected The resistance is usually high in the range of 5~50 ohms With doping level of 10 to the power of 13 cm3 with the orientation of 100. Substrate doping should be less than 'well' doping. Then the next step is to select that active area for transistors. Firstly, we will create isolation between each socket, then  deposit a layer of Silicon dioxide Of about 40 nm Next we will deposit a layer of silicon nitride of about 80 nm.  Then, 1um of photoresist is deposited, which will create the MASK 1, Then it is treated with UV light, and then the silicon nitrate will be etched, Then the photoresist is removed through chemicals. It is placed into a furnace, and field oxide is grown, this process is called 'LOCOS' Or local oxidation of silicon. silicon nitrate is then removed with hot phosphoric acid. Then we will create a gate area. The P-well, N-well, and p-type substrate is formed. This is how  a CMOS transistor is created.                                                                                                         

Clock tree synthesis is a crucial part of VLSI design. It consists of generating a network of clock distribution lines, which is known as the 'clock tree', to deliver the clock signal simultaneously and with the least and lowest skew to all sequential elements throughout the chip.

This process starts with defining clock requirements, which is then followed by generating a stratified network of clock lines then optimizing the clock tree to decrease skew, routing the clock lines, and verifying that the clock tree meets design requirements and timing constraints set by us.

Without clock tree synthesis, efficient clock distribution in VLSI designs cannot be guaranteed. It enables synchronous operation of sequential elements and ensures the design meets desired performance goals.
There is also a concept of H - Tree which calculates the middle of all its endpoints and originates a tree from that midpoint of all its endpoints.
For example let us say we have four flip flops flip flop one, flip flop 2, flip flop 3, and flip flop 4 they are placed in a square shape so the edge 3 syntheses will find the midpoint then it will reach the midpoint of flip flop 1 and 2 and then connect them same for flip flop 3 and 4 Show the clock reaches at every flip flop at the same time or almost at the same time, Show us skew Value will be zero or very close to zero. The clock will reach through real buffers, the connection is called a clock net. Also, the clock net is shielded so no glitch occurs and the net is not interfered.                                                                                                                                         
--Routing--
To Understand routing, let us say we have two points A and B and we have to connect A and B where A is the source and connect them in the best path with the least twists and turns. Twists and turns means zigzag lines, most of the lines should be in an L shape.
There is an algorithm for this that understands to not put the lines in such a way, it was invented by Lee in 1961 and is called Lee's algorithm. It creates a grid in the backend called the routing grid, it with the points to be routed. The first step is does that it labels the adjacent grids and calculate the path. Any routing algorithm or engine always prefers the path with the least turns. This algorithm works by first creating a maze of   numbers and then calculating the path. This is slow, time-consuming, and requires a lot of memory as each data has to be stored. There are also some rules that need to be followed during routing. 

Sign Off - this step has 3 attestation approaches
they are as follows
1. DRC i.e. Design Rule Check - This ensures that our design is set according to the design Guidelines, and is suited for fabrication. It's main purpose is to detect and correct errors like layout errors so no defects happen in the fabrication process.

2. Layout versus Schematic (LVS) - Compares and ensures the consistency between the schematic and the layout design.

3. STA i.e Static Timing Analysis - It checks the circuit to make sure that it meets the required delays like hold time, max and min clock frequency, e.t.c

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Thereshold timing-
A software called `GUNA` creates various .libs files, the schemantics of these .libs file are what we are going to discuss about.

![image](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/8bd59800-73a5-4031-bf81-6ed55068d277)


In this image, the red line is the o/p of the 1st inverter and blue one is the o/p of the second inverter.

![image](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/e9820094-c83b-46cb-8f30-55fa6a9c587e)

![image](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/d92b8c79-a906-4e58-b3c2-2b51d2e3300a)

![image](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/569cba23-a34e-43ae-b628-5a095e301d68)

Propagation delay is calculated as the difference between the time it takes for a signal to reach the output threshold and the time it takes for the same signal to reach the input threshold. If the propagation delay is negative, it can cause unexpected results, as the output signal will occur before the input signal. Therefore, it is crucial to select the correct threshold values. Generally, the delay threshold is set at 50%, while the slew rate threshold is set between 20% and 80%.

Transition time = time(slew_high_x_thr) - time(slew_low_x_thr)
Propagation delay = time(out_x_thr) - (time_x_thr)

![image](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/6193b8f9-78be-415e-a927-a4443541e730)

Delay Tables -
Got it, here's the revised text:

The file "sky130_inv.mag" located in the "vsdstdcelldesign" directory contains important information such as port information, logic, and PG. However, since OpenLANE is a PnR tool, it doesn't need the whole information present in the .mag file. The only details that OpenLANE requires are the boundary, power, and ground rails, as well as the input and output information. To extract this information, we use .lef files. Thus, our next objective is to extract the LEF file from the MAGIC file and integrate it into the picorv32a design.

When creating a standard cell, it's important to follow certain guidelines, such as ensuring that the input and output ports intersect with the horizontal and vertical tracks. This makes sure that the routes can reach the ports. Additionally, the width and height of the standard cell must be odd multiples of the track's horizontal and vertical pitch, respectively.

Tracks refer to the horizontal and vertical metal layers on which routing occurs. The intersection of horizontal and vertical tracks creates a routing grid, which is also known as a routing matrix.The intersection of horizontal and vertical tracks creates a routing grid, which is also known as a routing matrix.

The file- ~/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/openlane/sky130_fd_sc_hd/tracks.info contains track information. This is it before and after changing the grid values.

![image](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/b267b408-aaf2-40c0-864a-6251822f4564)

![image](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/2454c88f-b65a-4d18-aeb4-0f281303f4ac)

Now, we can satisfy the guidelines.  

Timing libs and New cell synthesis-
The lib directory has the timing files for SKY130 PDK, It has the timing and parameters for each cell. It can vary it could be slow or fast or typical depending on the supply voltage which is Pvt. The library named Sky130_fd_sc_hd__ss_025C_1v80 represents the  PVT corner as ss(slow-slow)

  ---OpenLane Labs---

Openlane is a tool tuned for 130nm cutting-edge technology, first, we will launch it then left-click and select - "Open Terminal "![Screenshot 2024-03-26 235359](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/1cd42941-300e-43b8-83ee-974acc62069b), then the terminal window will pop up; 
![Screenshot 2024-03-26 235512](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/a7f58aab-b989-430c-8540-656e3127b0a3)

then will type in the command line `ls` which means to list, then we will type `cd Desktop` cd means - change directory so this command line means to change the directory to Desktop, then `ls -ltr`, select tools using command line `cd tools`, then `ls -ltr`,` cd openlane_working_dir`, `cd openlane`, `ls -ltr`, then to run it in the interactive mode we will type the command line `docker`,  a bash 4.2 text will appear in front, then type `./flow.tcl -interactive`
this will turn the terminal into interactive mode ![Screenshot 2024-03-26 235925](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/e8d42fdd-f9ca-4d8a-98f1-2bf5aad087a4), the lines are below are the commands ![Screenshot 2024-03-27 000014](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/a8bddc4a-f3f4-4728-a040-ed2147e5fd98), then we will type `package require openlane 0.9`, `prep design picorv32a` to merge the lef files 
![Screenshot 2024-03-27 145202](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/4d5ea6af-0ceb-490a-a9c9-3229f8250283)
then when we check, a runs directory will be created. Inside the directory, a folder with today's date will be created ![Screenshot 2024-03-27 145814](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/f2a8af54-b20a-4685-8891-d74f16811667)
![Screenshot 2024-03-27 145754](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/10c47a59-ea98-42f7-849a-876e94244569), the next step is to  type `prep -design picorv32a`, after that we will run synthesis using the `run_synthesis` after some time, it will show ![Screenshot 2024-03-27 150726](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/1ca2bc8e-111c-4100-93e3-c453ed6825f5) to show that the synthesis was successful. Now we will characterize the synthesis results 

NOTE -- Flip Flop Ratio = Number of DFFs divided by the Number of cells * 100

By sloving this we get 1613 / 18036 * 100The other option is to view the results of the synthesis from the `synthesis` file in `picorv32a`. And to look the clock timing we can go to the `reports` folder. Then we will run the floorplan by the command `run_floorplan`.But before that, we have to set the variables. And to review the floorplan in Magic, use the command - `Magic -T/home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def & ` In magic, `S` key is to select `V` key to center and `Z` key to zoom, the pins will be equally distanced from each other, like the image
![image](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/d23d0738-4fce-49ad-93fa-242984f80733)

. The next step is to run placement by the `run_placement` command. It does 3 functions -
1. Gloobal Placement by using RePlace tool.
2. Optimization by Resier tool.
3. Detailed Placement by OpenDP tool.
After running the placement the output in magic looks like -

![image](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/117fffb0-ee89-4669-9f61-c898ee42714a)

Labs for CMOS
It's possible to change OpenLANE configurations within the shell itself, on the go. Normally, IO Mode is set to random equidistant. However, we can change this by using the following command after floorplan: "set::env(FP_IO_MODE) 2". Once this command is executed, the IO pins will no longer be equidistant in mode 2 (which is different from the default mode 1).
After this, we may run the floorplan to check whether or not are the IO pins placed in the Hungarian alg's way i.e. stacked on one another 

![image](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/01d8ca21-c3a3-42bc-b3ea-8502a2141a55)

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

Then run synthesis and check so that sky130_vsdinv cell is included in the design.



 Now we can run TritonCTS by `run_cts` command followed by `run_routing` to run routing, `run_magic`, `run_magicspice_export`, `run_magic_drc`, `run_netgen` then lastly `run_magic_antenna_check`.*To run Magic simulation, use the `Magic -T` command. 
This was the complete flow in labs, we ran it in interactive to run and understand each step, else the entire flow would have been executed and implemented in one go together.  
































































































     x-----x----x------x------x------x------x------x-----x-----x-----x----x-----x-----x-----x
         Thank You, You Have Reached The End Of This Repository 
         Author : Athv Sharma

