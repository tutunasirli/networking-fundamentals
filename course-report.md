# Networking Fundamentals — Course Report

## 1. Introduction

This report summarizes the key concepts covered in the **Ağ Temelleri** training completed through BTK Akademi. The course introduces the foundations of computer networking, addressing, communication protocols, wireless technologies, internet connectivity, and network security.

## 2. Network Fundamentals and Connected Devices

A computer network allows devices to exchange information and share resources.

Key concepts:
- **Internet:** A global network of interconnected networks.
- **LAN / WAN:** Local-area networks cover limited locations; wide-area networks connect networks across larger geographic areas.
- **SOHO network:** A small office/home office network.
- **End device:** A source or destination of network data, such as a computer, phone, or server.
- **Intermediary device:** A device that forwards or controls traffic, such as a switch or router.
- **Client/server:** A client requests a service; a server provides it.
- **Peer-to-peer (P2P):** Devices can share resources directly.
- **IoT and connected devices:** Sensors, actuators, RFID tags, smartwatches, smart cars, and home devices can collect or act on data.

## 3. Data, Signals, and Network Performance

Data is represented digitally as bits. Devices encode information and transmit it through network media.

- **Bit and byte:** A bit is a binary digit; a byte commonly consists of eight bits.
- **Signals:** Data can travel as electrical, optical, or wireless signals.
- **Network media:** The physical or wireless path used to carry data.
- **Bandwidth:** The theoretical or configured capacity of a link.
- **Throughput:** The actual achieved data-transfer rate.
- **bps:** Bits per second, with common multiples such as kbps, Mbps, and Gbps.

Bandwidth and throughput are related but not identical; real throughput is affected by overhead, congestion, interference, and equipment capabilities.

## 4. Network Devices and Topologies

Common devices include switches, routers, wireless access points, multilayer switches, and firewalls.

- **Switch:** Forwards frames inside a LAN using MAC address information.
- **Router:** Forwards packets between IP networks using a routing table.
- **Firewall:** Applies security rules to network traffic.
- **Physical topology:** The actual arrangement of cables and devices.
- **Logical topology:** The path or structure through which data flows.
- **Hierarchical design:** Larger networks may be organized into access, distribution, and core layers.

## 5. Network Interfaces, Ethernet, and Media

A network interface card (NIC) connects a device to a network. Ethernet is a widely used LAN technology.

Topics covered:
- MAC addresses and physical addressing
- Ethernet frames and MAC address tables
- Copper, coaxial, twisted-pair, and fiber-optic cables
- UTP and STP cabling
- RJ-11 and RJ-45 connectors
- T568A and T568B wiring schemes
- Straight-through and crossover cables
- Differences between like and unlike devices in traditional cabling examples

Fiber-optic cable transmits data using light. Copper Ethernet uses electrical signaling. Wireless media uses radio waves.

## 6. Ethernet Switching, ARP, and Broadcasts

A switch learns source MAC addresses from incoming frames and uses its MAC address table to forward frames.

- **ARP:** Resolves a local IPv4 address to a MAC address on an IPv4 LAN.
- **Broadcast:** A frame or packet sent to all applicable devices in a broadcast scope.
- **Broadcast domain:** The set of devices that receive a Layer 2 broadcast.
- **Broadcast containment:** Routers and VLAN boundaries can limit Layer 2 broadcast scope.
- **Logical grouping:** Devices can be grouped by network design, even when they are not physically adjacent.

## 7. IP Addressing: IPv4 and Subnetting

IPv4 addresses are 32 bits long and are commonly displayed as four decimal octets.

Example: `192.168.10.10/24`

- Subnet mask: `255.255.255.0`
- Network address: `192.168.10.0`
- Typical usable host range: `192.168.10.1`–`192.168.10.254`
- Broadcast address: `192.168.10.255`

A subnet mask or CIDR prefix identifies the network and host portions of an address. A default gateway is used to reach destinations outside the local subnet.

### Private IPv4 addressing

The private IPv4 ranges defined by RFC 1918 are:
- `10.0.0.0/8`
- `172.16.0.0/12`
- `192.168.0.0/16`

Private addresses are not globally routed across the public internet. Network Address Translation (NAT) is commonly used at network boundaries to translate private addresses to public addresses.

### Classful and classless addressing

Classful addressing divides IPv4 space into historical classes. Modern networks generally use classless addressing (CIDR), which supports flexible prefix lengths and more efficient address allocation.

## 8. IPv6

IPv6 uses 128-bit addresses written in hexadecimal groups separated by colons.

Important concepts:
- Leading zeros within a group can be omitted.
- One consecutive run of zero groups can be compressed using `::` once in an address.
- Link-local addresses support communication on a local link.
- Dual stack allows IPv4 and IPv6 to operate together.
- Tunneling carries one protocol across infrastructure that uses another.
- Translation mechanisms support communication between IPv4 and IPv6 environments.
- SLAAC enables stateless address autoconfiguration using router advertisements.

`2001:db8::/32` is reserved for documentation examples.

## 9. DHCP and Automatic Configuration

The Dynamic Host Configuration Protocol (DHCP) provides settings such as IP address, subnet mask, default gateway, and DNS server.

The common DHCPv4 address-allocation sequence is **DORA**:
1. Discover
2. Offer
3. Request
4. Acknowledge

DHCP clients request configuration from a DHCP server. A DHCP range or pool defines the addresses available for assignment. Hosts can also be configured manually, but incorrect manual settings may cause connectivity problems or address conflicts.

## 10. Routing and Communication Between Networks

A router uses its routing table to choose a path toward a destination network.

