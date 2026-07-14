# Protocol Reference

Summary of the main protocols used in the labs in this repository,
focused on the aspects relevant to traffic analysis.

## Ethernet

Data link layer protocol responsible for physical addressing (MAC) and
encapsulating packets for transmission on local networks. Relevant
fields: source/destination MAC address, EtherType.

## ARP (Address Resolution Protocol)

Protocol used to associate IP addresses with MAC addresses on a local
network. Basically composed of requests (*who-has*) and replies
(*is-at*). Frequently analyzed in ARP spoofing investigations.

## IPv4

Network layer protocol responsible for logical addressing and packet
routing. Relevant fields: source/destination IP address, TTL,
encapsulated protocol, fragmentation flags.

## IPv6

Successor to IPv4, with an expanded address space (128 bits) and
simplification of some header fields. Uses addresses such as
`fe80::/10` (link-local) and routable global prefixes.

## ICMP (Internet Control Message Protocol)

Protocol used for network diagnostics and error reporting (e.g.,
`ping`, destination unreachable messages, time exceeded). It is not
connection-oriented and has no ports.

## TCP (Transmission Control Protocol)

Connection-oriented transport layer protocol responsible for
guaranteeing reliable, ordered data delivery. Uses the *three-way
handshake* (SYN, SYN-ACK, ACK) to establish connections and has
mechanisms for flow control, retransmission, and graceful (FIN) or
abrupt (RST) termination.

## UDP (User Datagram Protocol)

Connectionless transport layer protocol, simpler and with less
overhead than TCP. Does not guarantee delivery, order, or flow
control. Used by protocols such as DNS and latency-sensitive services.

## DNS (Domain Name System)

Protocol responsible for resolving domain names into IP addresses (and
vice versa). Typically operates over UDP on port 53 (with fallback to
TCP for larger responses). Basic structure: queries and responses,
with different record types (A, AAAA, CNAME, MX, among others) and
return codes (e.g., `NOERROR`, `NXDOMAIN`).

## HTTP (Hypertext Transfer Protocol)

Application layer protocol used for web communication, based on
requests and responses. Typically operates over port 80, in plain
text — which is why credentials and sensitive data should never travel
over HTTP without encryption (see
[Lab 04](../labs/04-http-traffic-analysis/README.md)).

## HTTPS/TLS

HTTPS is HTTP running over a TLS encryption layer, typically on port
443. TLS establishes an encrypted session through a handshake (*Client
Hello*, *Server Hello*, certificate and key exchange) before
application data is transmitted. Without the session keys, the content
of the communication is not readable in the capture — only the
handshake metadata.

## DHCP (Dynamic Host Configuration Protocol)

Protocol used for automatically assigning IP addresses and other
network settings to hosts on a local network. Typically follows the
*Discover, Offer, Request, Ack* (DORA) flow, operating over UDP on
ports 67 and 68.
