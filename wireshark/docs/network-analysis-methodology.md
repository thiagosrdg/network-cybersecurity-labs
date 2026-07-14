# Network Traffic Analysis Methodology

This document describes the methodology used in all labs in this
repository to investigate traffic captures consistently, traceably,
and defensibly. The idea is to always apply the same sequence of
steps, adapting the depth to the objective of each lab.

## 1. Define the objective of the analysis

Before opening any capture, clearly define:

- What is being investigated (e.g., protocol behavior, connectivity
  troubleshooting, possible suspicious activity).
- What question the analysis should answer.
- The time scope and hosts involved.

A well-defined objective avoids generic, unfocused analyses.

## 2. Validate the origin of the capture

- Confirm where, when, and how the capture was performed.
- Verify that the capture was made in an authorized, controlled
  environment.
- Record the network interface, capture host, and context (lab,
  virtual machine, isolated network, etc.).

## 3. Identify predominant hosts and protocols

- Use Wireshark statistics (e.g., *Statistics > Protocol Hierarchy*,
  *Statistics > Conversations*) to get an overview.
- Identify the main source and destination hosts.
- Identify the protocols most relevant to the objective of the
  analysis.

## 4. Establish a timeline

- Order the relevant events chronologically.
- Identify the start and end of the communication being analyzed.
- Observe traffic spikes, unusual intervals, or events concentrated in
  short time periods.

## 5. Apply filters progressively

- Start with broad filters (e.g., `ip.addr == x.x.x.x`) and refine
  from there.
- Combine filters incrementally to isolate relevant traffic.
- Document the filters used at each step (see
  [wireshark-display-filters.md](wireshark-display-filters.md)).

## 6. Identify anomalies

- Compare the observed traffic with the expected behavior of the
  protocol.
- Look for retransmissions, unexpected resets, error codes, abnormal
  latency, or unusual traffic patterns.
- Avoid jumping to conclusions: an anomaly is a point of attention, not
  definitive proof.

## 7. Validate hypotheses

- For each observed anomaly, formulate an explainable hypothesis.
- Look for additional evidence in the capture itself (or in
  complementary captures) that confirms or refutes the hypothesis.
- When there isn't enough evidence, record the hypothesis as
  **unconfirmed**, rather than presenting it as a conclusion.

## 8. Record evidence

- Save relevant screenshots of the analyzed packets.
- Reference frame numbers, timestamps, and applied filters.
- Maintain traceability between the evidence and the conclusion
  associated with it.

## 9. Protect sensitive data

- Before documenting or publishing any evidence, apply the guidelines
  in [packet-capture-safety.md](packet-capture-safety.md).
- Anonymize IPs, MACs, hostnames, usernames, and any data that could
  identify real people or systems.

## 10. Document conclusions and limitations

- Clearly separate **observed facts** from **hypotheses** and
  **inferences**.
- Describe the limitations of the analysis (e.g., partial capture,
  lack of context, missing complementary logs).
- Include practical recommendations when applicable (mitigation,
  troubleshooting, next investigation steps).

This methodology is used consistently across all labs in this
repository and serves as the basis for the
[incident analysis template](../templates/incident-analysis-template.md).
