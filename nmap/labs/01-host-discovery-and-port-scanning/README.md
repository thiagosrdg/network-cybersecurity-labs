# Lab 01: Host Discovery and Port Scanning

## Status

Planned

## Objective

Perform discovery of active hosts on a lab network and run a basic TCP
port scan, identifying open, closed, and filtered ports, and
understanding the difference between the main scan types.

## Concepts covered

- Host discovery (`-sn`).
- TCP connect scan (`-sT`) vs. SYN scan (`-sS`).
- Port states: `open`, `closed`, `filtered`.
- Basic interpretation of Nmap output.
- Relationship between a SYN scan and the TCP *three-way handshake*
  (see also the
  [wireshark](../../../wireshark/labs/03-tcp-three-way-handshake/README.md)
  track).

## Environment

- Operating system (scanning host): `<fill in>`
- Nmap version: `<fill in>`
- Scan target(s) (owned/authorized environment): `<fill in>`
- Topology: `<fill in>`
- Virtual machines: `<fill in>`
- Auxiliary tools: `<fill in>`

## Authorization

`<Explicitly confirm that the scan target is an owned environment or
has documented authorization, as described in
docs/scanning-safety-and-ethics.md.>`

## Scenario

`<Describe the scenario used, for example, an isolated lab network
with one or more owned virtual machines as the target.>`

## Procedure

`<Describe, step by step, how the lab was performed.>`

## Commands used

```text
nmap -sn 192.168.1.0/24
nmap -sT 192.168.1.10
nmap -p- 192.168.1.10
```

## Result analysis

`<Document here the relevant results observed during the actual
execution of the lab: hosts discovered, ports identified, and their
states.>`

## Evidence

`<Add anonymized screenshots in screenshots/ and reference the
corresponding output files in outputs/ once the lab is performed.>`

## Key findings

`<Fill in after the lab is performed.>`

## Indicators of suspicious behavior

`<Fill in, if applicable — for example, unexpected services on
unusual ports.>`

## Mitigations or recommendations

`<Fill in, if applicable, after the lab is performed.>`

## Conclusion

`<Fill in after the lab is performed.>`

## References

- [Official Nmap documentation](https://nmap.org/book/man.html)
- [nmap/docs/scanning-safety-and-ethics.md](../../docs/scanning-safety-and-ethics.md)
- [nmap/resources/useful-commands.md](../../resources/useful-commands.md)
