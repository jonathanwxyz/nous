- Extensions on ISAs
- Allows for parallel execution at runtime
- A superscalar processor can execute more than one instruction during a clock cycle by simultaneously dispatching multiple instructions to different execution units of a processor.
- e.g Intel MMX and ARM NEON
- Combined with [[Single Instruction Multiple Data (SIMD)|SIMD]] instructions we get additional performance gains
- Break up 32 bit registers into vectors, specified by particular instructions:
![[Pasted image 20221227165352.png]]
- ARM NEON
![[Pasted image 20221227165611.png]]