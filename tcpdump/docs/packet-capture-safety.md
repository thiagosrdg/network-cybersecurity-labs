# Packet Capture Safety and Ethics — tcpdump

tcpdump is a command-line packet capture tool. Like the
[wireshark](../../wireshark/docs/packet-capture-safety.md) track, it
performs **passive** traffic capture — so the same authorization and
anonymization principles apply, adapted here to a command-line
workflow where captures are frequently written straight to `.pcap`
files without inspecting each packet first.

## Prior authorization

- Never capture traffic on networks, systems, or devices that are not
  yours or for which you do not have explicit authorization.
- In corporate or third-party environments, obtain written
  authorization before any capture, even for study purposes.

## Owned or authorized environments

- Perform the labs in controlled environments: virtual machines,
  isolated networks (host-only/NAT), or your own study labs.
- Avoid capturing traffic on networks shared with third parties
  without explicit authorization from everyone involved.

## Least-privilege capture

- Run `tcpdump` with the narrowest capture filter (BPF expression) and
  the shortest duration/packet count needed for the lab (`-c <count>`,
  `-G <seconds>`), instead of capturing indiscriminately.
- Prefer `-i <interface>` targeting a specific lab interface over
  capturing on `any`, to avoid accidentally recording unrelated
  traffic.

## Data anonymization

Before publishing any capture or evidence, anonymize:

- **IP addresses** — replace real public IPs with documentation
  addresses (`192.0.2.0/24`, `198.51.100.0/24`, `203.0.113.0/24`, per
  RFC 5737) or private ranges (`10.0.0.0/8`, `172.16.0.0/12`,
  `192.168.0.0/16`).
- **MAC addresses** — replace with generic addresses or use
  anonymization tools.
- **Hostnames** — replace real names with generic identifiers (e.g.,
  `host-lab-01`).
- **Payload content** — when capturing with `-A`/`-X` (ASCII/hex
  dump), review the output for credentials or personal data before
  including it in documentation.

## Removal of credentials and session data

- Never publish captures containing passwords, authentication tokens,
  session cookies, API keys, or authorization headers in plain text.
- Use only lab environments with fictitious, disposable credentials
  when the captured traffic includes application-layer protocols such
  as HTTP.

## Secure storage

- Keep raw (non-anonymized) `.pcap` files out of version control, in a
  secure location with restricted access.
- Only version captures that have **already been reviewed and
  anonymized**.
- Use the patterns defined in [.gitignore](../../.gitignore) to avoid
  accidentally versioning sensitive files (e.g., `*.private.pcap`,
  `*.sensitive.pcapng`, `captures/raw/`).

## No publishing of third-party traffic

- Do not publish captures made on third-party networks or systems,
  even if anonymized, without explicit authorization for distribution.
- If in doubt about the origin or authorization of a capture, **do not
  publish it**.

## Review before committing

Before every commit that includes capture files or screenshots:

1. Open the `.pcap` file (e.g., in Wireshark) and confirm there is no
   remaining sensitive data.
2. Review screenshots of terminal output for personal public IPs, real
   hostnames, or other identifiable information.
3. Check the file size — avoid versioning very large captures; when
   needed, use smaller representative samples of the relevant traffic.
4. If in doubt about the sensitivity of a piece of data, **do not
   publish it** and consult [SECURITY.md](../../SECURITY.md).
