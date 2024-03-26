    # VSD-ASIC-Level-Repository by Athrv Sharma
This is a repository for the ASIC Level of VLSI course.
It is as follows :-
A chip is inside a cover also called a package. There are many types of packages, they are also available in many materials like plastic. This package is mounted on a board-like structure. One popular example of a board is the Arduino board. The chip will have various components one of the important components are pads. It can be imagined as a path where signals can come in and out. Signals can be sent inside the chip and the signals can also come out of the chip. The 2 other main parts of the chip are the die and the core. The logic lies solely in the core, logic like gates like and, or, not gates e.t.c, a core usually consists of the SoC, SRam, Adc, Dac, Pill, Spi, and a couple of more components. The pills, ADCS, DAC, and Sram are the "Foundry IPs' " of a chip, gadgets like Mobile Phones, laptops, and their performance are all dependent on the IPs'.Die is just simply the size of the chip. A foundry is a large, extensive, colossal factory that helps manufacturing. It fundamentally manufactures the ICs' (Integrated Circuits) or the chips. An IP stands for 'Intellectual Property ' which means it mandates a particular intelligence to build the particular block. A foundry plays an essential role in the semiconductor industry. One of them is also present in IIT Bombay, India.

Usually, chips are coded in C or C++ languages  as they are more suitable for this process. This code is passed into a compiler and is converted into binary as it is the
only language a computer understands. Let us take an example  of  a  RISC-V, the code is first compiled into it's assembly language program which is nothing but the RISC-V
program, then this assembly language program is converted into machine language(Binary) which  is understood  by  the  computer. This is then executed to get the output. The
flow is -  Architecture --> RTL --> Layout(qFlow)  

There are many apps or application software that we use on a daily basis. They all depend on the chip. The central focus of our consideration hinges on how  it happens. The apps execute a signal to the so-called "System Software" which in turn converts the program to binary language. Majorly, the system software consists of the OS(Operating System), Compiler, and Assembler. It handles the IO operations, Allocates memory, and also helps in low-level system functions. A compiler and assembler convert the program to the chip type program for example if it is a RISC - V chip, the program will be converted into a RISC - V instruction. The abstract interface instruction set architecture can also be called the 'architecture of a computer '.  

