
### Introduction to IP
![[]]![[Pasted image 20240303154948.png]]


TCP and UDP add additional capabilities that IP can’t provide. For example, these provide multiplexing so that you can have many different applications on your system communicating to a separate server all simultaneously.

##### TCP- Transmission Control Protocol
Connection Oriented - Has a setup where a system is used to send and receive data.
Has flow control - Can regulate the speed and flow of data being transmitted.
Has reliable delivery - Can recover from errors and manage messages that are sent out of order.
Connection Oriented Protocols - HTTPS (Hypertext Transfer Protocol Secure), SSH (Secure Shell). These Connection Oriented Protocols prefer a return receipt.
##### UDP - User Datagram Protocol
Connectionless - No system to set up a form of traffic flow. Simple transaction that can be sent from one device to another.
Has Unreliable Delivery - Does not have the capability to reorder data that has been sent. Does not have error recovery. Used for use cases like phone calls that require real-time transmission of data. 
Connectionless Protocols - DHCP (Dynamic Host Configuration Protocol), TFTP(Trivial File Transfer Protocol)

Non-ephemeral ports = permanent port numbers - Ports 0-1,023, Usually server or a service
Ephemeral ports = temporary port numbers - Ports 1024-65,535, Used and disposed and determined in real-time by the client.

TCP and UDP can use any ports between 0 and 65,535.

TCP and UDP usually use different ports, so there can be a TCP connection from port 80 and a UDP connection from port 80 but since it is confusing it is not used most of the time.

![[Pasted image 20240303162416.png]]

### Common Network Ports

#### Port Number - Protocol - How the Protocol is Used
##### FTP: File Transfer Protocol
> tcp/20 (active mode data)
> tcp/21 (control)
- Transfers files between systems
Authenticates with a username and password

##### SSH: Secure Shell
> tcp/22
- Encrypted communication link
Views with plaintext and a terminal/console interface but the communication that is sent and received is encrypted.
Looks and acts like Telnet.

##### Telnet: Secure Shell
> tcp/23
- Console access
Views with plaintext and a terminal/console interface but the communication that is sent and received is NOT encrypted.

##### SMTP: Simple Mail Transfer Protocol
> tcp/25
- Server to server email transfer.
- Also used by clients to send mail to a mail server.
- Used to SEND mail.
Views with plaintext but the communication that is sent and received is NOT encrypted.
Clients receiving email use the IMAP and POP3 protocols. 

##### DNS: Dynamic Name Server
> udp/53
- Converts names to IP addresses

##### DHCP: Dynamic Host Configuration Protocol
> udp/67
> udp/68
- Automated configuration of IP address, subnet mask and other options.
- Requires a DHCP server
Server, appliance, integrated into a SOHO router, etc.
IP addresses are taken from a pool of IP addresses and assigned in real time. These IP addresses that are assigned each have a lease and must renew at the expiration of their lease that is set at different intervals.
Addresses are assigned by the MAC address in the DHCP server
DHCP Server manages and updated the IP address of each device. 

##### HTTP & HTTPS: Hypertext Transfer Protocol
> tcp/80 - Hypertext Transfer Protocol (Web server communication)
> tcp/443 - Hypertext Transfer Protocol Secure (Web server communication with encryption)
- Communication in the browser and by other applications to web servers.
Sends data in the clear (HTTP) or encrypted (HTTPS).

##### POP3 / IMAP: Hypertext Transfer Protocol
> tcp/110 - POP3: Post office Protocol version 3
- Basic mail transfer functionality.
> tcp/143 - IMAP4 - Internet Message Access Protocol v4
- Includes the management of email inboxes from multiple clients. 
Both receive emails from an email server

##### NetBIOS: Network basic Input/Output System
> udp/137 - NetBIOS name services (nbname)
> tcp/139 - NetBIOS session services (nbsession)
- Protocol used by Microsoft Windows also called CIFS (Common Internet File System)
> tcp/455 - NetBIOS-less
- More commonly used in the modern world which allows direct SMB communication over TCP without the NetBIOS transport.

##### SNMP: SImple Network Management Protocol
> udp/161 - Queries: Allows a network management device to query network infrastructure devices and get back performance details.
> udp/162 - Traps: Allows the network infrastructure devices to send out alerts to the network management device.
- v1 structured tables but unencrypted
- v2 structured tables with datatype enhancements, bulk transfers but still unencrypted
- v3 upgrade from v2 but with security like message integrity, authentication and encryption. 
Use v3 for any use because it only secure.

##### LDAP: Lightweight Directory Access Protocol
> tcp/389
- Store and retrieve information in a network directory.
Commonly used in Microsoft Active Directory

##### RDP: Remote Desktop Protocol
> tcp/3389
- Share a desktop from a remote location
Available in many different versions of Windows. Clients are available on macOS, Linux, Unix, iPhone, Android and others.
### Network Devices

##### Router: 
>Routes traffic between different IP subnets.
- Makes forwarding decisions based on IP address
- Routers inside of switches sometimes called "layer 3 switches"
> Often connects diverse network types
- LAN, WAN, copper, fiber

##### Switch : 
> Bridging done in hardware
- Makes forwarding decisions based on MAC address
- Does the data forwarding at very high speeds because it is all done in the hardware. It uses Application-specific integrated circuit (ASLC).
> Many ports and features
- The core of an enterprise network
- May provide Power over Ethernet (PoE)
> Multilayer switch aka Layer 3 Switch
- Includes routing functionality

##### Unmanaged Switch : 
- Very few configuration options - Plug and play
- Fixed configuration - No VLANs
- Very little integration with other devices - No management protocols
- Low price point - Simple is less expensive
##### Managed Switch : 
- VLAN support - Interconnect with other switches via 802.1Q
- Traffic prioritization - Voice traffic gets a higher priority
- Redundancy support - Spanning Tree Protocol (STP)
- Port mirroring - Capture packets
- External management  - Simple Network Management Protocol (SNMP)

##### Access point: 
> Not a wireless router
- A wireless router is a router and an access point in a single device
> An access point is a bridge
- Extends the wired network onto the wireless network
- Makes forwarding decisions based on MAC address

##### Patch panel: 
- Combination of punch-down blocks and RJ-45 connectors
- Runs from desks are made once - Permanently punched down to patch panel 
- Patch panel to switch can be easily changed - No special tools, Use existing cables

##### Firewalls: 
> Filters traffic by port number
- OSI layer 4 (TCP/UDP)
- Some firewalls can filter based on the application
>Can encrypt traffic into/out of the network
- Protect your traffic between sites.
> Can proxy traffic
- A common security technique where the firewall does the browsing for you and then returns the content of it is safe.
>Most firewalls can be layer 3 devices (routers)
-  Usuallv sits on the ingress/egress of the network