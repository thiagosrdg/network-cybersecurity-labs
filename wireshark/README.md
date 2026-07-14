# Wireshark Labs

![Status](https://img.shields.io/badge/status-in%20progress-yellow)
![Focus](https://img.shields.io/badge/focus-cybersecurity-blue)
![Tool](https://img.shields.io/badge/tool-Wireshark-1679A7)
![License](https://img.shields.io/badge/license-MIT-green)

> This folder is one of the lab tracks in the
> [network-cybersecurity-labs](../README.md) repository. See also the
> [nmap/](../nmap/README.md) track.

## Description

This track documents hands-on **network traffic analysis with
Wireshark** labs, focused on cybersecurity, protocol analysis, packet
investigation, and identification of suspicious behavior.

The goal is to incrementally build a documented technical portfolio
that demonstrates the ability to capture, analyze, and interpret
network traffic in controlled scenarios, applying information security
and network forensics fundamentals.

All labs are performed in owned or authorized environments, following
good ethical and data protection practices (see
[Ethical and legal notice](#ethical-and-legal-notice)).

## Learning objectives

- Gain an in-depth understanding of how TCP/IP protocols work.
- Develop proficiency in capturing and analyzing traffic with
  Wireshark.
- Practice building and using capture filters and display filters.
- Recognize normal network communication patterns and identify
  deviations.
- Apply a structured packet investigation methodology.
- Document technical analyses clearly, objectively, and reproducibly.
- Develop network forensics and incident response fundamentals.

## Skills demonstrated

- Packet analysis and header interpretation across multiple layers.
- Practical understanding of TCP/IP protocols (Ethernet, ARP,
  IPv4/IPv6, ICMP, TCP, UDP, DNS, HTTP).
- Analysis of ICMP, DNS, TCP, and HTTP traffic.
- Building capture and display filters.
- Network troubleshooting from packet evidence.
- Initial identification of suspicious traffic and indicators of
  compromise.
- Network forensics fundamentals.
- Structured technical documentation and responsible use of traffic
  analysis tools.

## Technologies and tools used

- [Wireshark](https://www.wireshark.org/) — graphical packet analysis.
- [TShark](https://www.wireshark.org/docs/man-pages/tshark.html) —
  command-line packet analysis.
- Virtualized and/or isolated lab environments.
- Markdown for technical documentation.
- Git/GitHub for version control and portfolio.

More details in
[resources/recommended-tools.md](resources/recommended-tools.md).

## Track structure

```text
wireshark/
├── README.md
├── docs/                       # Methodology, filters, and supporting concepts
├── labs/                       # Numbered hands-on labs
│   ├── 01-icmp-analysis/
│   ├── 02-dns-analysis/
│   ├── 03-tcp-three-way-handshake/
│   ├── 04-http-traffic-analysis/
│   └── 05-suspicious-traffic-analysis/
├── templates/                  # Reusable templates for new labs
└── resources/                  # Filters, protocol reference, and tools
```

The `LICENSE`, `.gitignore`, `CONTRIBUTING.md`, and `SECURITY.md` files
are shared across all tracks and live at the root of the
[network-cybersecurity-labs](../README.md) repository.

Each lab in `labs/` contains:

- `README.md` — complete lab documentation.
- `captures/` — anonymized `.pcap`/`.pcapng` files (when applicable).
- `screenshots/` — anonymized visual evidence (when applicable).

## Labs

| # | Lab | Protocol/Topic | Objective | Status |
|---|---|---|---|---|
| 01 | [ICMP Analysis](labs/01-icmp-analysis/README.md) | ICMP | Analyze Echo Request/Reply, TTL, and latency | `Planned` |
| 02 | [DNS Analysis](labs/02-dns-analysis/README.md) | DNS | Analyze queries, responses, and return codes | `Planned` |
| 03 | [TCP Three-Way Handshake](labs/03-tcp-three-way-handshake/README.md) | TCP | Analyze connection establishment and failures | `Planned` |
| 04 | [HTTP Traffic Analysis](labs/04-http-traffic-analysis/README.md) | HTTP | Analyze requests/responses and unencrypted traffic risks | `Planned` |
| 05 | [Suspicious Traffic Analysis](labs/05-suspicious-traffic-analysis/README.md) | Various | Apply a methodology to investigate unusual traffic | `Planned` |

Possible statuses: `Planned`, `In Progress`, `Completed`.

## Analysis methodology

All labs follow a consistent investigation methodology, described in
detail in
[docs/network-analysis-methodology.md](docs/network-analysis-methodology.md).
In summary, it covers:

1. Defining the objective of the analysis.
2. Validating the origin of the capture.
3. Identifying predominant hosts and protocols.
4. Building a timeline.
5. Progressively applying filters.
6. Identifying anomalies.
7. Validating hypotheses.
8. Recording evidence.
9. Protecting sensitive data.
10. Documenting conclusions and limitations.

## Ethical and legal notice

> ⚠️ **Important notice**
>
> Network traffic capture and analysis must only be performed in
> **owned or explicitly authorized environments**. Capturing traffic
> from third-party networks, systems, or devices without authorization
> may violate local laws and acceptable use policies.
>
> This track has an **exclusively educational and defensive** purpose.
> None of the labs documented here are intended to compromise
> third-party systems. All analyzed traffic is generated in controlled
> labs (virtual machines, isolated networks, or owned test
> environments).
>
> Before publishing any capture file, screenshot, or evidence, follow
> the guidelines described in
> [docs/packet-capture-safety.md](docs/packet-capture-safety.md), which
> cover anonymization of IPs, MACs, hostnames, credentials, and other
> sensitive data.

## Instructions to run or reproduce the labs

1. Install [Wireshark](https://www.wireshark.org/download.html) (the
   latest stable version) on your operating system.
2. Set up an isolated lab environment (virtual machine, virtual
   network, or an owned test environment).
3. Go to the desired lab directory under `labs/`.
4. Read the lab's `README.md` to understand the objective, scenario,
   and procedure.
5. Reproduce the capture in your own environment, applying the
   suggested capture and display filters.
6. Document your observations following the same model used in the
   lab (see [templates/lab-template.md](templates/lab-template.md)).
7. Before committing any capture or screenshot, review the content
   according to
   [docs/packet-capture-safety.md](docs/packet-capture-safety.md).

## Progress

This track is in the initial structuring phase. The labs have their
base documentation created, but still **no real captures or results
recorded**. The progress of each lab is tracked via the `Status` field
in the table above and in its respective `README.md`.

## Upcoming labs

Ideas for future expansion of this track (not yet started):

- DHCP traffic analysis.
- Introduction to TLS/HTTPS traffic analysis (metadata only, no
  decryption).
- ARP traffic analysis and ARP spoofing detection in a lab setting.
- Introduction to IDS/IPS and correlation with packet captures.
- Simulated data exfiltration analysis in a controlled environment.

## Commit convention and contact

The commit convention, the full legal notice, and professional contact
information are shared across the whole repository and are described
in the [main README.md](../README.md).

---

*This is a personal study track in cybersecurity and network traffic
analysis. Suggestions and technical corrections are welcome — see
[CONTRIBUTING.md](../CONTRIBUTING.md).*
