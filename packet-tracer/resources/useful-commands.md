# Useful Cisco IOS Commands

Quick reference for common Cisco IOS commands used during the Packet
Tracer labs.

## Basic device configuration

```text
enable
configure terminal
hostname R1
enable secret cisco123
service password-encryption
line console 0
 password cisco123
 login
line vty 0 4
 password cisco123
 login
 transport input ssh
```

## Interface configuration

```text
interface GigabitEthernet0/0
 description Link to LAN
 ip address 192.168.1.1 255.255.255.0
 no shutdown
```

## VLANs and trunking (switches)

```text
vlan 10
 name USERS
vlan 20
 name SERVERS

interface FastEthernet0/1
 switchport mode access
 switchport access vlan 10

interface GigabitEthernet0/1
 switchport mode trunk
 switchport trunk allowed vlan 10,20
```

## Inter-VLAN routing (router-on-a-stick)

```text
interface GigabitEthernet0/0.10
 encapsulation dot1Q 10
 ip address 192.168.10.1 255.255.255.0

interface GigabitEthernet0/0.20
 encapsulation dot1Q 20
 ip address 192.168.20.1 255.255.255.0
```

## Static routing

```text
ip route 192.168.20.0 255.255.255.0 192.168.1.2
ip route 0.0.0.0 0.0.0.0 192.168.1.254
```

## Basic dynamic routing (OSPF)

```text
router ospf 1
 network 192.168.1.0 0.0.0.255 area 0
 network 192.168.2.0 0.0.0.255 area 0
```

## Access control lists (ACLs)

```text
access-list 100 permit tcp any host 192.168.1.10 eq 80
access-list 100 deny ip any any
interface GigabitEthernet0/0
 ip access-group 100 in
```

## Port security (switches)

```text
interface FastEthernet0/1
 switchport mode access
 switchport port-security
 switchport port-security maximum 1
 switchport port-security violation shutdown
 switchport port-security mac-address sticky
```

## Verification commands

```text
show running-config
show ip interface brief
show vlan brief
show interfaces trunk
show ip route
show mac address-table
ping <ip>
traceroute <ip>
```

## Saving configuration

```text
copy running-config startup-config
```

Remember to review the final configuration and topology before
committing anything to `labs/**/topologies/` or `labs/**/screenshots/`
(see
[docs/lab-environment-and-methodology.md](../docs/lab-environment-and-methodology.md)).
