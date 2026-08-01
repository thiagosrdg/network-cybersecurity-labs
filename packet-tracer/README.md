# Packet Tracer Labs

![Status](https://img.shields.io/badge/status-planned-lightgrey)
![Focus](https://img.shields.io/badge/focus-networking-blue)
![Tool](https://img.shields.io/badge/tool-Cisco%20Packet%20Tracer-2f7fd1)
![License](https://img.shields.io/badge/license-MIT-green)

> This folder is one of the lab tracks in the
> [network-cybersecurity-labs](../README.md) repository. See also the
> [wireshark/](../wireshark/README.md), [nmap/](../nmap/README.md), and
> [tcpdump/](../tcpdump/README.md) tracks.

## Description

This track documents hands-on **network design, configuration, and
troubleshooting labs built in Cisco Packet Tracer** — switching,
routing, VLANs, access control lists, NAT, and basic network security
controls.

Unlike the other tracks, which analyze traffic or scan existing hosts,
this one looks at networking from the perspective of the person
**building and securing the infrastructure**: designing topologies,
configuring Cisco IOS devices, and validating that the resulting
network behaves as intended. It complements the
[wireshark/](../wireshark/README.md) and [tcpdump/](../tcpdump/README.md)
tracks (traffic analysis) and the [nmap/](../nmap/README.md) track
(reconnaissance) with the underlying network design and
configuration perspective.

All labs are built in the Packet Tracer simulator, so no real or
third-party infrastructure is ever involved.

## Learning objectives

- Design and document simple to moderately complex network topologies.
- Configure switching fundamentals (VLANs, trunking, inter-VLAN
  routing).
- Configure routing fundamentals (static routing, basic dynamic
  routing protocols).
- Apply basic security controls (port security, ACLs, SSH access,
  basic device hardening).
- Verify and troubleshoot connectivity using Cisco IOS `show`/`debug`
  commands and Packet Tracer's simulation mode.
- Document network designs and configurations clearly, objectively,
  and reproducibly.

## Track structure

```text
packet-tracer/
├── README.md
├── docs/                       # Methodology and lab environment notes
├── labs/                       # Numbered hands-on labs
│   └── 01-basic-topology-and-static-routing/
├── templates/                  # Reusable template for new labs
└── resources/                  # Useful Cisco IOS commands and references
```

The `LICENSE` and `.gitignore` files are shared across all tracks and
live at the root of the [network-cybersecurity-labs](../README.md)
repository.

Each lab in `labs/` contains:

- `README.md` — complete lab documentation.
- `topologies/` — the Packet Tracer project file(s) (`.pkt`) for the
  lab, when applicable.
- `screenshots/` — visual evidence (topology diagrams, command
  output, verification tests), when applicable.

## Labs

| # | Lab | Technique/Topic | Objective | Status |
|---|---|---|---|---|
| 01 | [Basic Topology and Static Routing](labs/01-basic-topology-and-static-routing/README.md) | Switching, static routing | Build a small multi-router topology and establish end-to-end connectivity | `Planned` |

Possible statuses: `Planned`, `In Progress`, `Completed`.

This track currently has only the base structure in place — new labs
(e.g., VLANs and trunking, inter-VLAN routing, dynamic routing, ACLs,
NAT, port security) will be added as they are actually performed.

## Ethical and legal notice

> ⚠️ **Important notice**
>
> All labs in this track are built and run **exclusively inside the
> Cisco Packet Tracer simulator**, using simulated devices and
> addressing. No lab in this track targets real, production, or
> third-party infrastructure.
>
> This track has an **exclusively educational** purpose: the goal is
> to practice network design, configuration, and troubleshooting
> skills, not to document or replicate any real organization's
> network.
>
> If a lab is inspired by a real-world scenario, identifying details
> (organization names, real IP ranges, hostnames) must be replaced
> with synthetic or documentation values before being committed (see
> [docs/lab-environment-and-methodology.md](docs/lab-environment-and-methodology.md)).

## Instructions to run or reproduce the labs

1. Install [Cisco Packet Tracer](https://www.netacad.com/courses/packet-tracer)
   (free, requires a Cisco Networking Academy account).
2. Go to the desired lab directory under `labs/`.
3. Read the lab's `README.md` to understand the objective, topology,
   and procedure.
4. Open the corresponding `.pkt` file in `topologies/` (when
   available) or rebuild the topology described in the lab.
5. Reproduce the configuration steps and verification commands in your
   own Packet Tracer instance.
6. Document your observations following the same model used in the
   lab (see [templates/lab-template.md](templates/lab-template.md)).

## General references

- [Cisco Packet Tracer — Networking Academy](https://www.netacad.com/courses/packet-tracer)
- [Cisco IOS command reference](https://www.cisco.com/c/en/us/support/ios-nx-os-software/ios-15-2m-t/products-command-reference-list.html)
- [resources/useful-commands.md](resources/useful-commands.md)

---

*This is a personal study track in networking and cybersecurity.
Suggestions and technical corrections are welcome.*
