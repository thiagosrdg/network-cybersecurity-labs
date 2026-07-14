# Glossary

Technical terms used throughout this repository, with brief
definitions for quick reference.

**Packet**
Unit of data transmitted on a network at the network layer (IP),
composed of a header and a payload.

**Frame**
Unit of data at the data link layer (e.g., Ethernet), which
encapsulates an IP packet for physical transmission on the network.

**Capture**
The process of intercepting and recording network traffic passing
through an interface, usually saved to a `.pcap` or `.pcapng` file.

**Protocol**
A set of rules that defines how data is formatted, transmitted, and
interpreted between devices on a network (e.g., TCP, DNS, HTTP).

**Port**
A number that identifies a specific service or application on a host,
used together with the IP address to address communications (e.g.,
port 443 for HTTPS).

**Socket**
The combination of an IP address and a port that uniquely identifies a
communication endpoint in a network connection.

**Payload**
The data actually carried by a packet or frame, excluding protocol
headers.

**Header**
The initial part of a packet or frame that contains control metadata
(addresses, flags, sizes, etc.), used by protocols to process the
communication.

**Three-way handshake**
The process of establishing a TCP connection, made up of the SYN,
SYN-ACK, and ACK steps.

**Retransmission**
The resending of a TCP segment whose acknowledgment (ACK) was not
received in time, indicating possible packet loss on the network.

**TTL (Time to Live)**
An IP header field that limits the number of hops a packet can travel
before being discarded, preventing infinite routing loops.

**DNS query**
A request sent by a client to a DNS server asking for a name to be
resolved (e.g., to an IP address).

**DNS response**
A response sent by a DNS server to a query, containing the resolution
result or an error code.

**Display filter**
A filter applied in Wireshark after capture, to show only packets that
match certain criteria, without altering the captured data.

**Capture filter**
A filter applied before or during capture, based on BPF syntax, that
determines which packets are actually captured and recorded.

**PCAP**
The traditional file format for storing network traffic captures.

**PCAPNG**
A more modern capture file format, successor to PCAP, with support for
multiple interfaces, comments, and additional metadata.

**Network forensics**
The area of information security focused on capturing, preserving, and
analyzing network traffic as evidence, with the goal of investigating
security incidents.

**Indicator of Compromise (IoC)**
Technical evidence (e.g., IP address, domain, traffic pattern) that
suggests malicious activity or a possible system compromise.
