# Lab 03: TCP Three-Way Handshake

## Status

Planned

## Objective

Analyze the establishment of TCP connections, identifying the steps of
the *three-way handshake* (SYN, SYN-ACK, and ACK), the sequence and
acknowledgment numbers involved, and observing possible
retransmissions, resets, or connection failures.

## Concepts covered

- TCP protocol (Transmission Control Protocol).
- *Three-way handshake* (SYN, SYN-ACK, ACK).
- Sequence (`seq`) and acknowledgment (`ack`) numbers.
- TCP flags (SYN, ACK, RST, FIN).
- Retransmissions and error analysis (`tcp.analysis.*`).
- Connection termination (graceful via FIN, abrupt via RST).

## Environment

- Operating system: `<fill in>`
- Wireshark version: `<fill in>`
- Network interface: `<fill in>`
- Topology: `<fill in>`
- Virtual machines: `<fill in>`
- Auxiliary tools: `<fill in>`

## Scenario

`<Describe the scenario used to generate the TCP traffic, for example,
connections established between a client and a lab server on a
specific port.>`

## Procedure

`<Describe, step by step, how the capture was performed and how the
TCP connections were generated during the lab.>`

## Filters used

### Capture filters

```text
tcp
```

### Display filters

```text
tcp
tcp.flags.syn == 1
tcp.flags.syn == 1 && tcp.flags.ack == 0
tcp.flags.syn == 1 && tcp.flags.ack == 1
tcp.flags.reset == 1
tcp.analysis.retransmission
```

## Packet analysis

`<Document here the relevant packets observed during the actual
execution of the lab: the full handshake sequence, seq/ack numbers at
each step, and any failures identified.>`

## Evidence

`<Add anonymized screenshots in screenshots/ and reference the
corresponding capture files in captures/ once the lab is performed.>`

## Key findings

`<Fill in after the lab is performed.>`

## Indicators of suspicious behavior

`<Fill in, if applicable, after the lab is performed — for example, a
high volume of SYN packets without a completed handshake (possible
half-open scan) or unusual RSTs.>`

## Mitigations or recommendations

`<Fill in, if applicable, after the lab is performed.>`

## Conclusion

`<Fill in after the lab is performed.>`

## References

- [RFC 9293 — Transmission Control Protocol (TCP)](https://www.rfc-editor.org/rfc/rfc9293)
- [Official Wireshark documentation](https://www.wireshark.org/docs/)
- [docs/wireshark-display-filters.md](../../docs/wireshark-display-filters.md)
