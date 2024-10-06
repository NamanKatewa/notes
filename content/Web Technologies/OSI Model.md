**Open System Interconnection**

- Reference model that describes how information from a software application in one computer moves through a physical medium to the software application in another computer.
- Seven Layers. Each layer performs a particular network function.
- Each layer is self contained. The task assigned can be performed independently.

![[OSI Model.png]]

- Two layers - upper & lower
- **Upper Layer** - deals with application related issues.
- Implemented only in the software.
- **Lower Layer** - deals with data transport issues.
- Implemented in hardware & software.


# Physical Layer

![[Physical Layer.png]]
- Transmit individual bits from one node to another node
- Lowest layer
- Establishes, maintains and deactivates the physical connection
- Specifies mechanical, electrical & procedural network interface specifications

**Features -**
## Line Configuration

- Defines the way how two or more devices can be connected physically.

## Data Transmission

- Defines the transmission mode whether it is simplex, half-duplex or full-duplex

## Topology

- Defines the way how network devices are arranged

## Signals

- Determines the type of signal used for transmitting the info


# Data Link Layer

![[Data Link Layer.png]]
- Responsible for error-free transfer of data frames
- Defines the format of the data on the network
- Reliable & efficient communication between two or more devices.
- Responsible for unique identification of each device that resided on local network

## Logical Link Control Layer

- Transferring packets to the Network Layer of the receiver.
- Identifies the address of the network layer protocol from the header
- Provides flow control

## Media Access Control Layer

- Link b/w Logical link control layer & network's physical layer
- Transferring packers over the network


**Features -**

## Framing

- Translates bits into packets known as **Frames**.
- Adds the header & trailer to the frame.
- Header contains hardware destination & source address
![[Data Link Framing.png]]

## Physical Addressing

- The frame is transmitted to the destination address mentioned in the header

## Flow Control

- Constant data rate is maintained on the both (receiving & sending) sides, to ensure no corruption.
- Ensures transmitting station's (sender) speed does not exceed receiving station's (receiver) speed.

## Error Control

- Adding a calculated value. **CRC** (Cyclic Redundancy Check)
- Placed in the trailer
- If error occurs, then receiver sends acknowledgement for retransmission of corrupted frames.

## Access Control

- Two or more devices connected, this determines which device has control over the link and when.


# Network Layer

![[Network Layer.png]]
- Manages device addressing, tracks the location of devices
- Determines the best path to move data from source to destination. Based on network conditions, priority, etc.
- Responsible for routing & forwarding the packets
- Routers are an example of this Layer.

**Functions -**

## Internetworking

- Provides a logical connection between different devices.

## Addressing

- Adds source & destination to the header of the data packets. Used to identify the device on the internet

## Routing

- Determines the optimal path out of multiple paths from source to destination

## Packetizing

- Receives packets from the upper layer & convert them into packets


# Transport Layer

![[Transport Layer.png]]
- Ensures messages are transmitted in the order in which they are sent, an no duplication.
- Transfer the data completely
- Converts data into smaller units called **segments**.

**Protocols in use -**
TCP & UDP (Refer [[TCP IP]])

**Functions -**

## Service-point addressing

- Transmission of data from one computer to another computer & even from the correct process of a computer to the correct process of another computer.
- Adds a header that contains the port address or **service-point address**

## Segmentation & Reassembly

- Divides message into multiple segments.
- Each segment is assigned with a sequence number identifying the segment
- It gets reassembled on receiving

## Flow Control

- End-to-end flow control rather than across single link

## Error Control

- Error control is also performed end to end instead of across single link.


# Session Layer

![[Session Layer.png]]
- Establish, maintain and synchronize the interaction b/w communicating devices

**Functions -**

## Dialog Control

- Created a dialog b/w two processes.
- Half-duplex or full-duplex

## Synchronization

- Adds checkpoints when transmitting data in a sequence.
- If error occurs, then the transmission resets from the checkpoint
- **Synchronization & Recovery**


# Presentation Layer

