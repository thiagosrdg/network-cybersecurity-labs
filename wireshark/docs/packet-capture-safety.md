# Packet Capture Safety and Ethics

Network traffic capture and analysis inherently involve potentially
sensitive data. This document defines the guidelines that must be
followed **before capturing, analyzing, or versioning any traffic** in
this repository.

## Prior authorization

- Never capture traffic on networks, systems, or devices that are not
  yours or for which you do not have explicit authorization.
- In corporate or third-party environments, obtain written
  authorization before any capture, even for study purposes.

## Owned or authorized environments

- Perform the labs in controlled environments: virtual machines,
  isolated networks (host-only/NAT), or your own study labs.
- Avoid capturing traffic on networks shared with third parties (e.g.,
  corporate networks, public networks, home networks with other users)
  without explicit authorization from everyone involved.

## Data anonymization

Before publishing any capture or evidence, anonymize:

- **IP addresses** — replace real public IPs with documentation
  addresses (`192.0.2.0/24`, `198.51.100.0/24`, `203.0.113.0/24`, per
  RFC 5737) or private ranges (`10.0.0.0/8`, `172.16.0.0/12`,
  `192.168.0.0/16`).
- **MAC addresses** — replace with generic addresses or use
  anonymization tools (e.g., `tracewrangler`).
- **Hostnames** — replace real names with generic identifiers (e.g.,
  `host-lab-01`).
- **Usernames** — replace with generic identifiers (e.g., `user-lab`).

## Removal of credentials and session data

- Never publish captures containing passwords, authentication tokens,
  session cookies, API keys, or authorization headers in plain text.
- When analyzing HTTP traffic (see
  [Lab 04](../labs/04-http-traffic-analysis/README.md)), use only lab
  environments with fictitious, disposable credentials.
- Review HTTP headers (`Authorization`, `Cookie`, `Set-Cookie`) before
  including any capture or screenshot in the documentation.

## Care with personal data

- Avoid capturing traffic involving real personal accounts, personal
  e-mails, banking data, or any identifiable information.
- Prefer generating synthetic traffic specifically for the lab's
  purposes (see the section below).

## Secure storage

- Keep raw (non-anonymized) capture files out of version control, in a
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

## Creating synthetic traffic in labs

- Whenever possible, generate the traffic to be analyzed yourself
  (e.g., `ping`, controlled DNS queries, HTTP requests to local test
  servers).
- This ensures full control over the captured content and eliminates
  the risk of exposing third-party data.

## Review before committing

Before every commit that includes capture files or screenshots:

1. Open the `.pcap`/`.pcapng` file and confirm there is no remaining
   sensitive data.
2. Review screenshots for personal public IPs, real hostnames,
   e-mails, or other identifiable information visible in the Wireshark
   interface.
3. Check the file size — avoid versioning very large captures; when
   needed, use smaller representative samples of the relevant traffic.
4. If in doubt about the sensitivity of a piece of data, **do not
   publish it** and consult [SECURITY.md](../../SECURITY.md).
