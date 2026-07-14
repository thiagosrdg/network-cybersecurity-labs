# Labs — Nmap

This directory brings together the hands-on network scanning and
enumeration labs with Nmap. Each lab follows the same documentation
structure, defined in
[templates/lab-template.md](../templates/lab-template.md), and follows
the guidelines in
[docs/scanning-safety-and-ethics.md](../docs/scanning-safety-and-ethics.md).

## Structure of each lab

```text
labs/NN-lab-name/
├── README.md         # Complete lab documentation
├── outputs/            # Anonymized Nmap outputs (-oN/-oX/-oG)
└── screenshots/         # Anonymized visual evidence
```

The `outputs/` and `screenshots/` directories contain a `.gitkeep`
file while there is no real material yet, to keep the structure
versioned in Git.

## List of labs

| # | Lab | Technique/Topic | Status |
|---|---|---|---|
| 01 | [Host Discovery and Port Scanning](01-host-discovery-and-port-scanning/README.md) | Host discovery and port scanning | `Planned` |

Before adding scan outputs or screenshots to any lab, read
[docs/scanning-safety-and-ethics.md](../docs/scanning-safety-and-ethics.md).
