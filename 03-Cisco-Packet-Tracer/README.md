# Cisco Packet Tracer Simulation

This directory contains the Cisco Packet Tracer simulation of the NOLYTECH PANCY network infrastructure.

## Simulation Overview

The simulated network includes:

- Two Cisco 2960 access switches.
- One Cisco 3560 multilayer core switch.
- One Cisco 2911 edge router.
- One Cisco 2911 ISP router.
- 20 client workstations.
- One internal intranet server.
- One external server simulating an Internet destination.

## Implemented Features

- VLAN segmentation (VLAN 10, 20 and 30).
- IEEE 802.1Q trunk links.
- Inter-VLAN routing.
- DHCP configuration.
- Static routing.
- NAT/PAT configuration.
- Internal HTTP server.
- External connectivity simulation.

## How to Open the Simulation

1. Download `NOLYTECH-PANCY-Network.pkt`.
2. Open Cisco Packet Tracer.
3. Select File → Open.
4. Select the downloaded `.pkt` file.
5. Explore the topology and device configurations.

## Important Note

This is an academic network simulation. The external server represents a simulated Internet destination, not a real Internet connection.

The simulation validates functional network behaviour but does not constitute a physical deployment or measured SLA performance assessment.
