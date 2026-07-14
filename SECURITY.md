# Security Policy

## Project purpose

**Network & Cybersecurity Labs** is a repository with an **exclusively
educational and defensive** purpose, created to document networking and
cybersecurity labs organized by track (e.g., `wireshark/`, `nmap/`,
`tcpdump/`). It is not intended to store, distribute, or promote
offensive techniques against third-party systems.

## Reporting vulnerabilities or sensitive data

If you identify:

- a vulnerability related to the content of this repository;
- a capture file, scan output, screenshot, or piece of documentation
  that mistakenly contains sensitive data (personal public IPs, real
  hostnames, credentials, cookies, tokens, or third-party
  information);

please **do not open a public issue** describing the problem in
detail. Instead, contact the maintainer privately through the e-mail
or channel listed in the `README.md` ("Contact and professional
profile" section), describing the issue briefly.

## General guidelines

- **Credentials and personal data must never be published in issues,
  pull requests, or versioned files.**
- Every capture file (`.pcap`/`.pcapng`) or scanning output must be
  manually reviewed before being added to the repository, following
  each track's guidelines:
  - [wireshark/docs/packet-capture-safety.md](wireshark/docs/packet-capture-safety.md)
  - [nmap/docs/scanning-safety-and-ethics.md](nmap/docs/scanning-safety-and-ethics.md)
  - [tcpdump/docs/packet-capture-safety.md](tcpdump/docs/packet-capture-safety.md)
- Screenshots must be reviewed to ensure they do not expose personal
  public IPs, real hostnames, e-mails, tokens, or other identifiable
  data.
- If sensitive material is identified after a merge, it will be
  removed from the history as soon as possible and the anonymization
  policy will be reinforced.

## Scope

This repository does not host production applications or process real
user data. Therefore, the "security" scope here mainly concerns the
**protection of data potentially present in traffic captures, scan
outputs, and other lab evidence**, not vulnerabilities in running
software.