ASIC is made up of 3 crucial elements which are RTL IPs, EDA Tools, and  PDK Data. RTL (Register Transfer Level) is a crucial tool for accurately describing the digital components of a design. There are hundreds of open-source PDK, RTL, and EDA tools and data.For RTL - Github, opencores, librecores are some of them. There are many great EDA Tools, the more popular out of them are Qflow, OpenRoad, OpenLane.  Before open source PDK, 
let us understand what is a PDK? -  
In the "age of gods" of intregated circuits or ics' Was tightly integrated with the manufacturing process available within each company those who control the physics they were the ones who control the creative agenda.
Lynn Conway and Carver Mead envisioned the need for separating the design from technology pioneered the structured design methodology based on the λ(lambda) based rules. They also introduced structure design methodology that laid the basics of modern IC Chip design practices. since that time we have started to see pure play fabs and fabless design companies. PDK is the interface between Fab and the designers The interface  which will refer to as process design kits or PDK.
PDK is process design kit collection of files used to model a fabrication process for the E D A tools used to design a IC. Process design rules DRS LVS, PEX, device model, digital standard cell libraries, I/O libraries.
It was hard for the general public and masses to access the PDK but now Google and Skywater technology have worked out an agreement for a 130-nanometer production pdk which was on June / 30 / 2020 the license  is Apache 2.0. This was the first ever open-source pdk for the Masses. So now we have all the elements for the open-source digital ASIC design for EDL tools: qflow, OpenRoad, and OpenLane. For RTL designs we have librecores, opencores, Github, and finally for PDK we have the agreement of Google and Skywater for the 130-nanometer production PDK. However, the market share for 130 nanometers is about 6%, and the  cutting-edge technology right now is about five nanometers. The 6% is about equivalent to $4.5 billion in annual revenue this is mainly due to two reasons because several applications do not need the advanced nodes. The fabrication process for these 130 and 180 nanometers is cheaper than compared to the advanced nodes. The Intel P4EE ran at 3.4 gigahertz and was designed by Intel using the 130-nanometer technology also the OSU team reported that a 327 megahertz post layout clock frequency for a single cycle rv 32 icp was received from a 130-nanometer node. 
The simplified RTL to GDSII to flow starts from the RTL which has the synthesis to floor planning to placement then the PDK which has the clock tree synthesis then the routing then finally the GDSII which is the end of the flow. The synthesis is as follows synthesis converts the rtl to a circuit out of components from the standard cell library (S C L) also known as the gate level synthesis. "Standard" cells have a regular layout, each has a different view or model like electrical, HDL, or spice. Layout ( abstract or detailed). The idea for Floor and power planning Is basically about the area of the silicon chip, die, etc, and the power distribution. Cheap floor planning the partition of the chip dye between different system building blocks takes place and also the placement of IO pads is done in this process. In macro floor planning the pin location, rows definition, dimensions, etc are done/planned. Power pads, power straps, and power rings are constructed in power planning. a gym is powered through many veedy deals and power pads They are constructed parallelly such parallel constructions are there to reduce the resistance and also to address the electromagnetization problem. The power distribution uses the upper metal layers rather than the lower metal layers as the upper metal layers as they are thicker than the lower metal layers and, hence have less resistance. Typically self placement is usually done in two steps global and detailed. In the clock three synthesis we create a clock distribution network to deliver the clock to all sequential elements within minimum skew 0 is hard to achieve and also make it in a good shape usually like a tree shape like a H, X... . Routing implements the nets using interconnection  available from the placed and available metal layers. The Skywater P D K has six layers the lowest one Is the interconnect layer And the titanium matride layer. The rest five layers are toggled into interconnecting layers Or aluminum layers. Enrouting metal tracks for a routing grid The routing grid is huge a divide and conquer approach is used, global routing creates routing guides and detailed routing uses the routing guides to implement the actual wiring. This includes physical verification like design rule checking D R C layout versus schematic l V S and timing verification like S T A or static timing analysis. Since the release of the PDK eFabless has decided to create an open-source asic flow called OpenLane. OpenLane started as an open source flow for a true open source tape out experiment striVe is a family of open everything SoCs like open pdk, open eda, and open rtl. The striVe family has many members they are the original striVe by SkyWater then striVe2 by Google, striVe3 by OpenRoad, striVe5 by efabless then finally the striVe6. The main goal for open lane is to produce clean gds 2 with no human intervention which means no human in the loop. And that too without any violation of LVS, DRC, and Timing Violation.    OpenLane is tuned for 130 nm open PDK. It also supports AFAB180 and GF130g.  It is also containized which means it is functional out of the box. It can be used to harden Macros and Chips. it has two modes of operation autonomous and interactive.                                                                    
When a metal wire segment is fabricated it can act as an antenna. Reactive iron etching causes charge to accumulate on the wire. Transistor gates can be damaged during fabrication. There are two solutions for it the first one is to do bridging which attaches a higher layer intermediary that requires router awareness. Adding antenna diode cells to leak away the charges these cells are provided by the S  C  L. The other solution is to adopt fake and dinner diode next to every cell input after placement then we could run the antenna checker magic on the routed layout if the checker reports a violation on the cell input then we have to replace the fake diode by a real one. Magic is used for designing rules checking and spice extraction from layout. Magic and Netgen are used for L V S.                                             
now let us learn how to define wit and height of core and a dye. First, let us begin with a netlist we have two flip flops and a combinational logic in between them. while defining a chip's dimensions, we mostly depend on the size of the combinational logic or the gates and the flip-flops. Firstly we will give the combinational logic and the flip flops respective breadth and height Then we are mostly interested in the dimensions of these standard cells. Let us take an example that a standard cell has a width and breadth of one unit by one unit thus the area will be one square unit we will calculate this entire area which will determine the width and height and the area of our chip. Let us take we have 2 flip flops and 2 gates each will have a width and height of 1 unit thus each of them has an area of 1 square unit therefore if we place them our total area will be 4 square units. So now we have a rough dimension or the rough area of our chip we are not omissing the wires into this right now. This is the minimum area that will be occupied by the netlist. When the entire area of a core is utilized and no free area is left it is known as 100 percent utilization or utilization factor = 1. The utilization factor is equal to the area occupied by the netlist divided by the total area of the core And the aspect ratio is height divided by width. If the utilization factor is 1 it means the chip is square if it is something like 0.5 it means that the chip is a rectangle.
the next step is to define the locations of the preplaced cells. To understand what is a preplaced cell let us first assume that we have a combinational logic and that the combinational logic has some amount of function. like it is the multiplier half adder full adder etc. First, we will remove a part of our main circuit, cut it in half, and place the two pieces on a block. Finally, we will connect the two blocks using wires. Next, we will extend the IO pins. we will black box these boxes. Then we will separate the black boxes into different IP modules. Similarly, there are other IPs' also available for example we have Memory, Clock Gating Cells, comparator, mux, etc. The arrangement of these IPs' in a chip is referred to as Floorplanning. These IPs'/blocks have user-defined locations, and hence are placed in a chip before automated placement and routing and are called - pre-placed cells. Automated placement and routing tools place the design's remaining logical cells onto one chip. Once they are placed, their location is fixed they're permanent, The further steps will not touch their location. There is also one more important thing that we have to book which is to surround the preplaced cells with Decoupling capacitors. Consider capacitance to be zero for the discussion RDD, RSS, IDD, and LSS are well-defined values. During switching operation a circuit demands switching current which means peak current or "Ipeak", now due to the presence of RDD and LDD there will be a voltage drop across them, and the voltage at node A would be VDD' instead of VDD. If VDD' goes below the noise margin, due to RDD and LDD, the logic one at the output of the circuit won't be detected as logic one at the input of the circuit following this circuit.  
The next important step is to bind netlist with physical cells. We will give each component of the netlist their own dimensions. These are present in shelves and let us call that a library. A library can be of two types one that contains the shape and the other that contains the information.  A library is a place where the standard cells are kept. Standard cells contain gates like - and gate, or gate, buffer, inverter, dff, latch, ICG, flip flops, etc.
There are two types of transistors CMOS and NMOS, to create a CMOS transistor we first select the substrate is selected usually a P-type Substrate is selected The resistance is usually high in the range of 5~50 ohms With doping level of 10 to the power of 13 cm3. With the orientation of 100. Substrate doping should be less than 'well' doping. Then the next step is to select that active area for transistors. Firstly, we will create isolation between each socket, then  deposit a layer of Silicon dioxide Of about 40 nm Next we will deposit a layer of silicon nitride of about 80 nm.  Then, 1um of photoresist is deposited, which will create the MASK 1, Then it is treated with UV light, and then the silicon nitrate will be etched, Then the photoresist is removed through chemicals. It is placed into a furnace, and field oxide is grown, this process is called 'LOCOS' Or local oxidation of silicon. silicon nitrate is then removed with hot phosphoric acid. Then we will create a gate area. The P-well, N-well, and p-type     substrate is formed. This is how  a CMOS transistor is created.                                                                                                         

