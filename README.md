# Network & Cybersecurity Labs

![Status](https://img.shields.io/badge/status-in%20progress-yellow)
![Focus](https://img.shields.io/badge/focus-cybersecurity-blue)
![License](https://img.shields.io/badge/license-MIT-green)

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

New tracks can be added at any time — just create a new folder at the
root of the repository (e.g., `zeek/`, `tcpdump/`, `log-analysis/`)
following the same organization pattern described below.

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
└── nmap/                    # Scanning and enumeration track with Nmap
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

See the detailed methodology for each track in
[wireshark/docs/network-analysis-methodology.md](wireshark/docs/network-analysis-methodology.md).

## Ethical and legal notice

> ⚠️ **Important notice**
>
> All labs in this repository — traffic capture, port scanning, or any
> other technique — must be performed **only in owned or explicitly
> authorized environments**. Capturing traffic from or scanning
> third-party networks, systems, or devices without authorization may
> violate local laws and acceptable use policies.
>
> This repository has an **exclusively educational and defensive**
> purpose. None of the labs documented here are intended to compromise
> third-party systems.
>
> Each track has its own specific ethical notice and detailed
> anonymization guidelines — see:
> - [wireshark/docs/packet-capture-safety.md](wireshark/docs/packet-capture-safety.md)
> - [nmap/docs/scanning-safety-and-ethics.md](nmap/docs/scanning-safety-and-ethics.md)

## Instructions to run or reproduce the labs

1. Choose the desired track (`wireshark/` or `nmap/`).
2. Read the track's `README.md` to understand objectives and
   prerequisites.
3. Set up an isolated environment you own (virtual machine or virtual
   network).
4. Go to the specific lab inside `labs/` and follow the described
   procedure.
5. Before committing any capture, scan output, or screenshot, review
   the content according to the respective track's security
   guidelines.

## Progress

This repository is in the structuring phase. The `wireshark/` track has
the base documentation for five labs created, still **with no real
captures or results recorded**. The `nmap/` track was just created,
with the base structure and one initial lab planned. The progress of
each lab is tracked via the `Status` field in its respective
`README.md`.

## Next steps

- Run and document the first real labs in `wireshark/` and `nmap/`.
- Expand the `nmap/` track with service/version detection, OS
  detection, and NSE labs.
- Consider creating new tracks (e.g., `tcpdump/`, `zeek/`,
  `log-analysis/`) as new labs are performed.

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

## Contact and professional profile

- GitHub: [thiagosrdg](https://github.com/thiagosrdg)
- LinkedIn: `<add LinkedIn link>`
- Contact e-mail: `<add professional contact e-mail>`

---

*This is a personal study project in networking and cybersecurity.
Suggestions and technical corrections are welcome — see
[CONTRIBUTING.md](CONTRIBUTING.md).*
