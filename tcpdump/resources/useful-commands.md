# Useful tcpdump Commands

Quick reference for common tcpdump commands and flags, for use during
the labs. All examples must be run only on owned or authorized
interfaces/networks (see
[docs/packet-capture-safety.md](../docs/packet-capture-safety.md)).

## Basic capture

```text
tcpdump -i eth0
tcpdump -i any
```

Captures traffic on the given interface (`-i`), printing a summary
line per packet to the terminal.

## Limiting capture size and duration

```text
tcpdump -i eth0 -c 100
tcpdump -i eth0 -G 60 -W 1
```

- `-c 100` — stops after capturing 100 packets.
- `-G 60 -W 1` — rotates the capture file every 60 seconds, keeping 1
  file (useful for time-bounded lab captures).

## Writing and reading capture files

```text
tcpdump -i eth0 -w capture.pcap
tcpdump -r capture.pcap
```

- `-w` — writes raw packets to a `.pcap` file instead of printing them
  (recommended for later analysis in Wireshark).
- `-r` — reads and prints packets from an existing capture file.

## Verbosity and packet detail

```text
tcpdump -i eth0 -v
tcpdump -i eth0 -vv
tcpdump -i eth0 -X
tcpdump -i eth0 -A
```

- `-v`/`-vv` — increases the verbosity of the printed output.
- `-X` — shows packet contents in hex and ASCII.
- `-A` — shows packet contents in ASCII only (useful for plain-text
  protocols such as HTTP; be mindful of the safety guidelines above).

## BPF filter examples

```text
tcpdump -i eth0 host 192.168.1.10
tcpdump -i eth0 net 192.168.1.0/24
tcpdump -i eth0 port 53
tcpdump -i eth0 tcp port 443
tcpdump -i eth0 udp port 53
tcpdump -i eth0 icmp
tcpdump -i eth0 src host 192.168.1.10
tcpdump -i eth0 dst host 192.168.1.20
```

BPF filter syntax is the same used by Wireshark capture filters — see
[wireshark/docs/wireshark-capture-filters.md](../../wireshark/docs/wireshark-capture-filters.md)
for a side-by-side explanation.

## Combining filters

```text
tcpdump -i eth0 'tcp port 443 and host 192.168.1.10'
tcpdump -i eth0 'icmp or arp'
tcpdump -i eth0 'tcp[tcpflags] & (tcp-syn) != 0'
```

- `and`/`or`/`not` combine BPF expressions.
- The last example shows only TCP packets with the SYN flag set — a
  building block for the same handshake investigation covered in
  [wireshark/labs/03-tcp-three-way-handshake/](../../wireshark/labs/03-tcp-three-way-handshake/README.md).

## Listing available interfaces

```text
tcpdump -D
```

Lists the network interfaces available for capture.

Remember to review and anonymize any capture file before adding it to
`labs/**/captures/`.
