We may want a co-processor to offload computationally intensive tasks to dedicated hardware such as a unit for [[Floating Point Arithmetic]].
We can emulate everything that could be done on a co-processor on the main processor but it may be much much slower.

Here are a list of some popular coprocessors:
- [[Floating Point Unit (FPU)|FPUs]]
- [[Digital Signal Processor (DSP)|DSPs]]
- [[Graphics Processing Unit (GPU)|GPUs]]
- [[Machine Learning Accelerators|MLAs]]

Many coprocessors like maths and I/O coproccessors are transparent
- You just drop a coprocessor in and everything speeds up
- No need to rewrite anything

Some coprocessors like GPUs are not transparent, they're highly specific
- Code must be rewritten to target GPUs!
- Only graphics code is sped up transparently