Clock tree synthesis is a crucial part of VLSI design. It consists of generating a network of clock distribution lines, which is known as the 'clock tree', to deliver the clock signal simultaneously and with the least and lowest skew to all sequential elements throughout the chip.

This process starts with defining clock requirements, which is then followed by generating a stratified network of clock lines then optimizing the clock tree to decrease skew, routing the clock lines, and verifying that the clock tree meets design requirements and timing constraints set by us.

Without clock tree synthesis, efficient clock distribution in VLSI designs cannot be guaranteed. It enables synchronous operation of sequential elements and ensures the design meets desired performance goals.
There is also a concept of H - Tree which calculates the middle of all its endpoints and originates a tree from that midpoint of all its endpoints.
For example let us say we have four flip flops flip flop one, flip flop 2, flip flop 3, and flip flop 4 they are placed in a square shape so the edge 3 syntheses will find the midpoint then it will reach the midpoint of flip flop 1 and 2 and then connect them same for flip flop 3 and 4 Show the clock reaches at every flip flop at the same time or almost at the same time, Show us skew Value will be zero or very close to zero. The clock will reach through real buffers, the connection is called a clock net. Also, the clock net is shielded so no glitch occurs and the net is not interfered.                                                                                                                                         
--Routing--
To Understand routing, let us say we have two points A and B and we have to connect A and B where A is the source and connect them in the best path with the least twists and turns. Twists and turns means zigzag lines, most of the lines should be in L shape.
There is an algorithm for this that understands to not put the lines in such a way, it was invented by Lee in 1961 and is called Lee's algorithm. It creates a grid in the backend called the routing grid, it with the points to be routed. The first step is does that it labels the adjacent grids and calculate the path. Any routing algorithm or engine always prefers the path with the least turns. This algorithm works by first creating a maze of   numbers and then calculating the path. This is slow, time-consuming, and requires a lot of memory as each data has to be stored. There are also some rules that need to be followed during routing. 

---OpenLane Labs---

Openlane is a tool tuned for 130nm cutting edge technology, first we will launch it then left click and select - "Open Terminal "  (Screenshot 2024-03-26 235512.png), then the terminal window will pop up; (Screenshot 2024-03-26 235359.png )
then will type in command line `ls` which means to list, then we will type `cd Desktop` cd means - change directory so this command line means to change the directory to Desktop, then `ls -ltr`, select tools using command line `cd tools`, then `ls -ltr`,` cd openlane_working_dir`, `cd openlane`, `ls -ltr`, then to run it in interactive mode we will type ethe command line `docker`,  a bash 4.2 text will appear in front, then type `./flow.tcl`
this will turn the terminal into interactive mode (Screnshot 2024-03-26 235925), the lines are in Screenshot 2024-03-27 000014.png 
------x------x------x------x-------x------x-----x-----x----x-----x----x----x
         Thank You, You Have Reached The End Of This Repository 
         Author : Athv Sharma
