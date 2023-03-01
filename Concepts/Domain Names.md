#Distributed-Systems 

### Why was it created?
Domain Names were created because humans find IP addresses hard to read and remember.

### What is it?
- The Domain Name System (DNS) is itself a [[Distributed System]] built on top of the Internet, used to ==create associations between human-readable names and IP addresses==.
	- for example www.bbc.co.uk will be 'translated' into an IP address
- It consists of a hierarchy of servers with the most authoritative server at the ‘top’ of the hierarchy, dealing with requests from users.
	- When the most authoritative fails it must fall back to other servers
	- ![[Pasted image 20230224152809.png]]
 - Complex delegation system
	 - for example .co.uk is meant to be for UK based companies
	 - .com is meant to be for companies, .org for organisations
	 - however this is very loose as anyone can generally get any domain

### Comparison to IP and MAC Addresses
- Unlike MAC and IP addresses, DNS cannot allocate ‘batches’ of names up-front, and needs to respond in real-time to requests to translate names into IP addresses.
	- As in the IP address for google couldn't be automatically translated into a Domain Name because what is an intuitive name has to be decided by people, so the IP address was only translated to google.com once people at google requested it from the DNS