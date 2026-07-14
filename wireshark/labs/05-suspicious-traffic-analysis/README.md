# Lab 05: Suspicious Traffic Analysis

## Status

Planned

## Objective

Apply an initial traffic investigation methodology to identify unusual
connections, observing ports, hosts, communication frequency,
retransmissions, and abnormal patterns. The lab aims to document
hypotheses responsibly, without asserting conclusions without
sufficient evidence.

## Concepts covered

- Traffic investigation methodology (see
  [docs/network-analysis-methodology.md](../../docs/network-analysis-methodology.md)).
- Difference between observed fact, hypothesis, inference, and
  confirmed conclusion (see
  [templates/incident-analysis-template.md](../../templates/incident-analysis-template.md)).
- Technical indicators of possible suspicious behavior (unusual ports,
  frequent RSTs, retransmissions, DNS error responses).
- Limitations of an analysis based solely on packet capture.

## Environment

- Operating system: `<fill in>`
- Wireshark version: `<fill in>`
- Network interface: `<fill in>`
- Topology: `<fill in>`
- Virtual machines: `<fill in>`
- Auxiliary tools: `<fill in>`

## Scenario

`<Describe the scenario used to generate or obtain the analyzed
traffic, making it explicit that it is a controlled lab environment
and/or synthetic traffic generated for study purposes.>`

## Procedure

`<Describe, step by step, how the capture was performed and how the
investigation was conducted, including the order in which filters were
applied.>`

## Filters used

### Capture filters

```text
Add capture filters here, if used.
```

### Display filters

```text
tcp.flags.reset == 1
tcp.analysis.retransmission
dns.flags.rcode != 0
tcp.port == 4444
tcp.port == 8080
frame.len > 1500
```

## Packet analysis

`<Document here the relevant packets observed during the actual
execution of the lab, applying the progressive analysis methodology
described in docs/network-analysis-methodology.md.>`

## Evidence

`<Add anonymized screenshots in screenshots/ and reference the
corresponding capture files in captures/ once the lab is performed.>`

## Key findings

`<Fill in after the lab is performed, classifying each finding as an
observed fact, hypothesis, inference, or confirmed conclusion.>`

## Indicators of suspicious behavior

`<Fill in, if applicable, after the lab is performed.>`

> **Important note**: using a specific port (e.g., 4444 or 8080)
> **does not prove**, on its own, malicious activity. Unusual ports
> are only a starting point for investigation — every indicator must
> be analyzed within the full context of the communication (hosts
> involved, traffic volume, the actual protocol used, frequency, and
> other evidence).

## Mitigations or recommendations

`<Fill in, if applicable, after the lab is performed.>`

## Conclusion

`<Fill in after the lab is performed, clearly stating the confidence
level of the conclusions presented.>`

## References

- [Official Wireshark documentation](https://www.wireshark.org/docs/)
- [docs/network-analysis-methodology.md](../../docs/network-analysis-methodology.md)
- [templates/incident-analysis-template.md](../../templates/incident-analysis-template.md)
