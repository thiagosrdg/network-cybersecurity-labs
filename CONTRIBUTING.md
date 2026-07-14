# Contributing Guide

Thank you for considering contributing to **Network & Cybersecurity
Labs**. This is a personal study and portfolio repository, organized
into tracks by tool/topic (e.g., `wireshark/`, `nmap/`, `tcpdump/`),
but suggestions, technical corrections, and documentation improvements
are welcome.

## Naming convention

- Use file and directory names in **English**, in `kebab-case`
  (e.g., `dns-analysis`, `packet-capture-safety.md`).
- New tracks should be created as a folder at the root of the
  repository, with the tool/topic name in lowercase (e.g., `zeek/`,
  `log-analysis/`).
- Within each track, new labs should follow the `NN-lab-name` pattern,
  with a two-digit sequential number (e.g., `06-arp-spoofing-detection`).
- Each lab must keep the appropriate evidence subdirectories (e.g.,
  `captures/` and `screenshots/` in the Wireshark and tcpdump tracks;
  `outputs/` and `screenshots/` in the Nmap track), even if initially
  empty (use `.gitkeep`).

## Structure of a new track

When creating a new track, follow the same organization already used
in `wireshark/`, `nmap/`, and `tcpdump/`:

```text
track-name/
├── README.md      # Description, objectives, labs, and ethical notice
├── docs/           # Track-specific methodology and security guidelines
├── labs/           # Numbered labs
├── templates/      # Reusable lab template
└── resources/      # Quick references (filters, commands, etc.)
```

Add the new track to the "Tracks" table in the
[main README.md](README.md).

## Lab documentation

- Every lab must follow the structure defined in the respective
  track's `lab-template.md` (e.g.,
  [wireshark/templates/lab-template.md](wireshark/templates/lab-template.md),
  [nmap/templates/lab-template.md](nmap/templates/lab-template.md),
  [tcpdump/templates/lab-template.md](tcpdump/templates/lab-template.md)).
- Documentation must be written in **English**, with clear and
  objective technical language.
- Do not record results, captures, scan outputs, or conclusions for
  labs that have not actually been performed yet.
- Update the `Status` field (`Planned`, `In Progress`, `Completed`)
  both in the lab's `README.md` and in the track's `README.md` table.

## Anonymization

- Before adding any `.pcap`, `.pcapng`, scan output, or screenshot
  file, follow the respective track's security guidelines (e.g.,
  [wireshark/docs/packet-capture-safety.md](wireshark/docs/packet-capture-safety.md),
  [nmap/docs/scanning-safety-and-ethics.md](nmap/docs/scanning-safety-and-ethics.md),
  [tcpdump/docs/packet-capture-safety.md](tcpdump/docs/packet-capture-safety.md)).
- Never include personal public IPs, credentials, cookies, tokens, or
  third-party data.
- Prefer generating synthetic traffic or results in controlled, owned
  lab environments.

## Branch creation

- Create branches from `main` with descriptive names:
  - `feat/feature-name`
  - `docs/document-name`
  - `fix/fix-description`

## Clear commits

This project follows the
[Conventional Commits](https://www.conventionalcommits.org/)
convention:

```text
docs: add DNS analysis notes
feat: add ICMP packet capture lab
fix: correct TCP filter example
refactor: reorganize lab structure
chore: update repository metadata
```

## Pull requests

- Clearly describe what was changed and why, including which track
  the change belongs to.
- Indicate whether the PR adds real lab results, only
  documentation/structure, or corrections.
- Confirm that no sensitive file was included (see
  [SECURITY.md](SECURITY.md)).

## Prohibited content

Contributions that include the following will not be accepted:

- Illegal, offensive, or unethical content.
- Traffic captured or scans performed without explicit authorization
  from the network/system owner.
- Personal data, credentials, tokens, cookies, or sensitive
  third-party information.
- Techniques or materials intended for offensive use against
  third-party systems.
