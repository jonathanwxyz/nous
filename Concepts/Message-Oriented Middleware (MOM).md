#Distributed-Systems 

### What is it?
A way of passing messages between processes that ==persistent asynchronous communication==, by employing ==message-queuing== between the sender and receiver.

As such, message-queuing systems offers intermediate-term storage capacity for messages, without requiring either the sender or receiver to be active during message transmission.

Applications communicate by inserting messages in specific queues which are then forwarded until eventually delivered to the destination.
- A sender is generally given only the guarantees that its message will eventually be inserted in the recipient’s queue.
- Message-queuing systems are often used to assist the integration of dispersed collections of databases as well as in publish-subscribe systems.