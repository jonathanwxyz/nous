This [[Logical Clocks|logical clock]] is useful for [[Distributed System Synchronisation]]. It assumes each processor $i$ has a Logical Clock, LCi.

1. When an event occurs on processor i, LCi is incremented by one.
2. When processor X sends a message to Y, it also sends its Logical Clock, LCx. 
3. When Y receives the message, if its local Logical Clock is already in advance of the clock it has just received plus one timestep, it keeps its current Logical Clock, otherwise it sets its local Logical Clock to be the one it has just received plus one timestep, i.e.:
```python
if LCy < (LCx + 1):  
	LCy = LCx + 1
```

### Notes on Lamport's Logical Clock
1. the receipt of a message forces the recipient to move its clock forward so that the ==“happened after” relationship is preserved== at that point.  
2. ==if a -> b then it is true that LCa < LCb==. But it is not necessarily true that just because LCa < LCb then a -> b. This means that ==we cannot infer a causal relationship just by looking at timestamps==.  
3. by using logical clocks, we can obtain a ==basic partial ordering of events==, i.e., we can tell that one event happened after another one, but ==we do not obtain a perfectly synchronised global time.==