- **Connected route:** A network directly attached to a router interface.
- **Default route:** A fallback route used when no more specific route matches.
- **Default gateway:** The router interface a host uses to reach remote networks.
- **Path selection:** The router chooses a matching route according to routing-table rules.

Hosts on different IP subnets generally need a Layer 3 device, such as a router, to communicate. The practical example in this repository demonstrates this principle.

## 11. Transport Layer: TCP, UDP, Ports, and Sockets

TCP and UDP provide transport-layer communication for applications.

| TCP | UDP |
|---|---|
| Connection-oriented | Connectionless |
| Provides ordered, reliable byte-stream delivery | Does not provide TCP-style delivery guarantees |
| Uses sequencing and acknowledgements | Has lower protocol overhead |
| Commonly used by HTTPS and SSH | Commonly used for DNS queries and real-time applications, depending on the service |

A port number identifies an application endpoint on a host. A socket is commonly described using an IP address, transport protocol, and port. A socket pair identifies the endpoints of a connection.

Common port examples:
- SSH: TCP 22
- DNS: UDP/TCP 53
- HTTP: TCP 80
- HTTPS: TCP 443
- DHCPv4: UDP 67/68
- SMTP: TCP 25; message submission commonly uses 587
- POP3: TCP 110; POP3S 995
- IMAP: TCP 143; IMAPS 993

Port assignments are common defaults; actual services may use different ports.

## 12. Application Protocols and Network Services

- **DNS:** Resolves domain names to records such as IP addresses.
- **HTTP/HTTPS:** Used for web communication; HTTPS protects traffic using TLS.
- **SSH:** Secure remote administration.
- **FTP:** File transfer; security depends on the selected mode and configuration.
- **SMTP:** Sends or relays email.
- **POP3 and IMAP:** Retrieve or manage email.
- **DHCP:** Supplies host network configuration.
- **HTML:** A markup language used to structure web pages.
- **Telnet:** A legacy remote terminal protocol that does not encrypt traffic and should generally be avoided for administration on untrusted networks.
- **VoIP:** Carries voice communications over IP networks.

## 13. Wireless Networking

Wireless networks use radio signals to provide mobility and connectivity.

Topics covered:
- Wi-Fi and IEEE 802.11 standards
- 2.4 GHz and 5 GHz frequency bands
- Access points and internet ports on wireless routers
- SSID and SSID broadcast
- Wireless channels and mixed-mode operation
- CSMA/CA (Carrier Sense Multiple Access with Collision Avoidance)
- RTS/CTS and acknowledgements
- MAC address filtering
- Ethernet over Powerline as an alternative way to extend network connectivity

The 2.4 GHz band often provides better reach through obstacles but can be congested. The 5 GHz band can provide more capacity but often has less range through obstacles. Actual results depend on equipment, interference, distance, and environment.

## 14. Internet Access, Cloud, and Virtualization

Internet Service Providers (ISPs) connect customers to the internet using technologies such as cable and DSL.

Cloud and virtualization concepts:
- **Cloud computing:** Computing resources delivered over a network.
- **SaaS:** Software as a Service.
- **PaaS:** Platform as a Service.
- **IaaS:** Infrastructure as a Service.
- **ITaaS:** IT resources delivered as a service.
- **Virtualization:** Running multiple virtual systems or network functions on shared physical resources.
- **Type 1 hypervisor:** Runs directly on host hardware.
- **Type 2 hypervisor:** Runs on top of a host operating system.
- **Network virtualization:** Creates logical networks over shared infrastructure.
- **SDN:** Software-Defined Networking supports programmable network control.
- **Control plane and data plane:** The control plane determines forwarding behavior; the data plane forwards traffic.
- **Bluetooth pairing:** Establishes a trusted connection between Bluetooth devices.

## 15. Network Security

Common threats and protections include:

- **Social engineering:** Manipulating people to disclose information or perform unsafe actions.
- **Phishing / vishing:** Fraudulent messages or calls designed to obtain information.
- **Malware:** Includes viruses, worms, Trojans, spyware, adware, and botnet-related threats.
- **DoS / DDoS:** Attempts to make services unavailable by exhausting resources.
- **Software vulnerabilities:** Weaknesses that may be exploited by attackers.
- **Firewall:** Enforces traffic policies.
- **Patching and updates:** Fix known defects and vulnerabilities.
- **Antivirus and anti-spyware tools:** Help detect or block some malicious software.
- **Popup and antispam blockers:** Reduce certain unwanted content and messages.
- **Strong authentication and least privilege:** Reduce the impact of compromised accounts.

Security is strongest when multiple controls are combined. No single tool prevents every attack.

## 16. Troubleshooting Commands

| Command | Typical use |
|---|---|
| `ping` | Tests IP reachability using ICMP |
| `tracert` / `traceroute` | Shows the path toward a destination |
| `ipconfig` | Displays Windows IP configuration |
| `ipconfig /all` | Displays detailed Windows network configuration |
| `nslookup` | Queries DNS |
| `netstat -ano` | Shows connections, listening ports, and process IDs on Windows |
| `show ip interface brief` | Summarizes Cisco router interface addresses and states |
| `show ip route` | Displays the Cisco router's IPv4 routing table |
| `show arp` | Displays ARP entries on supported Cisco devices |

A failed ping does not always mean a device is offline; ICMP can be filtered. Interpret the result alongside interface status, routing, DNS, and service-specific tests.

## 17. Conclusion

The training introduced the core concepts required to understand how devices connect, address one another, exchange data, and access network services. The Packet Tracer lab included in this repository applies the concepts of IPv4 addressing, default gateways, switching, and routing by connecting two separate LANs through a router.

The repository is intended to grow with further study and practical work, including subnetting, VLANs, inter-VLAN routing, DHCP, and access control lists.
