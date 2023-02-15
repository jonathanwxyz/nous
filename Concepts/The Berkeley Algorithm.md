### What is it?
Similar to [[Cristian's Algorithm]], but there's a ==master== server process which periodically polls other ==slave== processes.

The [[Clock Synchronisation]] method used in this algorithm, the average, cancels out individual clocks' tendencies to drift.

### Algorithm
1. A master is chosen via an election process such as the Bully Algorithm.  
2. The master polls the slaves who reply with their time in a similar way to Cristian’s algorithm.
3. The master observes the round-trip time (RTT) of the messages and estimates the time of each slave and its own.
4. The master then averages the clock times, ignoring any values it receives far outside the values of the others.
5. Instead of sending the updated current time back to the other process, the master then sends out the amount (positive or negative) that each slave must adjust its clock. This avoids further uncertainty due to RTT at the slave processes.