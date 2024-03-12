OSI:
	- Physique: bit/signal
		hub : sends to all in the bus 
		repeteur
		modem (modulation demodulation)
	- Link: crc controle erreur/flux , csma/cd ( collision detection ) , lan: multipoints -> mac / wan: point to point ppp (gateway , provider) (TRAME)
		switch : can send to one only destination using mac address
		bridge
		AP
	- Network: routage (PACKET)
	- Transport: QOS(latence?)
	- Session : synchronisation entre les apps
	- Presentation: representation de linfo 
	- App
ARP (between LINK & IP : trame) : @MAC de diffusion to send a trame to all :FF:FF:FF:FF:FF:FF : has to be renewed 
ipv4:
	{class A : last bit= 0: 0 ->127
	class B 10: 128 ->191 
	class C 110: 192 -> 223} UNICAST 
	class D 1110: 224 :MULTICAST(between broadcast and unicast)
	mask : left should always be 1
	reserved (0:network address(first), 255:broadcast address(last))
	plage dispo =(2^(nb bits machine))-2
	NAT: translate between private and public address , one way gate
	reserved addresses : 
		C: 192.168
		B: 172.\[16..31]
		A: 10.
port: 16 bits, 2bytes

| objet reseau | ID                                                               |
| ------------ | ---------------------------------------------------------------- |
| noeud        | IP                                                               |
| app reseau   | ( @IP, transportlayer, \#port )                                  |
| com reseau   | ( @IPsrc, transportlayersrc, \#portsrc ) ( @IPdest, \#portdest ) |

| CONFIGURATION |                                       |
| ------------- | ------------------------------------- |
| PC            | ip, mask, passarelle, route(auto)     |
| gateway       | interface(IP, mask), table de routage |
Routage: 
	static: by the admin
	dynamic: using protocols e.g.,RIP(routers shares their routing tables)
mask: /32 : select one specific address in routing table 
	/31 :cannot not be used 
	/30: used in wan ppp
CIDR: classless : we could divide the network or multiply it 

IP: max 64Kbyte 
link: max 1500byte
-> fragmentation

IP frame: 
	header min len :20bytes(4x5(HLEN))
TCP frame:
	Mode connecté(e.g, calls)
	piggy backing: data+acknowledgment in same frame
	ackn(receiver will send window size too)=seq+1 (from sender ) in bytes
	window size: data  number of bytes that can be sent without waiting for acknowledgment (buffer size in receiver) 
	connexion : 3way handshake
	deconnexion : 2 way handshake
tftp: udp / ftp: tcp
