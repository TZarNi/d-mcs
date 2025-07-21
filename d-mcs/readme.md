### Background

$\small{\textsf{There are some remote and ad-hoc sites where access-network over wireless.}}$
$\small{\textsf{It is better to have a real-time qucik check solution when I have a call that some wlan clients connectivity problem.}}$

### Overview

$\small{\textsf{This project demonstrates how to use a custom Ansible module written in Python to extract real-time wireless client information from a Cisco 1702i Autonomous AP.}}$
$\small{\textsf{It showcases automation of SSH access, parsing of CLI output, and intelligent mapping of 802.11 MCS index, signal strength, and}}$
$\small{\textsf{SNR into human-readable data rates and modulation types.}}$

### Features

$\small{\textsf{1. SSH login to Cisco AP directly via Ansible module:}}$<br>

$\small{\textsf{2. Collects connected clients' info:}}$
+ $\small{\textsf{MAC address}}$
+ $\small{\textsf{IP address}}$
+ $\small{\textsf{MCS Index}}$
+ $\small{\textsf{Signal Strength (dBm)}}$
+ $\small{\textsf{SNR (dB)}}$<br>

$\small{\textsf{3. Smart mapping of MCS Index + Spatial Stream to:}}$
+ $\small{\textsf{Data Rate (Mbps)}}$
+ $\small{\textsf{Modulation Type (BPSK/QPSK/16-QAM/64-QAM)}}$
+ $\small{\textsf{Code Rate (1/2, 3/4, etc.)}}$<br>

$\small{\textsf{4. Outputs a clean and aligned table via Ansible debug}}$

### Sample Output

<img width="959" height="319" alt="image" src="https://github.com/user-attachments/assets/de8c7e54-dbce-49a5-83a4-469aff32c4ae" />

### Project Structure
```yaml
.
├── inventory
│   └── ap_vars.yaml
├── library
│   └── mcs-check.py
└── mcs-check.yaml
```
### Usage

$\small{\textsf{Clone this repo}}$
$\small{\textsf{Create your inventory with the AP IP.}}$
$\small{\textsf{Update credentials in the playbook}}$
$\small{\textsf{Run the playbook:}}$
```yaml
ansible-playbook -i inventory/ap-vars.yaml mcs-check.yaml
```
### Requirements

+ $\small{\textsf{Python 3.x}}$
+ $\small{\textsf{Ansible 2.9+}}$
+ $\small{\textsf{Cisco 1702i AP in autonomous mode}}$
+ $\small{\textsf{paramiko library (install via pip install paramiko)}}$

### Example Use Case

$\small{\textsf{Ideal for:}}$
+ $\small{\textsf{Wireless performance monitoring}}$
+ $\small{\textsf{Auto-polling WiFi stats in educational or enterprise environments}}$
+ $\small{\textsf{Lightweight telemetry collection from standalone Cisco APs}}$
+ $\small{\textsf{Demonstrating advanced Ansible module authoring in network automation}}$

### Reference
```yaml
https://mcsindex.com/
https://www.accessagility.com/blog/how-to-improve-mcs-index
```
