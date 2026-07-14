# Labs — tcpdump

This directory brings together the hands-on command-line packet
capture labs with tcpdump. Each lab follows the same documentation
structure, defined in
[templates/lab-template.md](../templates/lab-template.md), and follows
the guidelines in
[docs/packet-capture-safety.md](../docs/packet-capture-safety.md).

## Structure of each lab

```text
labs/NN-lab-name/
├── README.md         # Complete lab documentation
├── captures/          # Anonymized .pcap files
└── screenshots/         # Anonymized visual evidence
```

The `captures/` and `screenshots/` directories contain a `.gitkeep`
file while there is no real material yet, to keep the structure
versioned in Git.

## List of labs

| # | Lab | Protocol/Topic | Status |
|---|---|---|---|
| 01 | [Basic Traffic Capture](01-basic-traffic-capture/README.md) | BPF filters, `.pcap` capture | `Planned` |

Before adding captures or screenshots to any lab, read
[docs/packet-capture-safety.md](../docs/packet-capture-safety.md).
