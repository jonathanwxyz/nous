**Related:** [[pMOS]], many things discussed here are opposite for the pMOS

> ### negative-Metal-Oxide-Semiconductor

### Summary
A negative-MOS transistor forms a closed-circuit when receiving a non-negligible voltage.

### Symbols
![[Pasted image 20221229113424.png]]

### What is it?
It is a type of [[Transistor|transistor]] used in [[CMOS Circuit]]s.

### How does it work?
![[Pasted image 20221229115031.png]]
**D** - Drain
**S** - Source
When we apply '0' to the ==**gate terminal**==, the channel is non conducting ('the switch is off/open'). This is referred to as a high impedance state.
There is a ==**threshold voltage**== where the channel will become conducting ('the switch is on/closed').

### Transmission Characteristics

^ddfedb

![[Pasted image 20221229122746.png]]
When conducting ('1' applied to the gate terminal), the nMOS is a poor conductor of '1's but a good conductor of '0's and thus transmits better. So if we connect a digital '0' to the drain then a strong '0' will be seen at the output, for '1' a weak '1' will be seen. This is opposite to the [[pMOS#^5c61c1|pMOS]].
Using these properties of nMOS and pMOS a [[Transmission Gate]] can be constructed