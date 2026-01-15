PAN - Personal Area Networks (smallest widely-used form of network we have)
- Essentially the short range between your phone and bluetooth/wifi devices
LAN - Local Area Networks
WAN - Wide Area Networks
MAN - Metropolitan Area Networks
SAN - Storage Area Networks (Used for specialized, high-speed information storage and retrieval)

Difference between LAN and WAN is a little squishy. Depends on distance as main determinant. We use a change in technology to help the networks cover wider areas, helping distinguish between LAN and WAN.

MANs are city-sized networks, but a little difficult to run.

TCPIIP
- Application (7, 5)
- Transport (4)
- Internetwork (3)
- Network Access (2, 1)

ISO-OSI model
7 - Application
6 - Presentation
5 - Session
4 - Transport
3 - Network
2 - Data-Link
1 - Physical

Requests move down the layers from 7 to 1, with different devices processing at different layers.

Layers will always communicate with the corresponding layer on the other device it is communicating with.

**Application**
- What is used to interface with/create data
- Data Stream
**Presentation**
- Ensures data is in the proper format to be passed up to the application in a readable way
- Encryption and de-encryption takes place at this layer
- Data Stream
**Session**
- Initiates and ends a communication session
- Data Stream
**Transport**
- Manages the communications that are ongoing
- Takes the data stream and divides it into discreet chunks called **segments**. Chunks receive **Source** and **Destination** **Headers**. Ports are assigned, so that segments are delivered to the right location
**Network**
- IP Address Assigned 
**Data-Link**
- MAC Address Assigned (MAC does not change, but can be spoofed)
**Physical**
- Device has a physical address

MAC | IP | Ports | Segment
SD | SD | SD | DATA | FCS
|-------------Frame-------------|

Collision Sense Multiple Access with Collision Avoidance (CSMA/CA)
- Ethernet was built on this framework?

