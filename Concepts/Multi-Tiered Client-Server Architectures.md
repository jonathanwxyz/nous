#Distributed-Systems 
![[Pasted image 20230315203600.png]]
- Can split tasks between client and server in many different ways
- Typically can think of systems of this sort in 3 logical tiers, UI, Application business logic, Data
- Most typically and most simply, we just allocate UI to Client and rest to server


![[Pasted image 20230315203630.png]]
- A server may sometimes need to act as a client as seen above
- Splitting the logical components of the system onto different machines is called ==vertical distribution==