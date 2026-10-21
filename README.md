# VoIP Telephony with Voice and Data VLANs

A Cisco Packet Tracer networking lab demonstrating an IP phone network with a dedicated voice VLAN and a separate data VLAN for connected PCs. This project is suitable for a networking portfolio and can be extended with DHCP, call control, and security features.

## Project Overview

The topology connects Cisco IP phones to an access switch, with PCs connected through the phones' PC ports. A router provides Layer 3 connectivity. The screenshots document a voice/data VLAN configuration scenario and an IP phone showing a connected call state.

> **Artifact limitation:** The original Cisco Packet Tracer `.pkt` file was not provided. This repository contains the supplied screenshots and documentation only; it does not claim to include a runnable simulation file or a verified configuration.

## Features

- Separate voice and data VLAN design
- Cisco 7960 IP phone topology
- Router-to-switch uplink
- PC connectivity through IP phone PC ports
- Documented topology and verification workflow

## Technologies Used

- Cisco Packet Tracer
- Cisco IOS-style switching and routing concepts
- IEEE 802.1Q VLAN concepts
- IP telephony / VoIP concepts

## Project Structure

```text
voip-voice-data-vlan/
├── README.md
└── screenshots/
    ├── ip-phone-connected.png
    └── voice-data-vlan-topology.png
```

## Network Topology Details

The supplied topology screenshot labels the following networks:

| Network | VLAN | Subnet |
|---|---:|---|
| Voice | 33 | `172.16.10.0/24` |
| Data | 50 | `192.168.10.0/24` |

Devices shown include a Cisco 2811 router, a Cisco Catalyst 2960-series switch, Cisco 7960 IP phones, and PCs. The router connects to the switch; each phone connects to the switch, and a PC can connect to the phone's PC port.

These values are transcribed from the screenshot labels and are not independently verified against a `.pkt` file.

## How to Recreate and Test

1. Open Cisco Packet Tracer and create a new project.
2. Add one Cisco 2811 router, one Catalyst 2960 switch, IP phones, and PCs.
3. Connect the router to the switch using a copper straight-through cable.
4. Connect each IP phone to the switch. Connect each PC to the PC port on its phone.
5. Create VLAN 33 for voice and VLAN 50 for data.
6. Configure the switch ports with the appropriate data VLAN and voice VLAN settings.
7. Configure router addressing and any required DHCP scopes for both subnets.
8. Configure the call-control service supported by your Packet Tracer version if you want to test phone-to-phone calls.
9. Assign addresses to PCs and phones, then test local connectivity and call functionality.

The steps above are a recreation guide, not a claim that the unavailable original configuration has been reproduced exactly.

## Useful Verification Commands

```text
show vlan brief
show interfaces trunk
show running-config
show ip interface brief
show ip dhcp binding
show telephony-service
show ephone registered
```

Command availability depends on the device model and Packet Tracer version.

## Expected Results

- Voice and data VLANs appear in `show vlan brief`.
- The switch uplink carries the required VLANs if configured as a trunk.
- PCs receive addresses from the data subnet if DHCP is configured.
- IP phones receive voice-network addressing and register when DHCP, call control, and device settings are correctly configured.
- A phone-to-phone call can be tested if the required telephony service is configured.

These are expected outcomes for a correctly recreated lab, not results verified from the supplied screenshots.

## Important Notes

- The original `.pkt` file was not supplied.
- Screenshots are included as visual references only.
- IP addressing, DHCP options, call-control configuration, and switch-port commands may need adjustment for your Packet Tracer version.
- Do not describe this project as fully tested until you recreate it and verify the results.
