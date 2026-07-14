# tcpdump Labs

![Status](https://img.shields.io/badge/status-planned-lightgrey)
![Focus](https://img.shields.io/badge/focus-cybersecurity-blue)
![Tool](https://img.shields.io/badge/tool-tcpdump-4a4a4a)
![License](https://img.shields.io/badge/license-MIT-green)

> This folder is one of the lab tracks in the
> [network-cybersecurity-labs](../README.md) repository. See also the
> [wireshark/](../wireshark/README.md) and [nmap/](../nmap/README.md)
> tracks.

## Description

This track documents hands-on **command-line packet capture with
tcpdump** labs, focused on cybersecurity, BPF filter syntax, and
producing `.pcap` captures that complement the deeper protocol
investigation performed in the
[wireshark](../wireshark/README.md) track.

The goal is to incrementally build a documented technical portfolio
that demonstrates the ability to capture network traffic from the
command line — a skill particularly relevant on servers and headless
systems where a graphical tool like Wireshark isn't available.

All labs are performed in owned or authorized environments, following
good ethical and data protection practices (see
[Ethical and legal notice](#ethical-and-legal-notice)).

## Learning objectives

- Gain proficiency with tcpdump's command-line options.
- Practice building BPF (Berkeley Packet Filter) expressions.
- Understand when to capture directly to a `.pcap` file versus
  inspecting traffic live in the terminal.
- Relate command-line captures to the deeper analysis performed with
  Wireshark.
- Document technical procedures clearly, objectively, and
  reproducibly.

## Skills demonstrated

- Command-line packet capture on Unix-like systems.
- BPF filter construction and combination.
- Producing `.pcap` evidence for later protocol analysis.
- Troubleshooting network connectivity from a terminal-only
  environment.
- Responsible, authorized use of traffic capture tools.

## Track structure

```text
tcpdump/
├── README.md
├── docs/                       # Safety, ethics, and supporting concepts
├── labs/                       # Numbered hands-on labs
│   └── 01-basic-traffic-capture/
├── templates/                  # Reusable template for new labs
└── resources/                  # Useful commands and BPF filter reference
```

The `LICENSE`, `.gitignore`, `CONTRIBUTING.md`, and `SECURITY.md` files
are shared across all tracks and live at the root of the
[network-cybersecurity-labs](../README.md) repository.

Each lab in `labs/` contains:

- `README.md` — complete lab documentation.
- `captures/` — anonymized `.pcap` files (when applicable).
- `screenshots/` — anonymized visual evidence (when applicable).

## Labs

| # | Lab | Protocol/Topic | Objective | Status |
|---|---|---|---|---|
| 01 | [Basic Traffic Capture](labs/01-basic-traffic-capture/README.md) | BPF filters, `.pcap` capture | Capture traffic from the command line and export it for analysis | `Planned` |

Possible statuses: `Planned`, `In Progress`, `Completed`.

This track currently has only the base structure and one starter lab
in place — further labs (e.g., capturing on a remote host over SSH,
rotating captures with `-G`/`-W`, filtering on packet content) will be
added as they are actually performed.

## Ethical and legal notice

> ⚠️ **Important notice**
>
> Like the [wireshark](../wireshark/README.md) track, tcpdump performs
> **passive** traffic capture, but it must still only be run in
> **owned or explicitly authorized environments**. Capturing traffic
> from third-party networks, systems, or devices without authorization
> may violate local laws and acceptable use policies.
>
> This track has an **exclusively educational and defensive** purpose.
> None of the labs documented here are intended to compromise
> third-party systems.
>
> Before publishing any capture file or screenshot, read
> [docs/packet-capture-safety.md](docs/packet-capture-safety.md), which
> covers authorization, least-privilege capture, and anonymization of
> IPs, MACs, hostnames, and other sensitive data.

## Instructions to run or reproduce the labs

1. Install `tcpdump` on your operating system (pre-installed on most
   Linux/Unix distributions; available via package managers).
2. Set up an isolated lab environment (virtual machine, virtual
   network, or an owned test environment).
3. Go to the desired lab directory under `labs/`.
4. Read the lab's `README.md` to understand the objective, scenario,
   and procedure.
5. Reproduce the capture in your own environment, applying the
   suggested BPF filters.
6. Document your observations following the same model used in the
   lab (see [templates/lab-template.md](templates/lab-template.md)).
7. Before committing any capture or screenshot, review the content
   according to
   [docs/packet-capture-safety.md](docs/packet-capture-safety.md).

## General references

- [tcpdump official website](https://www.tcpdump.org/)
- [tcpdump man page](https://www.tcpdump.org/manpages/tcpdump.1.html)
- [resources/useful-commands.md](resources/useful-commands.md)

---

*This is a personal study track in cybersecurity and command-line
traffic capture. Suggestions and technical corrections are welcome —
see [CONTRIBUTING.md](../CONTRIBUTING.md).*
