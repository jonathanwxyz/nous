### What is it?
A logic controlled switch

### How does it work?
![[Pasted image 20221229130711.png]]
Made by combining a [[nMOS]] and a [[pMOS]] in parallel, utilising their special [[nMOS#^ddfedb|transmission characteristics]].

When ==control== is '0' both [[Transistor|transistors]] are off ('open switch'). when control is '1', both are switched on, causing input **p** to be connected to the output **q**.

By using complementary transistors we ensure that a binary 0 or 1 is efficiently transmitted through the switch (again, refer to their [[nMOS#^ddfedb|transmission characteristics]].

## Used in
- [[2-to-1 MUX]]