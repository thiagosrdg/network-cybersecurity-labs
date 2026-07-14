# Labs

This directory brings together all hands-on network traffic analysis
labs with Wireshark. Each lab is independent, but all follow the same
documentation structure, defined in
[templates/lab-template.md](../templates/lab-template.md), and the same
[analysis methodology](../docs/network-analysis-methodology.md).

## Structure of each lab

```text
labs/NN-lab-name/
├── README.md         # Complete lab documentation
├── captures/          # Anonymized .pcap/.pcapng files (when applicable)
└── screenshots/        # Anonymized visual evidence (when applicable)
```

The `captures/` and `screenshots/` directories contain a `.gitkeep`
file while there is no real material yet, to keep the structure
versioned in Git.

## List of labs

| # | Lab | Protocol/Topic | Status |
|---|---|---|---|
| 01 | [ICMP Analysis](01-icmp-analysis/README.md) | ICMP | `Planned` |
| 02 | [DNS Analysis](02-dns-analysis/README.md) | DNS | `Planned` |
| 03 | [TCP Three-Way Handshake](03-tcp-three-way-handshake/README.md) | TCP | `Planned` |
| 04 | [HTTP Traffic Analysis](04-http-traffic-analysis/README.md) | HTTP | `Planned` |
| 05 | [Suspicious Traffic Analysis](05-suspicious-traffic-analysis/README.md) | Various | `Planned` |

Before adding captures or screenshots to any lab, read
[docs/packet-capture-safety.md](../docs/packet-capture-safety.md).
