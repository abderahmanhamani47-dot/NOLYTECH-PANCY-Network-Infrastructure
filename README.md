# NOLYTECH PANCY – Network Infrastructure Design & Simulation
1. Project Overview

This project focuses on the end-to-end design and simulation of a computer network infrastructure based on a client requirements specification.

The objective was to design a reliable, maintainable and cost-conscious network infrastructure for an institution planning to deploy two computer rooms, each containing 10 workstations.

Rather than simply connecting network devices, the project involved analysing the client's needs, translating functional requirements into technical specifications, designing the network architecture, configuring the infrastructure and validating its main services through practical tests.

The proposed infrastructure was implemented and tested using Cisco Packet Tracer.

2. Client Context & Requirements

The fictional client, NOLYTECH PANCY, requested a network infrastructure meeting the following requirements:

Requirement

Expected functionality

Workstations

20 fixed PCs distributed across two rooms

Internet access

External network connectivity for workstations

Automatic configuration

DHCP-based IP address assignment

Room communication

Communication between both computer rooms

Intranet availability

Internal server accessible from both rooms

Internet independence

Intranet access must remain possible if Internet connectivity fails

Performance

5 Mbps per workstation and at least 100 Mbps access to the intranet server

Maintainability

Simple administration and troubleshooting

Budget

Cost-conscious equipment selection

The requirements specification also included physical installation constraints, equipment capacity limitations and a defined maintenance and deployment framework.

3. Engineering Approach

The project followed four main engineering phases:

Phase 1 – Requirements Analysis

Analyse the client's functional and technical requirements.

Identify infrastructure constraints and expected network services.

Determine the network segmentation and connectivity requirements.

Identify performance, availability and maintainability objectives.

Phase 2 – Network Architecture Design

Design the logical and physical network architecture.

Select an appropriate hierarchical network topology.

Define VLAN segmentation.

Establish the IPv4 addressing and subnetting plan.

Identify the roles of switching, routing and server equipment.

Phase 3 – Implementation & Configuration

Build the infrastructure in Cisco Packet Tracer.

Configure access switches and the multilayer core switch.

Implement VLANs and IEEE 802.1Q trunk links.

Configure inter-VLAN routing.

Deploy DHCP services.

Configure static routing and NAT/PAT.

Configure the internal intranet server and external test server.

Phase 4 – Testing & Validation

Verify automatic IP address allocation.

Test communication between VLANs.

Verify access to the intranet server.

Test connectivity to the external simulated network.

Inspect NAT translations.

Validate HTTP services through workstation web browsers.

4. Network Architecture

The simulated infrastructure is composed of the following elements:

Device

Role

SW-SALLE1

Access switch for Room 1

SW-SALLE2

Access switch for Room 2

SW-CORE

Multilayer switch providing VLAN segmentation and inter-VLAN routing

R-NOLYTECH

Edge router connecting the internal network to the external network

R-ISP

Router simulating the Internet service provider

Intranet Server

Internal HTTP server

External Server

External HTTP server used to simulate an Internet destination

20 Workstations

Client devices distributed across both rooms

Logical Network Segmentation

Three VLANs were implemented:

VLAN ID

Name

Network

Default Gateway

10

SALLE1

192.168.10.0/28

192.168.10.1

20

SALLE2

192.168.20.0/28

192.168.20.1

30

SERVEURS

192.168.30.0/28

192.168.30.1

The internal intranet server uses a static IP address:

192.168.30.2/28

Network Topology

<!-- Add the network topology image here -->

02-Network-Architecture/diagrams/network-topology.png

5. Technologies & Protocols

The project involved the following technologies and networking concepts:

Technology

Purpose

Cisco Packet Tracer

Network simulation

VLAN

Logical network segmentation

IEEE 802.1Q

VLAN trunking

DHCP

Automatic IP configuration

IPv4 / CIDR

IP addressing and subnetting

Inter-VLAN Routing

Communication between VLANs

Static Routing

Routing between internal and external networks

NAT/PAT

Translation of private IP addresses

ICMP

Connectivity verification

HTTP

Intranet and external web services

6. Implementation Details

6.1 VLAN Configuration

Three logical networks were created to separate the two computer rooms and the server infrastructure.

VLAN 10: Room 1 workstations.

VLAN 20: Room 2 workstations.

VLAN 30: Internal servers.

Access ports were assigned to their corresponding VLANs, while trunk links were configured between access switches and the multilayer core switch.

6.2 Inter-VLAN Routing

