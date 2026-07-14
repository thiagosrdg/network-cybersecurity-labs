# Incident Analysis Template

This template helps structure the documentation of a traffic analysis
aimed at investigating a possible incident. It complements the
[lab template](lab-template.md) and follows this repository's
[traffic analysis methodology](../docs/network-analysis-methodology.md).

> **Important**: always distinguish between **observed fact**,
> **hypothesis**, **inference**, and **confirmed conclusion** (see the
> specific section at the end of this template). Do not present
> hypotheses as if they were conclusions.

## Context

Describe the general context: why this analysis is being performed,
what the lab scenario is, and what trigger (real or simulated)
motivated the investigation.

## Scope

Define the boundaries of the analysis:

- Which hosts, networks, or time ranges are within scope.
- What is explicitly out of scope for this analysis.

## Capture origin

- Capture location/environment:
- Network interface used:
- Tool used (Wireshark, TShark, tcpdump, etc.):
- Authorization/lab context:

## Date and time

- Capture date:
- Start time:
- End time:
- Time zone considered:

## Hosts involved

| Host/IP (anonymized) | Role | Notes |
|---|---|---|
| `<host-lab-01>` | | |
| `<host-lab-02>` | | |

## Timeline

| Time | Observed event |
|---|---|
| `HH:MM:SS` | Event description (observed fact) |
| `HH:MM:SS` | Event description (observed fact) |

## Protocols involved

List the relevant protocols identified during the analysis (e.g., TCP,
DNS, HTTP) and the role of each in the investigated scenario.

## Observed indicators

List the technical indicators identified (e.g., unusual ports,
elevated retransmissions, DNS error responses, connections to unusual
hosts), classifying each according to the
[Fact, hypothesis, inference, and conclusion](#fact-hypothesis-inference-and-confirmed-conclusion)
section.

## Evidence

Reference the packets, frames, timestamps, and screenshots
(anonymized) that support each observed indicator.

## Hypotheses

Describe the hypotheses formulated from the observed indicators,
making it clear that they have not yet been confirmed.

## Limitations

Describe the limitations of the analysis (e.g., incomplete capture,
lack of logs from other systems, inability to inspect encrypted
traffic).

## Conclusion

Present the conclusion of the analysis, clearly indicating the
confidence level (confirmed, partially confirmed, inconclusive).

## Recommendations

List practical recommendations resulting from the analysis (e.g.,
configuration adjustments, need for additional capture, points of
attention for future monitoring).

## Fact, hypothesis, inference, and confirmed conclusion

To maintain technical rigor in the documentation, always use the
classification below:

- **Observed fact**: something directly visible in the captured
  packets (e.g., "packet 42 contains an RST flag").
- **Hypothesis**: a possible explanation for an observed fact, not yet
  verified (e.g., "this RST may indicate a closed port on the
  destination").
- **Inference**: a deduction based on multiple observed facts, with
  reasonable confidence, but still subject to review (e.g., "the
  pattern of RSTs suggests a port scan").
- **Confirmed conclusion**: a statement supported by sufficient,
  verifiable evidence within the scope of the analysis (e.g., "packets
  1 through 50 confirm a sequential port scan on host X").
