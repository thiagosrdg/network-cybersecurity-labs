# Useful Filters

Practical list of display filters organized by protocol and purpose,
for quick reference during the labs. For the full explanation of each
category, see
[docs/wireshark-display-filters.md](../docs/wireshark-display-filters.md).

## General diagnostics

```text
ip.addr == 192.168.1.10
tcp.port == 443
udp.port == 53
frame.len > 1500
frame contains "error"
```

## ICMP — connectivity and latency

```text
icmp
icmp.type == 8
icmp.type == 0
icmp.type == 3
icmp.type == 11
```

## DNS — name resolution

```text
dns
dns.flags.response == 0
dns.flags.response == 1
dns.qry.name == "example.com"
dns.flags.rcode != 0
```

## TCP — connection control

```text
tcp
tcp.flags.syn == 1
tcp.flags.syn == 1 && tcp.flags.ack == 0
tcp.flags.syn == 1 && tcp.flags.ack == 1
tcp.flags.reset == 1
tcp.flags.fin == 1
tcp.analysis.retransmission
tcp.analysis.duplicate_ack
tcp.analysis.zero_window
```

## HTTP — unencrypted web traffic

```text
http
http.request
http.response
http.request.method == "GET"
http.request.method == "POST"
http.response.code >= 400
```

## Suspicious traffic investigation

```text
tcp.flags.reset == 1
tcp.analysis.retransmission
dns.flags.rcode != 0
tcp.port == 4444
tcp.port == 8080
frame.len > 1500
```

> Reminder: unusual ports, on their own, **do not prove** malicious
> activity. Every indicator must be analyzed within the context of the
> observed communication (see
> [Lab 05](../labs/05-suspicious-traffic-analysis/README.md)).

## Useful combinations

```text
ip.addr == 192.168.1.10 && tcp.port == 443
http.request && ip.src == 192.168.1.30
dns.flags.response == 1 && dns.flags.rcode != 0
tcp.flags.syn == 1 && tcp.flags.ack == 0 && ip.dst == 192.168.1.20
```