The Cisco multilayer switch was configured to perform Layer 3 routing between the different VLANs.

Switched Virtual Interfaces (SVIs) were configured as default gateways:

VLAN 10: 192.168.10.1

VLAN 20: 192.168.20.1

VLAN 30: 192.168.30.1

IP routing was enabled on the core switch.

6.3 DHCP Configuration

DHCP pools were configured on the core switch to automatically assign IP addresses to workstations in both computer rooms.

Each DHCP pool provides the appropriate network configuration, including:

IP address.

Subnet mask.

Default gateway.

6.4 Routing & NAT/PAT

Static routing was implemented between the core switch and the edge router.

NAT overload (PAT) was configured on the edge router to allow multiple internal workstations to share the external interface address when accessing the simulated external network.

6.5 Intranet Server

An internal server was configured with a static IPv4 address in VLAN 30.

The HTTP service was enabled to provide access to the intranet from both computer rooms.

Because the intranet server is hosted inside the local infrastructure, its access does not depend on the simulated external Internet connection.

7. Testing & Validation

The following functional tests were performed during the simulation:

Test

Expected result

Status

DHCP – Room 1

Automatic IP assignment

Passed

DHCP – Room 2

Automatic IP assignment

Passed

Inter-VLAN connectivity

Communication between both rooms

Passed

Intranet connectivity

Access to internal server

Passed

External connectivity

Access to simulated external server

Passed

NAT/PAT verification

Internal addresses translated to external interface address

Passed

HTTP intranet access

Intranet webpage accessible

Passed

HTTP external access

External test webpage accessible

Passed

Validation Evidence

<!-- Add your real screenshots in this section -->

Screenshots and test evidence will be organised in:

05-Testing-and-Validation/screenshots/

8. Performance & Design Considerations

The original requirements specify:

5 Mbps per workstation.

At least 100 Mbps access to the intranet server.

These requirements must be assessed against the selected equipment capabilities and the available link bandwidth.

The Packet Tracer simulation validates functional connectivity and service behaviour. It does not, by itself, demonstrate measured throughput or prove compliance with the contractual bandwidth requirements.

A separate bandwidth assessment and equipment compatibility analysis are therefore required.

9. Equipment Selection & Budget

The original case study provides a restricted equipment catalogue from three suppliers:

Baukia

Ciscolombo

Gilson Networks

The final equipment selection and financial assessment will be documented separately, using the catalogue specifications, equipment prices, installation constraints and technician costs.

Important: The Cisco devices used in Packet Tracer represent the simulated network implementation. They should not be confused with the equipment proposed in the final catalogue-based solution.

10. Security, Maintainability & Future Improvements

The current simulation provides basic network separation through VLANs and address translation through NAT/PAT.

Further improvements could include:

Access Control Lists (ACLs) to restrict unnecessary inter-VLAN traffic.

Firewall deployment and security policy enforcement.

Secure device administration using SSH.

Port security on access switches.

Network monitoring and centralised logging.

Redundant network links and equipment.

Configuration backups and documented recovery procedures.

Performance monitoring and bandwidth measurements.

These improvements would strengthen the security, availability and maintainability of the proposed infrastructure.

11. Repository Structure

NOLYTECH-PANCY-Network-Infrastructure/
│
├── 01-Project-Overview/
├── 02-Network-Architecture/
├── 03-Cisco-Packet-Tracer/
├── 04-Implementation/
├── 05-Testing-and-Validation/
├── 06-Budget-and-Equipment/
├── 07-Documentation/
└── README.md

12. Key Learning Outcomes

This project provided practical experience in:

Translating client requirements into a technical network solution.

Designing logical and physical network architectures.

Understanding VLAN segmentation and Layer 2 switching.

Configuring Layer 3 routing and DHCP services.

Implementing NAT/PAT for external connectivity.

Deploying and testing internal network services.

Troubleshooting connectivity issues.

Documenting technical decisions and validation results.

It also strengthened my understanding of the relationship between network design choices, infrastructure constraints, service availability and maintainability.

13. Project Information

Author: Abderrahmane Hamani
Institution: Polytech Nancy – Université de Lorraine
Academic field: Computer Science, Automation, Robotics and Networks
Project type: Academic Engineering Case Study
Simulation tool: Cisco Packet Tracer

This project is an academic network engineering case study. The infrastructure was designed and validated in a Cisco Packet Tracer simulation. It does not represent a physical production deployment.**Field:** Computer Science, Networks and Cybersecurity
