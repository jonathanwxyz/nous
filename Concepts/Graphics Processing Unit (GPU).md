![[Pasted image 20221228111932.png]]


### Best tasks for a GPU
Good for doing millions of the same calculation on different data
- graphics
- matrix multiplication
- FTT
Good for easily parallelisable computations and [[Floating Point Arithmetic]]

- Computation Intensive
- Many independent computations
- Many similar computations

### GPU vs CPU
> #### Why not have thousands of [[Arithmetic Logic Unit (ALU)|ALUs]] in a [[Central Processing Unit (CPU)|CPU]]?
> Because we have other constraints!
> - Not enough space for instance

| |GPU| CPU|
|---|----|---|
|**Execution Units**|Many parallel execution units | Few execution units but higher clock speeds|
|**Pipelines**|Much deeper pipelines, hundreds of stages| 10-20|
|**Memory Interfaces**|Significantly faster and more advanced memory interfaces, need to shift around a lot more data| Simpler|
|**[[Latency]]**|Can tolerate higher latency (order of milliseconds)| Designed to minimise latency, e.g mouse and keyboard<br /> To achieve this:<br /> - cache<br />for out of cache ops:<br /> - instruction pre-fetch<br /> - out-of-order execution, flow control|
|**[[Bandwidth\|Throughput]]**|Maximise throughput i.e processing millions of pixels at a time|Doesn't need to be as parallel|
|**Cache**|Doesn't need large amounts of cache. Dedicate more transistor area to computation horsepower|Needs large Cache|

#### Summary
- [[Central Processing Unit (CPU)|CPUs]] are low latency (latency intolerant), low throughput processors
- GPUs are high latency (latency tolerant), high throughput processors
- GPUs can have more [[Arithmetic Logic Unit (ALU)|ALUs]] for the same sized chip and therefore run many more threads of computation
- Modern GPUs run 10,000s of threads concurrently
- CPUs are task parallel, GPUs data parallel
	- Multi threaded cores vs SIMT (Single Instruction Multiple Thread) cores
	- 10s of threads vs 10,000s of threads

![[Pasted image 20221228121212.png]]

### Properties of GPUs
- Special Purpose requirements
	- Latency tolerant
	- Data parallel
	- (potentially) thousands of threads
- Streaming data
	- Not reused - low amount of cache
	- Can [[Direct Memory Access (DMA)|DMA]] in blocks of DRAM
- Can use synchronous threads - no need for waiting and interlocking
	- Synchronisation handled at a higher level
- Much responsibility for correct function transferred to software e.g
	- Memory (cache) coherency
	- Thread synchronisation
 - Can measure performance in [[Floating Point Operations Per Second (FLOPS)|FLOPS]]

### Discrete and Integrated GPUs
|Discrete|Integrated|
|---|---|
|More Computational Power| Less|
| More Memory Bandwidth| Less|
| Uses more power| More power efficient|


### General Purpose GPU (GPGPU)
- GPUs can be used for general purpose computing
- Most appropriate for tasks where parallelism is appropriate and latency is not an issue
	- e.g bioinformatics
- Processing can be maintained without the need for large caches
- Some language 'platforms' have developed for this:
	- CUDA (Compute Unified Device Architecture) by NVIDIA
	- Direct Compute by Microsoft
	- Open Computing Language (OpenCL) by Khronos Group (open)
- CPUs can be 10x+ faster than GPUs for sequential parts of code
- GPUs can be 10x+ faster than CPUs for parallel code
- So right hardware for right application!
	- heterogeneous computing
		- This is the norm on mobile computers like iPhones


