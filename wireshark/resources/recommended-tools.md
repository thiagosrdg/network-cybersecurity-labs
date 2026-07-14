# Recommended Tools

Complementary tools that can be used throughout the labs in this
repository, besides Wireshark itself. The list has a defensive and
educational purpose — no listed tool is presented as a requirement for
offensive use.

## Wireshark

Graphical network protocol analyzer, used as the main tool in this
repository to inspect traffic captures, apply filters, and investigate
protocol behavior in detail.

## TShark

Command-line version of Wireshark, useful for automation, analysis on
servers without a graphical interface, and processing captures in
scripts.

## tcpdump

Command-line packet capture tool, widely available on Unix-like
systems. Frequently used to generate `.pcap` captures in lab
environments that are later analyzed in detail in Wireshark.

## Nmap

Network discovery and port scanning tool. In this repository, it is
mentioned only as a generator of controlled traffic in owned labs
(e.g., to study how a port scan shows up in a capture), not as a tool
for attacking third parties.

## Zeek

Network traffic analysis framework aimed at security monitoring,
capable of generating structured logs of connections and protocols
from traffic captures. Useful as a complement to Wireshark in
larger-scale analyses.

## NetworkMiner

Network forensics tool that extracts artifacts (files, credentials,
sessions) from `.pcap` captures. Used to complement manual
investigation done in Wireshark, always in controlled lab
environments.

## CyberChef

Web application for transforming, decoding, and analyzing data (e.g.,
Base64 decoding, hashes, payload extraction). Useful for examining
content extracted from packets during an investigation.

## Python

Language used to automate analysis tasks, programmatically process
captures (e.g., with libraries such as `pyshark`), and support the
generation of technical reports.

## Scapy

Python library for creating, manipulating, and sending network
packets. Used in controlled labs to generate specific synthetic
traffic (e.g., custom ICMP packets) that is then analyzed in
Wireshark.
