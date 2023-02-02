### What is it?
- FPGAs can be seen as a target technology  
	- (like ASICs, discrete logic gates etc.)  
- FPGAs can be seen as a processing device  
	- (like a [[Central Processing Unit (CPU)|CPU]], [[Graphics Processing Unit (GPU)|GPU]], [[Digital Signal Processor (DSP)|DSP]], etc.)  
- FPGAs themselves are CHIPs (and consequently ASICs) that can be reprogrammed to host any digital circuit (only limited by the device capacity)
- Allow customisation of hardware to a problem
### How does it work?
#### Logic
![[Pasted image 20221228143646.png]]
LUTs are the basic building blocks
Look up tables can be loaded in, to gain the desired behaviour by emulating [[Logic Gates|logic gates]]
##### Advantages
- convenient  
- access time: constant  
- can be high-precision  
##### Disadvantages
- can get very big  
- does not scale well

#### Routing
The routing is implemented with multiplexers (like a switch)
![[Pasted image 20221228144135.png]]

#### FPGA Fabric
Example of an FPGA fabric composed of LUTs, switch matrices and  
I/O cells. Other common primitives: memories, multipliers, transceivers, ...
![[Pasted image 20221228144214.png]]

### Cost of programmability
- Software (CPU): might provide 100 possible instructions, but only one fired in each operational cycle  
- Hardware (FPGA): not all blocks are usable, interconnection network (for wiring logic cells) is pure overhead.  
- If we compare (non-programmable) ASIC with (programmable) FPGA technology (considering same process technology):  
	- 18 x in area  
	- 3-4 x slower  
	- 5-10 x more power  
	- However, FPGAs are mass produced in most advanced process technologies 
		- -> low cost (for lower volumes), reasonable power/performance  
	- Remember: # transistors (area) is a minor issue today  
- Re-programmability allows better utilization of the real estate
- Some microarchitectural structures would be very expensive to be implemented from LUTs  
	- Multipliers (would otherwise cost one LUT per product of input  
	operand bits (Na x Nb)  
	- RAM blocks (we would otherwise have only the LUT Flops)
 
**Important:  
For benchmarking, don’t compare algorithms, but problems!  
Different target technologies (CPU, GPU, FPGA) allow different  
optimisations.**
### FPGA vs CPU vs GPU
![[Pasted image 20221228145901.png]]
The pipelining approach FPGAs might take to running multiple operations on data often leads to better efficiency
![[Pasted image 20221228150010.png]]
As can be seen, the FPGA can be more efficient than [[Graphics Processing Unit (GPU)|GPUs]]

#### When to use each?
- [[Central Processing Unit (CPU)|CPUs]] - good for control dominant problems (if-else, case statements)
	- e.g OS, GUIs, Complex state machines
	- Good for a large variety of tasks
	- Can rapidly change the executed program
 - [[Graphics Processing Unit (GPU)|GPUs]] - good for data parallel problems that can be vectorised (for using the [[Single Instruction Multiple Data (SIMD)|SIMD]] units)
	 - For problems that need only little control flow and synchronisation with other threads or tasks (video processing)
	 - [[Floating Point Arithmetic|Floating point number crunching]]
- FPGAs: can work as a CPU and/or GPU (with some penalty)  
	- Outstanding performance on stream processing problems and whenever pipelining can be applied on large data sets  
	- Allow tight synchronization of processing and data movement
		- e.g., we might decompress a video stream using only on-FPGA resources while streaming the result over to various further video acceleration modules without ever needing off-chip communication
	- Customized data types  
	- Brilliant in bit fiddling operations (e.g., compression, crypto)  
	- Configuration can change circuit slowly (ms)
- No clear winner
	- Heterogeneous computing!

### Examples of FPGA use
##### Using DSP blocks on the FPGA
![[Pasted image 20221228151729.png]]
Allows us to optimise the number of operations required
##### Multiplexer
![[Pasted image 20221228151829.png]]
