# Lab 01: Basic Traffic Capture

## Status

Planned

## Objective

Capture network traffic from the command line using tcpdump, applying
BPF capture filters, writing the result to a `.pcap` file, and
reviewing the captured packets both in the terminal and later in
Wireshark.

## Concepts covered

- Basic tcpdump usage (`-i`, `-c`, `-w`, `-r`).
- BPF (Berkeley Packet Filter) syntax.
- Difference between printing packets to the terminal and writing them
  to a `.pcap` file.
- Relationship between tcpdump captures and the
  [wireshark](../../../wireshark/README.md) track (a `.pcap` captured
  here can be opened and analyzed there).

## Environment

- Operating system: `<fill in>`
- tcpdump version: `<fill in>`
- Network interface: `<fill in>`
- Topology: `<fill in>`
- Virtual machines: `<fill in>`
- Auxiliary tools: `<fill in>`

## Scenario

`<Describe the scenario used to generate the traffic, for example,
running ping and DNS queries from a lab host while capturing with
tcpdump on an isolated network.>`

## Procedure

`<Describe, step by step, how the capture was performed, including the
tcpdump command(s) run and how the resulting file was reviewed.>`

## Commands used

```text
tcpdump -i eth0 -c 50 -w capture.pcap
tcpdump -r capture.pcap
```

## Packet analysis

`<Document here the relevant packets observed during the actual
execution of the lab: protocols seen, hosts involved, and any notable
fields.>`

## Evidence

`<Add anonymized screenshots in screenshots/ and reference the
corresponding capture files in captures/ once the lab is performed.>`

## Key findings

`<Fill in after the lab is performed.>`

## Indicators of suspicious behavior

`<Fill in, if applicable, after the lab is performed.>`

## Mitigations or recommendations

`<Fill in, if applicable, after the lab is performed.>`

## Conclusion

`<Fill in after the lab is performed.>`

## References

- [tcpdump man page](https://www.tcpdump.org/manpages/tcpdump.1.html)
- [tcpdump/docs/packet-capture-safety.md](../../docs/packet-capture-safety.md)
- [tcpdump/resources/useful-commands.md](../../resources/useful-commands.md)
