---
title: Networking Lab Guide
parent: Writing
nav_order: 4
---

# 🧪 Networking Lab: Set Up and Monitor a Local Network

This guide walks you through setting up a basic home or virtual lab to learn and test fundamental networking tools and concepts — no expensive hardware required.

You’ll:
- Create a mini LAN environment (physical or virtual)
- Set up a DHCP server and client
- Use tools like `ping`, `traceroute`, and `Wireshark`
- Capture and analyze network traffic

## 🧱 Requirements

- A computer running Windows, Linux, or macOS
- Optional: Virtualization tool like [VirtualBox](https://www.virtualbox.org/) or [VMware Workstation Player](https://www.vmware.com/products/workstation-player.html)
- A second virtual machine (or physical device) for testing
- Tools:
  - `ping`, `traceroute` (built-in)
  - [`Wireshark`](https://www.wireshark.org/download.html)
  - [`dnsmasq`](https://thekelleys.org.uk/dnsmasq/doc.html) (for DHCP/DNS, Linux/macOS)

## 🔧 Step 1: Set Up the Test Network

### Option A: Physical Devices
- Connect two machines to the same LAN or via Ethernet cable.
- Assign one a static IP; the other will request one via DHCP.

### Option B: Virtual Machines
- Create two VMs in VirtualBox.
- Use **Internal Network** or **Host-Only Adapter** mode.
- Disable NAT to isolate the environment.

## ⚙️ Step 2: Configure DHCP (on Linux/macOS)

Install `dnsmasq`:

```bash
sudo apt install dnsmasq   # Debian/Ubuntu
brew install dnsmasq       # macOS (Homebrew)
```
 Edit `/etc/dnsmasq.conf` (or create one in a custom directory):

```ini
interface=eth0
dhcp-range=192.168.50.10,192168.50.100,12h
```

Restart the service:

 ```bash
 sudo systemctl restart dnsmasq
 ```

 ## 📡 Step 3: Run Diagnostics
### 🔁 Ping Test
```bash
ping 192.168.50.1
```
 Check for successful replies.

 ### 🧭 Traceroute
 ```bash
traceroute 8.8.8.8      # Linux/macOS
tracert 8.8.8.8         # Windows
```

See how many hops and what IPs are involved.

## 🔍 Step 4: Capture with Wireshark
### Start Wireshark
1. Open Wireshark.
2. Select the interface (e.g., `eth0`,`vboxnet0`,`en0`).
3. Apply a capture filter:

    ```ini
    ip.addr == 192.168.50.10
    ```
### Things to Try:
- **Start a ping** and watch ICMP packets
- **Run a DNS query**:

    ```bash
    nslookup google.com
    ```
- **Download a file** and observe the TCP handshake (SYN, SYN-ACK, ACK)

## 🛠️ Optional Tools to Explore
- `netstat` or `ss` — show open ports and active connections
- `nmap` — scan your mini-network
- `iftop` — real-time traffic monitor (Linux)
- `ipconfig` / `ifconfig` / `ip a` — inspect interface IPs

## 📚 Summary
You’ve now:

- Created a basic two-host network
- Set up a functioning DHCP server
- Used `ping`, `traceroute`, and `Wireshark` to inspect traffic
- Captured real packets and examined networking layers

## 🙋 Why This Matters
This lab replicates what many IT, sysadmin, and network engineering roles involve:

- Diagnosing connection issues
- Monitoring traffic
- Verifying IP addressing and routing

It also lays the foundation for more advanced skills like firewall debugging, subnetting, or VLAN segmentation.

## 🔗 Resources
- Wireshark Labs (by Protocol Analysis Institute)
- Nmap Guide
- Linux iproute2 Cheatsheet