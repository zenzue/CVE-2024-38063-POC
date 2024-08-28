# IPv6 Vulnerability Packet Sender for Memory Corruption
## CVE-2024-38063
This Python script is designed to send crafted packets to trigger potential memory corruption vulnerabilities `CVE-2024-38063`. It utilizes the Scapy library to create and send IPv6 packets, optionally using specified MAC addresses. The script can handle multiple network interfaces.

## Features

- Send crafted IPv6 packets with optional Interface headers.
- Configure destination IP and optionally MAC address.
- Specify the number of tries and batches for packet sending.
- Supports multiple network interfaces for packet dispatch.

## Requirements

- Python 3.x
- Scapy: You can install Scapy using pip:
  ```bash
  pip install scapy
  ```

## Usage

To use this script, you will need to provide several command-line arguments. Here is how to run the script with the required options:

```bash
python cve-2024-38063.py --iface "eth0,eth1" --ip_addr "2001:db8::1" --mac_addr "00:1A:2B:3C:4D:5E" --num_tries 20 --num_batches 20
```

### Arguments

- `--iface`: A comma-separated list of interfaces to use for sending packets. This argument is required.
- `--ip_addr`: The destination IPv6 address to which the packets will be sent. This argument is required.
- `--mac_addr`: The destination MAC address. This is optional; if omitted, no Ethernet header will be added.
- `--num_tries`: The number of tries per batch. Defaults to 20.
- `--num_batches`: The number of batches of tries. Defaults to 20.

### Example

Here is an example command that uses two interfaces to send packets:

```bash
python packet_sender.py --iface "eth0,eth1" --ip_addr "2001:db8::1" --mac_addr "00:1A:2B:3C:4D:5E" --num_tries 30 --num_batches 10
```

This will send packets to the specified IP address with the specified MAC address over `eth0` and `eth1`, with 30 tries per batch and 10 batches in total.

## Author

- Aung Myat Thu aka `w01f`

## Acknowledgments

- Thanks to the Scapy development team for providing such a powerful tool.
- Thanks to `ynwarcs` for idea
