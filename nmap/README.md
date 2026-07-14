# Nmap Labs

![Status](https://img.shields.io/badge/status-planned-lightgrey)
![Focus](https://img.shields.io/badge/focus-cybersecurity-blue)
![Tool](https://img.shields.io/badge/tool-Nmap-2f7fd1)
![License](https://img.shields.io/badge/license-MIT-green)

> This folder is one of the lab tracks in the
> [network-cybersecurity-labs](../README.md) repository. See also the
> [wireshark/](../wireshark/README.md) track.

## Description

This track documents hands-on **network discovery and port scanning
with Nmap** labs, focused on cybersecurity, network reconnaissance,
service enumeration, and understanding how these techniques show up in
network traffic.

Just like the [wireshark/](../wireshark/README.md) track, the goal is
to incrementally build a documented technical portfolio — in this
case, focused on the perspective of the host performing the scan and
on interpreting the results obtained.

All labs must be performed exclusively in owned or explicitly
authorized environments (see
[Ethical and legal notice](#ethical-and-legal-notice)).

## Learning objectives

- Understand the main types of Nmap scans (host discovery, TCP
  connect, SYN scan, UDP scan).
- Interpret port states (`open`, `closed`, `filtered`).
- Practice service, version, and operating system detection.
- Relate scan results to the behavior observed at the network layer
  (complementing the Wireshark track).
- Document technical analyses clearly, objectively, and reproducibly.
- Reinforce the importance of prior authorization for any scanning
  activity.

## Track structure

```text
nmap/
├── README.md
├── docs/                       # Security, ethics, and supporting concepts
├── labs/                       # Numbered hands-on labs
│   └── 01-host-discovery-and-port-scanning/
├── templates/                  # Reusable template for new labs
└── resources/                  # Useful commands and references
```

The `LICENSE`, `.gitignore`, `CONTRIBUTING.md`, and `SECURITY.md` files
are shared across all tracks and live at the root of the
[network-cybersecurity-labs](../README.md) repository.

Each lab in `labs/` contains:

- `README.md` — complete lab documentation.
- `outputs/` — anonymized Nmap outputs (`-oN`/`-oX`/`-oG`), when
  applicable.
- `screenshots/` — anonymized visual evidence, when applicable.

## Labs

| # | Lab | Technique/Topic | Objective | Status |
|---|---|---|---|---|
| 01 | [Host Discovery and Port Scanning](labs/01-host-discovery-and-port-scanning/README.md) | Host discovery, TCP scan | Discover active hosts and identify open ports | `Planned` |

Possible statuses: `Planned`, `In Progress`, `Completed`.

This track currently has only the base structure in place — new labs
(e.g., service/version detection, OS detection, NSE usage) will be
added as they are actually performed.

## Ethical and legal notice

> ⚠️ **Important notice**
>
> Unlike passive traffic capture, a port scan is an **active action**
> against a target. Scanning hosts, networks, or systems without
> explicit authorization may violate local laws, even when it causes
> no direct damage.
>
> This track has an **exclusively educational and defensive** purpose.
> All scans must be performed in owned, isolated, or explicitly
> authorized test environments.
>
> Before running any lab, read
> [docs/scanning-safety-and-ethics.md](docs/scanning-safety-and-ethics.md),
> which covers authorization, recommended environments, low-impact
> best practices, and result anonymization.

## Instructions to run or reproduce the labs

1. Install [Nmap](https://nmap.org/download.html) on your operating
   system.
2. Set up an isolated environment you own (virtual machine or virtual
   network) as the scan target.
3. Go to the desired lab directory under `labs/`.
4. Read the lab's `README.md` to understand the objective, scenario,
   and procedure.
5. Reproduce the suggested commands in your own environment.
6. Document your observations following the same model used in the
   lab (see [templates/lab-template.md](templates/lab-template.md)).
7. Before committing any scan output or screenshot, review the content
   according to
   [docs/scanning-safety-and-ethics.md](docs/scanning-safety-and-ethics.md).

## General references

- [Official Nmap documentation](https://nmap.org/book/man.html)
- [resources/useful-commands.md](resources/useful-commands.md)

---

*This is a personal study track in cybersecurity and network
reconnaissance. Suggestions and technical corrections are welcome —
see [CONTRIBUTING.md](../CONTRIBUTING.md).*
