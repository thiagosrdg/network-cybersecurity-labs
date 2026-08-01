# Packet Tracer Lab Environment and Methodology

Cisco Packet Tracer is a network simulator: every device, link, and
address in these labs is virtual, and no lab in this track touches
real or third-party infrastructure. Even so, this document keeps the
same documentation discipline used across the other tracks in this
repository.

## Lab environment

- All topologies are built entirely inside Packet Tracer. No lab
  requires access to real hardware, a real ISP, or any network you do
  not own.
- Addressing follows private ranges (`10.0.0.0/8`, `172.16.0.0/12`,
  `192.168.0.0/16`) or documentation ranges (`192.0.2.0/24`,
  `198.51.100.0/24`, `203.0.113.0/24`, per RFC 5737).
- If a lab is inspired by a real network design (e.g., from a course,
  a certification study guide, or a workplace diagram), it must be
  rebuilt with synthetic device names, hostnames, and addressing —
  never a direct copy of a real, identifiable topology.

## Methodology

Each lab in this track follows the same general approach:

1. Define the objective and the concepts to be practiced.
2. Sketch the topology and the IP addressing plan before configuring
   any device.
3. Build the topology in Packet Tracer.
4. Configure devices incrementally, verifying connectivity at each
   stage (e.g., Layer 2 before Layer 3, routing before ACLs).
5. Validate the final result with `show`/`ping`/`traceroute` and, when
   useful, Packet Tracer's Simulation mode to inspect packet flow.
6. Document the configuration, verification steps, and any issues
   encountered.
7. Record key findings and, when applicable, security-relevant
   observations (e.g., the effect of an ACL, the impact of disabling
   port security).

## Evidence and storage

- Save the working topology as a `.pkt` file in the lab's
  `topologies/` directory, when the file size and content allow it.
- Save relevant screenshots (topology diagram, `show` command output,
  simulation results) in the lab's `screenshots/` directory.
- `.pkt` files are binary; keep them reasonably small and avoid
  committing multiple redundant versions of the same lab — use Git
  history for iteration instead of keeping old copies in the
  directory.

## Purpose of this track

This track has an **exclusively educational** purpose: to build
practical skills in network design, Cisco IOS configuration, and
troubleshooting, and to document that learning process in a clear and
reproducible way.
