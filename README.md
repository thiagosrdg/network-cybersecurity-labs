# Network & Cybersecurity Labs

## Description

This repository brings together hands-on **network and cybersecurity
labs**, organized by tool/topic into independent tracks. Each track
documents analysis, investigation, or network reconnaissance labs,
following a consistent methodology and a standardized documentation
structure.

The goal is to incrementally build a technical portfolio that
demonstrates the ability to operate network and security tools,
interpret their results, and document analyses clearly and
reproducibly — always in owned or explicitly authorized environments.

## Ethics statement

> All laboratories in this repository were performed in controlled
> environments using systems owned by me or explicitly authorized
> for security testing.
>
> IP addresses, hostnames, MAC addresses and other identifying
> information may be replaced with synthetic values for documentation.

## Tracks

| Track | Tool/Topic | Description | Status |
|---|---|---|---|
| [wireshark/](wireshark/README.md) | Wireshark | Network traffic analysis, protocols, and packet investigation | `In progress` |
| [nmap/](nmap/README.md) | Nmap | Network discovery, port scanning, and service enumeration | `Planned` |
| [tcpdump/](tcpdump/README.md) | tcpdump | Command-line packet capture and BPF filters | `Planned` |


## Repository structure

```text
network-cybersecurity-labs/
├── README.md               # This file — general index of the repository
├── LICENSE
├── .gitignore
├── CONTRIBUTING.md
├── SECURITY.md
├── wireshark/               # Traffic analysis track with Wireshark
│   ├── README.md
│   ├── docs/
│   ├── labs/
│   ├── templates/
│   └── resources/
├── nmap/                    # Scanning and enumeration track with Nmap
│   ├── README.md
│   ├── docs/
│   ├── labs/
│   ├── templates/
│   └── resources/
└── tcpdump/                 # Command-line capture track with tcpdump
    ├── README.md
    ├── docs/
    ├── labs/
    ├── templates/
    └── resources/
```

Each track follows the same internal organization:

- `README.md` — track description, objectives, labs, and a
  tool-specific ethical/legal notice.
- `docs/` — methodology, supporting concepts, and security guidelines.
- `labs/` — numbered hands-on labs (`NN-lab-name/`), each with its own
  `README.md` and directories for evidence (`captures/`, `outputs/`,
  `screenshots/`, depending on the tool).
- `templates/` — reusable templates for new labs.
- `resources/` — quick references, filters, and useful commands.

The `LICENSE`, `.gitignore`, `CONTRIBUTING.md`, and `SECURITY.md` files
are unique and shared across all tracks.

## Skills demonstrated

- Packet analysis and header interpretation across multiple layers.
- Practical understanding of TCP/IP protocols (Ethernet, ARP,
  IPv4/IPv6, ICMP, TCP, UDP, DNS, HTTP).
- Use of capture filters and display filters in Wireshark.
- Command-line packet capture and BPF filters with tcpdump.
- Network reconnaissance and service enumeration with Nmap.
- Network troubleshooting from technical evidence.
- Initial identification of suspicious traffic and indicators of
  compromise.
- Network forensics fundamentals.
- Structured technical documentation and responsible use of network
  and security tools.

## Analysis methodology

Each track follows its own methodology, adapted to the tool and the
type of evidence analyzed, but all of them share the same principles:

1. Clearly define the objective of the analysis.
2. Validate the origin of the evidence (capture, scan, log).
3. Identify predominant hosts, protocols, or services.
4. Progressively apply filters/commands, from broad to specific.
5. Identify anomalies without jumping to conclusions.
6. Validate hypotheses with concrete evidence.
7. Record evidence in a structured way.
8. Protect sensitive data before any publication.
9. Document conclusions, limitations, and recommendations.

## Ethical and legal notice

> ⚠️ **Important notice**
>
> All labs in this repository — traffic capture, port scanning, or any
> other technique — must be performed **only in owned or explicitly
> authorized environments**. 
>
> This repository has an **exclusively educational and defensive**
> purpose. None of the labs documented here are intended to compromise
> third-party systems.

## Instructions to run or reproduce the labs

1. Choose the desired track (`wireshark/`, `nmap/`, or `tcpdump/`).
2. Read the track's `README.md` to understand objectives and
   prerequisites.
3. Set up an isolated environment you own (virtual machine or virtual
   network).
4. Go to the specific lab inside `labs/` and follow the described
   procedure.
5. Before committing any capture, scan output, or screenshot, review
   the content according to the respective track's security
   guidelines.

## Next steps

- Run and document the first real labs in `wireshark/`, `nmap/`, and
  `tcpdump/`.
- Expand the `nmap/` track with service/version detection, OS
  detection, and NSE labs.
- Expand the `tcpdump/` track with remote/SSH captures and rotating
  capture files.

## Commit convention

This repository follows the
[Conventional Commits](https://www.conventionalcommits.org/)
convention:

```text
docs: add DNS analysis notes
feat: add ICMP packet capture lab
fix: correct TCP filter example
refactor: reorganize lab structure
chore: update repository metadata
```
---

*This is a personal study project in networking and cybersecurity.*
