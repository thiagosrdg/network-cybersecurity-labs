# Lab 02: DNS Analysis

## Status

Planned

## Objective

Analyze DNS queries and responses captured in a lab environment,
identifying the queried names, the record types involved, and the
response codes. The lab aims to observe both normal name resolution
behavior and possible anomalies.

## Concepts covered

- DNS protocol (Domain Name System).
- Structure of queries and responses.
- Record types (A, AAAA, CNAME, MX, among others).
- DNS response codes (`rcode`), including `NOERROR` and `NXDOMAIN`.
- Difference between recursive and iterative resolution (conceptual).
- Capture and display filters specific to DNS.

## Environment

- Operating system: `<fill in>`
- Wireshark version: `<fill in>`
- Network interface: `<fill in>`
- Topology: `<fill in>`
- Virtual machines: `<fill in>`
- Auxiliary tools: `<fill in>`

## Scenario

`<Describe the scenario used to generate the DNS traffic, for example,
name resolution from a lab host against a controlled DNS resolver.>`

## Procedure

`<Describe, step by step, how the capture was performed and which DNS
queries were generated during the lab.>`

## Filters used

### Capture filters

```text
port 53
```

### Display filters

```text
dns
dns.flags.response == 0
dns.flags.response == 1
dns.qry.name
dns.flags.rcode != 0
```

## Packet analysis

`<Document here the relevant packets observed during the actual
execution of the lab: queried names, record types, response times, and
any error codes returned.>`

## Evidence

`<Add anonymized screenshots in screenshots/ and reference the
corresponding capture files in captures/ once the lab is performed.>`

## Key findings

`<Fill in after the lab is performed.>`

## Indicators of suspicious behavior

`<Fill in, if applicable, after the lab is performed — for example,
queries to unusual domains, a high volume of `NXDOMAIN` responses, or
atypical query patterns.>`

## Mitigations or recommendations

`<Fill in, if applicable, after the lab is performed.>`

## Conclusion

`<Fill in after the lab is performed.>`

## References

- [RFC 1035 — Domain Names, Implementation and Specification](https://www.rfc-editor.org/rfc/rfc1035)
- [Official Wireshark documentation](https://www.wireshark.org/docs/)
- [docs/wireshark-display-filters.md](../../docs/wireshark-display-filters.md)
