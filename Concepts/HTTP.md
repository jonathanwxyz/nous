#Distributed-Systems 

### What is it?
- The HyperText Transport Protocol (HTTP) is a [[Protocols|protocol]] which provides a specification (vocab) that allows client applications to request resources from ==web servers==, and web servers to respond to these requests

### HTTP 'verbs'
An incomplete list of 'verbs' used by client applications and web servers when communicating via HTTP over the internet:

|HTTP verbs|Description|
|---|---|
|HEAD|Asks for the response identical to the one that would correspond to a GET request, but without the response body. This is useful for retrieving meta-information written in response headers, without having to transport the entire content.|
|GET|Requests a representation of the specified resource. Requests using GET should only retrieve data and should have no other effect.|
|POST|Submits data to be processed (e.g., from an HTML form) to the identified resource. The data is included in the body of the request. This may result in the creation of a new resource or the updates of existing resources or both.|
|OPTIONS|Returns a list of the commands supported by this particular server.|
|DELETE|It is used to delete a resource. It may return the a representation of the removed resource.|

### Stateless
- Web servers that follow the HTTP protocol are said to be ==stateless==
	- Once a request from a client is fulfilled, the web server ==disconnects from the client and 'forgets' that the client ever connected==
- Allows for the system to treat each request for content as an ==independent transaction== that can be completed
- There are ways of preserving state information outside of the scope of the protocol but encoded into applications and servers that use it