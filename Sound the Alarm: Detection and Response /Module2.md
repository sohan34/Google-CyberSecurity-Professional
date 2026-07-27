# Course 6 — Module 2

## Table of Contents

- [Network Monitoring](#network-monitoring)
- [Packet Analysis and Packet Captures](#packet-analysis-and-packet-captures)
- [IPv4 and IPv6 Headers](#ipv4-and-ipv6-headers)
- [Wireshark](#wireshark)
- [tcpdump](#tcpdump)
- [Terms and Definitions](#terms-and-definitions-course-6-module-2)

---

## Network Monitoring

Network communication can be noisy. Events like sending an email, streaming a video, or visiting a website all produce network communications in the form of **network traffic** and **network data**.

- **Network traffic:** The amount of data that moves across a network. It can also include the type of data transferred, such as HTTP.
- **Network data:** The data that is transmitted between devices on a network.

Network monitoring is essential for maintaining situational awareness of activity on a network. By collecting and analyzing network traffic, organizations can detect suspicious activity.

### Know Your Network

Networks connect devices, and devices communicate and exchange data using network protocols. Network communications provide information such as:

- Source and destination IP addresses
- Amount of data transferred
- Date and time
- More

This information helps security professionals develop a **baseline** of normal behavior.

**Baseline:** A reference point used for comparison.

Baselines help establish a standard of expected or normal behavior for systems, devices, and networks. Knowing normal network behavior makes it easier to identify abnormal behavior.

### Monitor Your Network

Once a baseline is established, you can monitor a network to identify deviations from that baseline.

Monitoring involves examining network components to detect unusual activity, such as large or unusual data transfers.

#### Flow Analysis

**Flow** refers to the movement of network communications and includes information related to packets, protocols, and ports.

- Packets can travel to ports.
- Ports receive and transmit communications.
- Ports are often, but not always, associated with network protocols.

Example:

- Port 443 is commonly used by HTTPS, a protocol that provides website traffic encryption.

Malicious actors can use protocols and ports that are not commonly associated with each other to maintain communications between a compromised system and their own machine. This is known as **command and control (C2)**.

- **Command and control (C2):** The techniques used by malicious actors to maintain communications with compromised systems.

Example:

- Malicious actors may use HTTPS over port 8088 instead of the commonly associated port 443.

Organizations must know which ports should be open and approved for connections and watch for mismatches between ports and protocols.

#### Packet Payload Information

Network packets contain transmission components such as:

- Source and destination IP addresses
- Packet payload information

**Packet payload information:** The actual data transmitted in the packet.

This data is often encrypted and may require decryption to be readable. Monitoring payload information can uncover unusual activity, such as sensitive data transmitting outside the network, which may indicate a **data exfiltration** attack.

- **Data exfiltration:** Unauthorized transmission of data from a system.

#### Temporal Patterns

Network packets contain time-related information that can reveal patterns.

Example:

- A company operating in North America may normally experience bulk traffic between 9 a.m. and 5 p.m.

If large volumes of traffic appear outside normal hours, that is considered **off baseline** and should be investigated.

### Protect Your Network

Security operations centers (SOCs) monitor systems against security threats and attacks. Organizations may also deploy a **network operations center (NOC)**.

- **SOC:** Focuses on maintaining security through detection and response
- **NOC:** Focuses on maintaining network performance, availability, and uptime

Security analysts monitor networks to identify **indicators of compromise (IoC)** and protect networks from threats or attacks.

- **Indicators of compromise (IoC):** Observable evidence that suggests signs of a potential security incident.

### Network Monitoring Tools

Network monitoring can be automated or manual. Common tools include:

#### Intrusion Detection Systems (IDS)

- Monitor system activity
- Alert on possible intrusions
- Commonly inspect packet payload content for patterns associated with malware or phishing

#### Network Protocol Analyzers

Also known as **packet sniffers**, these tools capture and analyze data traffic within a network.

Examples:

- `tcpdump`
- Wireshark

Packet captures created by these tools can be investigated to identify potentially malicious activity.

### Key Takeaways

- Monitoring and protecting networks is a key responsibility of security professionals.
- Baselines help identify deviations from expected traffic patterns.
- IDS tools and network protocol analyzers support network monitoring efforts.

---

## Packet Analysis and Packet Captures

Security analysts monitor and analyze network traffic flows by generating packet captures and examining the traffic for unusual activity.

### Packets

A **data packet** is a basic unit of information that travels from one device to another within a network.

- **Data packet:** A basic unit of information that travels from one device to another within a network.

Packets form the basis of information exchange over a network. Each time you visit a website or upload data, packets are sent and received between your computer and the server.

Example:

- When uploading an image to a website, the data is broken into multiple packets, routed to the destination, and reassembled upon delivery.

Packets provide context during investigations and help analysts identify abnormalities.

### Packet Components

Packets contain three components:

- Header
- Payload
- Footer

#### Header

The header is the most essential component of a packet.

Packets can have several headers depending on the protocols used, such as:

- Ethernet header
- IP header
- TCP header

Headers provide routing information such as:

- Source and destination IP addresses
- Packet length
- Protocol
- Packet identification numbers
- More

#### Payload

The payload directly follows the header and contains the actual data being delivered.

Example:

- In an image upload, the image itself is the payload.

#### Footer

The footer, also known as the trailer, is located at the end of a packet.

- Ethernet uses footers to provide error-checking information to determine if data has been corrupted.
- Most protocols, such as IP, do not use footers.

**Note:** Ethernet packets analyzed in some tools may not display footer information due to network configurations.

### Network Protocol Analyzers

**Network protocol analyzers** or **packet sniffers** are tools designed to capture and analyze data traffic within a network.

Examples include:

- `tcpdump`
- Wireshark
- TShark

These tools can be used to:

- Monitor networks and identify suspicious activity
- Collect network statistics such as bandwidth or speed
- Troubleshoot network performance issues like slowdowns

They can also be misused by malicious actors to capture sensitive data such as login information.

### How Network Protocol Analyzers Work

Network protocol analyzers use software and hardware to capture and display traffic.

#### 1. Capturing Traffic Through the NIC

Packets are collected through the **Network Interface Card (NIC)**.

- **Network Interface Card (NIC):** Hardware that connects computers to a network.

By default, NICs only listen to traffic addressed to them. To capture all visible traffic, the NIC must be placed into:

- Monitoring mode
- Promiscuous mode

This allows access to all visible network packets, but it does not mean the analyzer can access all packets across the entire network. The tool must be placed in the appropriate network segment.

**Note:** Promiscuous mode can expose a device to attacks because it allows sensitive information like passwords and confidential data to be captured. Use responsibly.

#### 2. Converting Binary to Readable Format

Network traffic is collected in raw binary format, which consists of 0s and 1s.

The analyzer converts binary data into a human-readable format so analysts can interpret it.

### Packet Capturing

**Packet sniffing** is the practice of capturing and inspecting data packets across a network.

- **Packet capture (p-cap):** A file containing data packets intercepted from an interface or network.

Packet captures can be viewed and analyzed using network protocol analyzers. They can also be filtered to show only the data relevant to an investigation.

**Note:** Intercepting and examining private network communications without permission is illegal in many places.

### Packet Capture Formats and Libraries

Packet capture files come in different formats depending on the library used.

#### Libpcap

- Designed for Unix-like systems such as Linux and macOS
- Used as the default packet capture file format by tools like `tcpdump`

#### WinPcap

- Open-source packet capture library for Windows
- Older format and not predominantly used

#### Npcap

- Library designed by Nmap
- Commonly used in Windows operating systems

#### PCAPng

- Modern format
- Can simultaneously capture packets and store data
- “ng” stands for next generation

### Key Takeaways

- Network protocol analyzers help investigators understand activity on a network.
- Packet captures provide data for detailed analysis.
- Analyzing packet captures is an essential network security skill.

---

## IPv4 and IPv6 Headers

Internet Protocol (IP) includes standards used for routing and addressing data packets as they travel between devices on a network. IP is the foundation for all internet communications.

Two versions are used today:

- IPv4
- IPv6

### IPv4

IPv4 is the most commonly used version of IP.

IPv4 headers have 13 fields:

1. **Version:** Indicates the IP version
2. **Internet Header Length (IHL):** Specifies the length of the IPv4 header including Options
3. **Type of Service (ToS):** Provides information about packet priority
4. **Total Length:** Specifies the total length of the packet including header and data
5. **Identification:** Identifies fragments of the original packet for reassembly
6. **Flags:** Provides fragmentation information
7. **Fragment Offset:** Identifies the correct sequence of fragments
8. **Time to Live (TTL):** Limits how long a packet can circulate in a network
9. **Protocol:** Specifies the protocol used for the data portion
10. **Header Checksum:** Used for error checking the header
11. **Source Address:** The sender’s address
12. **Destination Address:** The receiver’s address
13. **Options:** Optional security options for the packet

### IPv6

IPv6 adoption has been increasing because of its large address space.

IPv6 headers have 8 fields:

1. **Version:** Indicates the IP version
2. **Traffic Class:** Similar to IPv4 ToS; provides priority or class information
3. **Flow Label:** Identifies packets in a flow
4. **Payload Length:** Specifies the length of the data portion
5. **Next Header:** Indicates the type of header that follows the IPv6 header
6. **Hop Limit:** Similar to IPv4 TTL; limits how long a packet can travel before being discarded
7. **Source Address:** The sender’s address
8. **Destination Address:** The receiver’s address

Header fields contain valuable information for investigations, and tools like Wireshark help display them in human-readable form.

### Key Takeaways

- IP is the standard used for routing and addressing packets.
- IPv4 and IPv6 use different header structures.
- Header fields provide important investigative details.

---

## Wireshark

Wireshark is an open-source network protocol analyzer. It uses a graphical user interface (GUI), which makes packet analysis easier to visualize.

### Display Filters

Wireshark display filters let you apply filters to packet capture files.

You can filter by:

- Protocols
- IP addresses
- Ports
- Other packet properties

#### Comparison Operators

Comparison operators can be expressed using symbols or abbreviations.

| Operator Type | Symbol | Abbreviation |
|---|---|---|
| Equal | == | eq |
| Not equal | != | ne |
| Greater than | > | gt |
| Less than | < | lt |
| Greater than or equal to | >= | ge |
| Less than or equal to | <= | le |

You can combine comparison operators with Boolean logic like `and` and `or`. Parentheses can be used to group expressions.

#### Contains Operator

The `contains` operator filters packets that contain an exact string match.

#### Matches Operator

The `matches` operator filters packets based on a regular expression (regex).

### Filter Toolbar

Wireshark filters are entered in the filter toolbar.

Example:

- `dns` displays packets containing the DNS protocol

### Filter for Protocols

Simply type the protocol name into the filter toolbar.

Examples:

- `dns`
- `http`
- `ftp`
- `ssh`
- `arp`
- `telnet`
- `icmp`

### Filter for an IP Address

Use the following filters:

- `ip.addr == 172.21.224.2`
- `ip.src == 10.10.10.10`
- `ip.dst == 4.4.4.4`

### Filter for a MAC Address

A Media Access Control (MAC) address is a unique alphanumeric identifier assigned to each physical device on a network.

Example:

- `eth.addr == 00:70:f4:23:18:c4`

### Filter for Ports

Use port filters to isolate specific traffic.

Examples:

- `udp.port == 53`
- `tcp.port == 25`

### Follow Streams

Wireshark can filter for packets specific to a protocol and view streams.

A stream or conversation is the exchange of data between devices using a protocol. Wireshark reassembles the stream so it is easier to read.

This is useful for examining conversations such as HTTP request and response messages.

### Key Takeaways

- Wireshark is useful for inspecting packet capture files.
- Display filters help isolate relevant network packets.
- Packet analysis is an essential skill for security analysts.

---

## tcpdump

`tcpdump` is a command-line network protocol analyzer.

A **command-line interface (CLI)** is a text-based user interface that uses commands to interact with the computer.

`tcpdump` is used to capture network traffic. This traffic can be saved to a packet capture file for later analysis.

`tcpdump` comes pre-installed in many Linux distributions and can also be installed on Unix-based operating systems such as macOS.

**Note:** Network traffic is often encrypted, so inspecting packets may require decrypting data using the appropriate private keys.

### Capturing Packets with tcpdump

Capturing packets with `tcpdump` usually requires administrator-level privileges.

You must either:

- Be logged in as the root user
- Have permission to use `sudo`

- **Root user (or superuser):** A user with elevated privileges to modify the system.
- **Sudo:** A command that temporarily grants elevated permissions to specific users.

#### Basic Syntax

    sudo tcpdump [-i interface] [option(s)] [expression(s)]

- `sudo tcpdump` runs `tcpdump` with elevated permissions
- `-i` specifies the network interface to capture traffic from
- `option(s)` are optional
- `expression(s)` further filter traffic

Before capturing traffic, you can list available interfaces with:

    tcpdump -D

### Options

Options, also known as flags, can be added to control how `tcpdump` works.

Short options use a single hyphen, and long options use two hyphens.

**Note:** Options are case-sensitive. For example, `-w` and `-W` are different.

**Note:** Short options with values can sometimes be written with or without a space. For example:

- `sudo tcpdump -i any -c 3`
- `sudo tcpdump -iany -c3`

Both are equivalent.

#### `-w`

Writes captured packets to a file instead of printing them in the terminal.

Example:

    sudo tcpdump -i any -w packetcapture.pcap

#### `-r`

Reads a packet capture file.

Example:

    sudo tcpdump -r packetcapture.pcap

#### `-v`

Prints more packet information.

Verbosity levels include:

- `-v`
- `-vv`
- `-vvv`

The more `v`s, the more detailed the output.

Example:

    sudo tcpdump -r packetcapture.pcap -v

#### `-c`

Controls how many packets `tcpdump` captures.

Examples:

- `-c 1` captures one packet
- `-c 10` captures ten packets

Example:

    sudo tcpdump -i any -c 3

#### `-n`

Disables name resolution.

By default, `tcpdump` converts IP addresses to names and ports to commonly associated services. This can be misleading.

`-n` prevents hostname resolution. `-nn` prevents both hostnames and ports from being resolved.

**Pro tip:** Disabling name resolution is best practice when sniffing or analyzing traffic.

Example:

    sudo tcpdump -r packetcapture.pcap -v -n

### Expressions

Filter expressions are optional but useful for packet analysis.

Examples:

- `ip6` filters for IPv6 traffic
- Boolean logic like `and`, `or`, and `not` can further filter traffic

Example:

    sudo tcpdump -r packetcapture.pcap -n 'ip and port 80'

You can use single or double quotes to ensure all expressions are executed. Parentheses can be used to group and prioritize expressions.

Example:

- `ip and (port 80 or port 443)`

### Interpreting Output

`tcpdump` prints one line of text for each packet, and each line begins with a timestamp.

Example:

    sudo tcpdump -i any -v -c 1

The output typically includes:

- Timestamp
- Source IP
- Source port
- Destination IP
- Destination port

The remaining output includes additional TCP details such as flags and sequence number. The `-v` option provides extra packet information.

### Key Takeaways

- `tcpdump` is an important command-line packet analysis tool.
- You need elevated privileges to capture traffic.
- Capturing, filtering, and interpreting packets on the command line is an important security skill.

---

## Terms and Definitions — Course 6, Module 2

| Term | Definition |
|---|---|
| Command and control (C2) | The techniques used by malicious actors to maintain communications with compromised systems |
| Command-line interface (CLI) | A text-based user interface that uses commands to interact with the computer |
| Data exfiltration | Unauthorized transmission of data from a system |
| Data packet | A basic unit of information that travels from one device to another within a network |
| Indicators of compromise (IoC) | Observable evidence that suggests signs of a potential security incident |
| Internet Protocol (IP) | A set of standards used for routing and addressing data packets as they travel between devices on a network |
| Intrusion detection systems (IDS) | An application that monitors system activity and alerts on possible intrusions |
| Media Access Control (MAC) Address | A unique alphanumeric identifier that is assigned to each physical device on a network |
| National Institute of Standards and Technology (NIST) Incident Response Lifecycle | A framework for incident response consisting of four phases: Preparation; Detection and Analysis; Containment, Eradication and Recovery; and Post-incident activity |
| Network data | The data that’s transmitted between devices on a network |
| Network protocol analyzer (packet sniffer) | A tool designed to capture and analyze data traffic within a network |
| Network traffic | The amount of data that moves across a network |
| Network Interface Card (NIC) | Hardware that connects computers to a network |
| Packet capture (p-cap) | A file containing data packets intercepted from an interface or network |
| Packet sniffing | The practice of capturing and inspecting data packets across a network |
| Playbook | A manual that provides details about any operational action |
| Root user (or superuser) | A user with elevated privileges to modify the system |
| Sudo | A command that temporarily grants elevated permissions to specific users |
| tcpdump | A command-line network protocol analyzer |
| Wireshark | An open-source network protocol analyzer |
