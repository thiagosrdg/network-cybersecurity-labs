# Wireshark Display Filters

Display filters are applied **after capture**, in Wireshark's filter
bar, to show only the packets relevant within an already-completed
capture. They do not reduce what is captured, only what is displayed.

For the difference between display filters and capture filters, see
[wireshark-capture-filters.md](wireshark-capture-filters.md).

## Ethernet

| Filter | Description |
|---|---|
| `eth.addr == aa:bb:cc:dd:ee:ff` | Shows frames with the given MAC (source or destination). |
| `eth.src == aa:bb:cc:dd:ee:ff` | Shows frames with the given source MAC. |
| `eth.dst == aa:bb:cc:dd:ee:ff` | Shows frames with the given destination MAC. |
| `eth.type == 0x0800` | Shows Ethernet frames carrying IPv4. |

## ARP

| Filter | Description |
|---|---|
| `arp` | Shows all ARP traffic. |
| `arp.opcode == 1` | Shows ARP requests (*who-has*). |
| `arp.opcode == 2` | Shows ARP replies (*is-at*). |
| `arp.duplicate-address-detected` | Flags possible IP address conflicts detected by Wireshark. |

## IPv4

| Filter | Description |
|---|---|
| `ip` | Shows all IPv4 traffic. |
| `ip.addr == 192.168.1.10` | Shows packets with the given IP (source or destination). |
| `ip.src == 192.168.1.10` | Shows packets with the given source IP. |
| `ip.dst == 192.168.1.10` | Shows packets with the given destination IP. |
| `ip.ttl < 10` | Shows packets with a low TTL (useful for investigating routes/traceroute). |

## IPv6

| Filter | Description |
|---|---|
| `ipv6` | Shows all IPv6 traffic. |
| `ipv6.addr == fe80::1` | Shows IPv6 packets with the given address. |
| `ipv6.src == fe80::1` | Shows IPv6 packets with the given source address. |

## ICMP

| Filter | Description |
|---|---|
| `icmp` | Shows all ICMP traffic. |
| `icmp.type == 8` | Shows Echo Request messages. |
| `icmp.type == 0` | Shows Echo Reply messages. |
| `icmp.type == 3` | Shows Destination Unreachable messages. |
| `icmp.type == 11` | Shows Time Exceeded messages (common in traceroute). |

## DNS

| Filter | Description |
|---|---|
| `dns` | Shows all DNS traffic. |
| `dns.flags.response == 0` | Shows only queries. |
| `dns.flags.response == 1` | Shows only responses. |
| `dns.qry.name == "example.com"` | Shows queries for a specific name. |
| `dns.flags.rcode != 0` | Shows DNS responses with an error code (e.g., NXDOMAIN). |

## TCP

| Filter | Description |
|---|---|
| `tcp` | Shows all TCP traffic. |
| `tcp.port == 443` | Shows TCP traffic on port 443 (source or destination). |
| `tcp.flags.syn == 1 && tcp.flags.ack == 0` | Shows SYN packets (connection start). |
| `tcp.flags.syn == 1 && tcp.flags.ack == 1` | Shows SYN-ACK packets. |
| `tcp.flags.reset == 1` | Shows packets with the RST flag (reset connection). |
| `tcp.analysis.retransmission` | Shows retransmissions identified by Wireshark. |
| `tcp.analysis.zero_window` | Shows zero window situations (possible congestion). |

## UDP

| Filter | Description |
|---|---|
| `udp` | Shows all UDP traffic. |
| `udp.port == 53` | Shows UDP traffic on port 53 (DNS). |
| `udp.length > 512` | Shows UDP datagrams larger than 512 bytes. |

## HTTP

| Filter | Description |
|---|---|
| `http` | Shows all HTTP traffic. |
| `http.request` | Shows only HTTP requests. |
| `http.response` | Shows only HTTP responses. |
| `http.request.method == "GET"` | Shows GET requests. |
| `http.request.method == "POST"` | Shows POST requests. |
| `http.response.code >= 400` | Shows responses with a client or server error. |

## TLS

| Filter | Description |
|---|---|
| `tls` | Shows all TLS traffic. |
| `tls.handshake.type == 1` | Shows *Client Hello* messages. |
| `tls.handshake.type == 2` | Shows *Server Hello* messages. |
| `tls.alert_message` | Shows TLS alerts (possible handshake failures). |

> Note: by default, the content of TLS sessions is not readable without
> the session keys. Analysis here is limited to handshake metadata.

## DHCP

| Filter | Description |
|---|---|
| `dhcp` | Shows all DHCP traffic. |
| `dhcp.option.dhcp == 1` | Shows DHCP Discover messages. |
| `dhcp.option.dhcp == 2` | Shows DHCP Offer messages. |
| `dhcp.option.dhcp == 3` | Shows DHCP Request messages. |
| `dhcp.option.dhcp == 5` | Shows DHCP Ack messages. |

## Error analysis

| Filter | Description |
|---|---|
| `tcp.analysis.flags` | Shows packets flagged by Wireshark with some analysis condition (errors, retransmissions, etc.). |
| `_ws.expert.severity == "error"` | Shows packets classified as errors by Expert Info. |
| `icmp.type == 3` | Shows ICMP error messages (destination unreachable). |

## Retransmissions

| Filter | Description |
|---|---|
| `tcp.analysis.retransmission` | Shows all identified TCP retransmissions. |
| `tcp.analysis.fast_retransmission` | Shows fast retransmissions. |
| `tcp.analysis.duplicate_ack` | Shows duplicate ACKs, indicating possible packet loss. |

## Combining filters

| Filter | Description |
|---|---|
| `ip.addr == 192.168.1.10 && tcp.port == 443` | Combines a specific host and port. |
| `tcp.flags.syn == 1 && ip.dst == 192.168.1.20` | Shows connection attempts to a specific host. |
| `http.request && ip.src == 192.168.1.30` | Shows HTTP requests originating from a specific host. |
| `dns.flags.rcode != 0 && dns.flags.response == 1` | Shows only DNS responses with an error. |

These filters are a starting point. Each lab documents, in its own
"Filters used" section, the filters actually applied during the
analysis.
