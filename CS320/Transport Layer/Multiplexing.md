# Connectionless Demultiplexing
- when creating socket, must specify *host-local* port number
- when creating datagram to send into [[UDP]] socket, must specify
	- destination IP address
	- destination port number
- when receiving host recieves UDP segment
	- checks destination port number in segment
	- directs UDP segment to socket with that port number
- 