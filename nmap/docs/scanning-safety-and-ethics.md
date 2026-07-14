# Nmap Safety and Ethics

Nmap is a network discovery and port scanning tool. Unlike a passive
traffic capture, a scan is an **active** action against a target —
which is why the authorization precautions here are even more critical
than those described for the
[wireshark](../../wireshark/docs/packet-capture-safety.md) track.

## Authorization is mandatory

- **Never run a scan against hosts, networks, or systems that are not
  yours or for which you do not have explicit, written
  authorization.**
- Port scanning without authorization may be considered a crime in
  several jurisdictions, even when it causes no direct harm.
- In corporate environments, obtain formal authorization (e.g., an
  approved test window, defined scope) before any scan, even for study
  purposes.

## Recommended environments for the labs

- Your own virtual machines, on an isolated network (host-only/NAT).
- Legitimate test targets maintained for educational purposes (e.g.,
  `scanme.nmap.org`, which is publicly made available by the Nmap
  maintainers specifically for light, respectful testing — always
  check the official usage policy before using it).
- CTF environments or security labs created specifically for practice
  (e.g., your own vulnerable VMs).

## Best practices during the labs

- Prefer lower-impact scans when the goal is purely learning (avoid
  `-T5`/aggressive timing unless necessary).
- Always document the target, the time, and the justification for the
  scan.
- Avoid scans that could cause denial of service (e.g., large volumes
  of simultaneous connections) against systems with limited resources.

## Anonymization and data protection

- Before publishing any scan output (`outputs/`) or screenshot:
  - Replace real IPs with documentation addresses (`192.0.2.0/24`,
    `198.51.100.0/24`, `203.0.113.0/24`, per RFC 5737) or private
    ranges (`10.0.0.0/8`, `172.16.0.0/12`, `192.168.0.0/16`).
  - Remove hostnames, service banners, or versions that could identify
    a real third-party system.
  - Review the full output (including service banners, which may
    contain sensitive information) before committing.
- Never publish results of scans performed against third-party systems
  without explicit authorization for disclosure.

## Secure storage

- Keep raw, unreviewed outputs out of version control.
- Only version outputs that have already been reviewed and
  anonymized, following the patterns defined in
  [.gitignore](../../.gitignore).

## Purpose of this track

This track has an **exclusively educational and defensive** purpose:
the goal is to understand how scanning techniques work, how they show
up on the network, and how they can be detected and mitigated — not to
run tests against third-party systems without authorization.
