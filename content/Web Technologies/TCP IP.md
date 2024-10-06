- Developed before [[OSI Model]]
- Five Layers - **Application**, **Transport**, **Network**, **Data Link**, **Physical**
- Hierarchical protocol made up of interactive modules.
- Each module provides specific functionality
- Each upper-layer is supported by two or more lower-level protocols

![[TCP IP.png]]


# Network Access Layer

- Lowest layer of the TCP/IP model
- Combination of Physical & Data Link layer
- Defines how the data should be sent physically through the network
- Mapping the IP address into physical addresses.
- IP Datagram into frames
- Protocols used - Ethernet, Token Ring FDDI, Frame Relay

# Internet Layer / Network Layer

- Second Layer
- Send packets from any network.
- Protocols used -

## IP

### IP Addressing
- Logical host addresses
- Used by internet & higher layers to identify the device & provide routing

### Host to Host Communication
- Determines the path through which data is to be transmitted

### Data Encapsulation & Formatting
- Accepts the data from Transport Layer.
- Ensures data is sent & received securely.
- Encapsulate data into message known as IP datagram

### Fragmentation & Reassembly
- Limit imposed on the size of IP datagram by data link layer is called **MTU** Maximum Transmission Unit.
- If size of IP Datagram is greater than MTU, IP protocol splits datagram into smaller units
- Fragmentation can be done by the sender or intermediate router.
- Receiver's side all the fragments are reassembled to form the message.

### Routing
- IP Datagram sent over LAN, MAN, WAN -> Direct Delivery
- Source & Destination are on distant network, then IP Datagram is sent indirectly
- Accomplished by routing the IP Datagram through devices such a router


## ARP

**Address Resolution Protocol**

- Used to find the physical address from IP address
- **ARP Request** - Sender wants to know the physical address of the device. It broadcasts the ARP request to the network.
- **ARP Reply** - Every device attached to the network will accept the ARP request & process the request, but only recipient recognize the IP address and sends back its physical address in form of ARP reply.
- Recipient adds the physical address both to its cache memory & datagram header

## ICMP

**Internet Control Message Protocol**

- Used by hosts or router to send notifications regarding datagram problems back to the sender.
- A datagram travels from router to router until it reaches its destination
- If a router is unable to route the data because of some reasons. Such as disabled links, device is on fire, network congestion, etc. This protocol informs the sender that datagram is undeliverable
- **ICMP Test** - test whether the destination is reachable
- **ICMP Reply** - check whether the destination device is responding or not
- The core is to report the problems, not correct them. Correction is the job of the sender
- Can only send messages to the source, but not intermediate routers. Because datagram doesn't have that info.


# Transport Layer
- Responsible for reliability, flow control, correction of data.

## UDP

**User Datagram Protocol**

- Connectionless Service
- End-to-end delivery of transmission
- Unreliable protocol, as it discovers errors, but cannot specify them
- UDP discover the error. ICMP reports the error to the sender.
- **Source Port Address** - Address of the application program that created the message
- **Destination Port Address** - Address of the application program that receives the message.
- **Total Length** - Total number of bytes the user datagram is
- **Checksum** - 16-bit field used in error detection
- Does not specify which packet is lost.

![[UDP.png]]
![[UDP Header Format.png]]

## TCP

**Transmission Control Protocol**

- Creates a virtual circuit between sender & receiver, and active for the duration of the transmission
- Reliable protocol
- Detects the error, retransmits the damaged frames.
- Ensures all segments are received & acknowledged before the transmission is considered complete
- At the sender, TCP divides the message into smaller units known as **segment**.
- Each segment contains sequence number for reordering to form the original message.
- At the receiving end, TCP collects all segments and reorders them based on sequence number.


# Application Layer

- Top most layer
- High-level handling protocols, issues of representation
- Allows user to interact with the application
- When communicating b/w applications, they forward their data to the transport layer.

## HTTP

**Hypertext Transfer Protocol**

- Access data over WWW . It transfers the data in the form of plain text, audio, video.
- Efficiency to use in a hypertext env, rapid jumps from one document to another

## SNMP

**Simple Network Management Protocol**

- Used for managing the devices on the internet

## SMTP

**Simple Mail Transfer Protocol**

- Support e-mail.
- Used to send data to another email address

## DNS

**Domain Name System**

- IP address is used to identify the connection of a host to the internet.
- But, people prefer to use names, instead of addresses.
- This maps the names to addresses.

## TELNET

**Terminal Network**

- Establishes the connection b/w local computer and remote computer, in such a way that the local terminal appears to be a terminal at the remote system

## FTP

**File Transfer Protocol**

- Standard for transferring files from one computer to another