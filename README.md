# Enterprise Network Topology

This document outlines a comprehensive enterprise network topology, designed to provide a secure, scalable, and resilient infrastructure for a modern organization. The topology incorporates various zones and layers to segment traffic, enforce security policies, and optimize performance.

## Architecture Overview

The network is logically divided into several key zones, each serving a specific purpose and protected by appropriate security controls. The primary zones include:

*   **Internet/WAN Edge**: The demarcation point between the internal network and external networks (Internet, WAN).
*   **DMZ (Demilitarized Zone)**: A buffer zone for publicly accessible services, isolated from both the Internet and the internal network.
*   **Internal Network**: The core of the enterprise network, further segmented into core, distribution, and access layers.
*   **Server Farm**: A dedicated zone for critical application and database servers.
*   **Management Network**: A separate, secure network for managing network devices and servers.
*   **Wireless Network**: Provides secure wireless connectivity for internal users.
*   **VPN/Remote Access**: Enables secure remote access for users outside the corporate network.

## Network Zones and Components

### Internet/WAN Edge

This zone represents the entry and exit point for all external traffic. It is critical for establishing a secure perimeter.

*   **Internet**: The external network.
*   **Router/Firewall Edge**: The primary device at the network edge, responsible for routing external traffic and providing initial firewall protection.
*   **External Firewall**: A robust firewall that enforces security policies between the Internet/WAN Edge and the DMZ/Internal Network, performing deep packet inspection and intrusion prevention.

### DMZ (Demilitarized Zone)

The DMZ hosts services that need to be accessible from the Internet but should not have direct access to the internal network. This isolation minimizes the risk of external attacks compromising internal resources.

*   **Web Server**: Hosts public-facing websites and web applications.
*   **DNS Server**: Provides public DNS resolution for external services.
*   **Mail Server**: Handles incoming and outgoing email traffic.

### Internal Network

The internal network is structured in a hierarchical three-tier model (core, distribution, access) to ensure scalability, redundancy, and efficient traffic flow.

#### Core/Distribution Layer

*   **Internal Firewall**: Separates the DMZ and the Internet/WAN Edge from the internal network, enforcing granular security policies.
*   **Core Switch**: The backbone of the internal network, providing high-speed switching and routing between distribution switches and other network segments.
*   **Distribution Switch 1 & 2**: Aggregate traffic from access layer switches and provide policy-based connectivity to the core. They also handle routing between VLANs.

#### Access Layer

*   **Access Switch A & B**: Connect end-user devices to the network. They typically implement port security, VLAN assignments, and Quality of Service (QoS).
*   **End User Devices**: Workstations, laptops, and other devices used by employees.

### Server Farm

This zone houses critical enterprise servers, requiring strong security and high availability.

*   **Server Farm Firewall**: A dedicated firewall protecting the server farm from the rest of the internal network, enforcing strict access controls.
*   **Application Server**: Hosts business-critical applications.
*   **Database Server**: Stores and manages organizational data.
*   **Storage Server**: Provides centralized storage for data and backups.

### Management Network

Isolated from the production network, the management network provides a secure channel for administrators to manage network devices and servers, reducing the risk of unauthorized access.

*   **Management Switch**: Connects management devices and servers.
*   **Monitoring Server**: Collects performance data and alerts from network devices and servers.
*   **Log Server**: Centralizes log collection for security auditing and troubleshooting.
*   **Backup Server**: Manages and stores backups of critical data and configurations.

### Wireless Network

Provides secure and reliable wireless connectivity for authorized users.

*   **Wireless Controller**: Manages and configures wireless access points, enforcing security policies and optimizing wireless performance.
*   **Access Point 1 & 2**: Provide wireless coverage in different areas of the organization.
*   **Wireless Clients**: Laptops, smartphones, and other devices connecting wirelessly.

### VPN/Remote Access

Enables secure connectivity for remote users and branch offices over public networks.

*   **VPN Concentrator**: Terminates VPN tunnels from remote clients, encrypting and decrypting traffic to ensure secure communication.
*   **Remote Users**: Individuals accessing the corporate network from outside the office.
