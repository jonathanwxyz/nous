**Related:** [[nMOS]], many things discussed here are opposite for the nMOS

> ### positive-Metal-Oxide-Semiconductor

### Summary
A positive-MOS transistor forms an open circuit when receiving a non-negligible voltage.

### Symbols
![[Pasted image 20221229113512.png]]

### What is it?
It is a type of [[Transistor|transistor]] used in [[CMOS Circuit]]s.

### How does it work?
![[Pasted image 20221229115107.png]]
**D** - Drain
**S** - Source
When we apply '1' to the ==**gate terminal**==, the channel is non conducting ('the switch is off/open'). This is referred to as a high impedance state.
There is a ==**threshold voltage**== where the channel will become conducting ('the switch is on/closed').

### Transmission Characteristics
^5c61c1
![[Pasted image 20221229130420.png]]
When conducting ('0' applied to the gate terminal), the pMOS is a poor conductor of '0's but a good conductor of '1's and thus transmits better. So if we connect a digital '1' to the drain then a strong '1' will be seen at the output, for '0' a weak '0' will be seen. This is opposite to the [[nMOS#^ddfedb|nMOS]].
Using these properties of nMOS and pMOS a [[Transmission Gate]] can be constructed