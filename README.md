
---

# Network Packet Sniffer

This Python script uses the Scapy library to capture and analyze network packets. It listens for IP packets on a network interface and displays information about the source and destination IP addresses, the protocol used (TCP, UDP, ICMP), and any payload data that might be present.


## Introduction

Packet sniffers are essential tools in network security and analysis. This script provides a simple implementation of a network packet sniffer using Python and Scapy. The script captures IP packets and provides detailed information about them, including the protocol and payload (if available). It is useful for monitoring network traffic, debugging network issues, and learning about network protocols.

## Features

- **Capture IP Packets:** Listens for IP packets on a specified network interface.
- **Protocol Detection:** Identifies whether the packet is using TCP, UDP, ICMP, or another protocol.
- **Payload Extraction:** Extracts and displays payload data for TCP and UDP packets.
- **Real-Time Monitoring:** Displays packet information in real-time as they are captured.

## Prerequisites

To run this script, you'll need:

- Python 3.x installed on your machine.
- The `scapy` library, which can be installed using pip.

## Installation

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/your-username/network-packet-sniffer.git
   ```

2. Navigate to the project directory:

   ```bash
   cd Prodigy-infoTech_cs_intern_05

   ```

3. Install the required `scapy` library:

   ```bash
   pip install scapy
   ```

4. (Optional) If you are running on Linux or macOS, you may need to run the script with elevated privileges to access network interfaces. Use `sudo`:

   ```bash
   sudo python packet_sniffer.py
   ```

## Usage

1. Run the script using Python:

   ```bash
   sudo python packet_sniffer.py
   ```

2. The script will start sniffing the network interface and print out details of each captured packet.

### Example:

```bash
Source IP: 192.168.1.10 -> Destination IP: 192.168.1.1 | Protocol: TCP
Payload: b'GET / HTTP/1.1\r\nHost: example.com\r\n\r\n'

Source IP: 10.0.0.2 -> Destination IP: 8.8.8.8 | Protocol: ICMP
```

### Command-Line Arguments

You can specify the network interface you want to sniff on by modifying the `sniff()` function in the script:

```python
sniff(filter="ip", iface="eth0", prn=packet_callback, store=0)
```

Replace `"eth0"` with the appropriate interface name (e.g., `"wlan0"` for Wi-Fi on Linux).

## Functions Overview

- **packet_callback(packet):**
  - **Description:** This is the callback function that processes each captured packet. It extracts the source and destination IP addresses, determines the protocol, and prints the packet details. If the packet is TCP or UDP, it also prints the payload.
  - **Arguments:**
    - `packet`: The captured packet to be processed.

## File Structure

```bash
.
├── packet_sniffer.py     # Main packet sniffer script
└── README.md             # This README file
```

---

### Notes:
- Replace `"https://github.com/your-username/network-packet-sniffer.git"` with your actual GitHub repository URL.
- You may need elevated privileges to run the script on certain operating systems due to the need for access to network interfaces.
