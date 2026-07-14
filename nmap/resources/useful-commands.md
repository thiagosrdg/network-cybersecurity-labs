# Useful Nmap Commands

Quick reference for common Nmap commands and flags, for use during the
labs. All examples must be run only against owned or authorized
targets (see
[docs/scanning-safety-and-ethics.md](../docs/scanning-safety-and-ethics.md)).

## Host discovery

```text
nmap -sn 192.168.1.0/24
```

Performs only active host discovery on the network, without port
scanning (equivalent to a "ping scan").

## Basic port scanning

```text
nmap 192.168.1.10
nmap -p 1-1000 192.168.1.10
nmap -p- 192.168.1.10
```

- `-p 1-1000` — limits the scan to a port range.
- `-p-` — scans all 65535 TCP ports.

## Scan types

```text
nmap -sS 192.168.1.10
nmap -sT 192.168.1.10
nmap -sU 192.168.1.10
```

- `-sS` — SYN scan (half-open), requires elevated privileges.
- `-sT` — TCP connect scan, completes the three-way handshake.
- `-sU` — UDP port scan.

## Service and version detection

```text
nmap -sV 192.168.1.10
```

Attempts to identify the service and version running on each open
port.

## Operating system detection

```text
nmap -O 192.168.1.10
```

Attempts to infer the target's operating system based on TCP/IP stack
characteristics.

## Nmap Scripting Engine (NSE)

```text
nmap -sC 192.168.1.10
nmap --script=default 192.168.1.10
```

Runs standard NSE reconnaissance scripts. More invasive scripts should
be used with extra caution and only in authorized environments.

## Full reconnaissance scan

```text
nmap -sS -sV -O -p- 192.168.1.10
```

Combines SYN scan, version detection, OS detection, and a scan of all
ports. A slower, "noisier" scan — use in moderation.

## Timing control

```text
nmap -T2 192.168.1.10
nmap -T4 192.168.1.10
```

Controls the timing aggressiveness of the scan (`-T0` slower/stealthier
to `-T5` faster/more aggressive). Prefer more conservative values in
labs with limited resources.

## Exporting results

```text
nmap -oN output.txt 192.168.1.10
nmap -oX output.xml 192.168.1.10
nmap -oG output.gnmap 192.168.1.10
```

- `-oN` — normal text output.
- `-oX` — XML output (useful for further processing).
- `-oG` — "grepable" output (legacy format, still useful in scripts).

Remember to review and anonymize any output file before adding it to
`labs/**/outputs/`.
