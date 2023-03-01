#Distributed-Systems 

### What is it?
- The Media Access Control (MAC) address is a ==unique identifier given to each network device in a system==: this means that every ethernet or wifi card in a computer has one MAC address.
	- Devices often have multiple MAC addresses
		- It's a 48 bit number so plenty of addresses
- Consists of 2 parts:
	- ==Organisationally Unique Identifier== (OUI)
		- A 24 bit number purchased from IEEE, which acts as a central authority that hardware vendors can purchase unique identifiers from
	- ==Network Interface Controller== (NIC)
		- Once a vendor has an OUI, so long as the vendor makes sure the NIC is unique (internally) then the resulting MAC address will be unique
- 