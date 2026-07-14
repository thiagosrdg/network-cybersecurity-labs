# Capture Filters vs Display Filters

Wireshark uses two distinct types of filters, with different syntax
and purposes. Understanding this difference is essential before
starting any lab.

## Conceptual difference

| Aspect | Capture Filter | Display Filter |
|---|---|---|
| When applied | Before/during capture | After capture, on already-captured packets |
| What it does | Decides **which packets are captured** | Decides **which already-captured packets are shown** |
| Syntax | Based on BPF (Berkeley Packet Filter) | Wireshark's own syntax (richer and more granular) |
| Can it be changed later? | No — packets discarded during capture cannot be recovered | Yes — can be reapplied as many times as needed |
| Where it's configured | In the capture options, before starting | In the filter bar, at any time |

In short: **capture filters reduce the volume of captured data**,
while **display filters help navigate and investigate** the data
already captured. In analysis labs, it's common to capture more
broadly and refine the investigation with display filters (see
[wireshark-display-filters.md](wireshark-display-filters.md)).

## Capture filter syntax (BPF)

Common examples:

```text
host 192.168.1.10
net 192.168.1.0/24
port 53
tcp port 443
udp port 53
icmp
src host 192.168.1.10
dst host 192.168.1.20
```

### Quick explanation

- `host 192.168.1.10` — captures all traffic to/from the given host.
- `net 192.168.1.0/24` — captures all traffic within the given
  network.
- `port 53` — captures traffic (TCP or UDP) on port 53 (DNS).
- `tcp port 443` — captures only TCP traffic on port 443 (HTTPS).
- `udp port 53` — captures only UDP traffic on port 53 (DNS).
- `icmp` — captures only ICMP traffic.
- `src host 192.168.1.10` — captures traffic whose source is the given
  host.
- `dst host 192.168.1.20` — captures traffic whose destination is the
  given host.

## Best practices

- Use capture filters when the expected traffic volume is large and
  the focus of the analysis is already known (e.g., capturing only DNS
  traffic).
- Avoid overly restrictive capture filters in exploratory labs —
  packets discarded during capture are permanently lost.
- For broad or exploratory investigations, prefer capturing without a
  filter (or with a minimal filter) and refining the analysis with
  display filters.
- Always document which capture filter (if any) was used, to ensure
  the lab is reproducible.
