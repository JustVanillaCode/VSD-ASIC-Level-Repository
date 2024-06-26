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


Openlane is a tool tuned for 130nm cutting-edge technology, first, we will launch it then left-click and select - "Open Terminal "![Screenshot 2024-03-26 235359](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/1cd42941-300e-43b8-83ee-974acc62069b), then the terminal window will pop up; 
![Screenshot 2024-03-26 235512](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/a7f58aab-b989-430c-8540-656e3127b0a3)

then will type in the command line `ls` which means to list, then we will type `cd Desktop` cd means - change directory so this command line means to change the directory to Desktop, then `ls -ltr`, select tools using command line `cd tools`, then `ls -ltr`,` cd openlane_working_dir`, `cd openlane`, `ls -ltr`, then to run it in the interactive mode we will type the command line `docker`,  a bash 4.2 text will appear in front, then type `./flow.tcl -interactive`
this will turn the terminal into interactive mode ![Screenshot 2024-03-26 235925](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/e8d42fdd-f9ca-4d8a-98f1-2bf5aad087a4), the lines are below are the commands ![Screenshot 2024-03-27 000014](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/a8bddc4a-f3f4-4728-a040-ed2147e5fd98), then we will type `package require openlane 0.9`, `prep design picorv32a` to merge the lef files 
![Screenshot 2024-03-27 145202](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/4d5ea6af-0ceb-490a-a9c9-3229f8250283)
then when we check, a runs directory will be created. Inside the directory, a folder with today's date will be created ![Screenshot 2024-03-27 145814](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/f2a8af54-b20a-4685-8891-d74f16811667)
![Screenshot 2024-03-27 145754](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/10c47a59-ea98-42f7-849a-876e94244569), the next step is to  type `prep -design picorv32a`, after that we will run synthesis using the `run_synthesis` after some time, it will show ![Screenshot 2024-03-27 150726](https://github.com/JustVanillaCode/VSD-ASIC-Level-Repository/assets/162819270/1ca2bc8e-111c-4100-93e3-c453ed6825f5) to show that the synthesis was successful. Now we will characterize the synthesis results 

 Now we can run TritonCTS by the `run_cts` command followed by `run_routing` to run routing, `run_magic`, `run_magicspice_export`, `run_magic_drc`, `run_netgen` then lastly `run_magic_antenna_check`.*To run Magic simulation, use the `Magic -T` command. 
This was the complete flow in labs, we ran it in interactive to run and understand each step, else the entire flow would have been executed and implemented in one go together.  
