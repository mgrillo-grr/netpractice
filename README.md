*This project has been created as part of the 42 curriculum by mgrillo.*

# NetPractice

## Description

NetPractice is a networking fundamentals project from 42 School. The goal is to solve 10 levels of progressively complex, non-functioning network diagrams. By modifying the TCP/IP configuration of devices (IP addresses, subnet masks, and default gateways), the student must make the entire network operational.

This project provides a practical, hands-on introduction to how data travels through switches and routers. It reinforces core concepts of IPv4 addressing, routing tables, and the role of a gateway without requiring any physical hardware.


The project provides hands-on experience with fundamental networking concepts, including:

- **IPv4 Addressing & Subnet Masks**
-- Binary and decimal conversion
-- CIDR notation (/24, /16, etc.)
-- Network ID, broadcast address, and host range

- **Subnetting & Network Segmentation**
-- Dividing large networks into smaller subnets
-- Optimizing IP allocation
-- Reducing broadcast domains

- **Static Routing & Default Gateways**
-- Role of the gateway as a network exit point
-- Configuring static routes between routers
-- Understanding routing tables

- **Network Device Roles**
-- Hosts: sources and destinations of traffic
-- Switches: Layer 2 forwarding (MAC addresses)
-- Routers: Layer 3 forwarding (IP addresses)

- **Public vs Private IP Ranges**
-- RFC 1918: 10.0.0.0/8, 172.16.0.0/12, 192.168.0.0/16
-- Why private addresses cannot route over the internet

- **Conflict & Overlap Prevention**
-- Duplicate IP addresses on the same network
-- Overlapping subnet ranges
-- Misconfigured or unreachable gateways



The goal is not just to complete the 10 levels,
-- but to understand why a configuration works
-- and why another fails.

Each level builds intuition for real-world networking,
-- from small home networks to multi-router infrastructures.

## Instructions

### How to Run the Training Interface

1. Download the project files from the 42 intranet
2. Extract the files to your preferred directory
3. Make the script executable (if necessary): (chmod +x run.sh)
4. Run the interface: (./run.sh)
-- This script launches a local Python HTTP server and automatically opens the NetPractice page in your default web browser.
- **Manual start (if run.sh fails):**
-- python3 -m http.server 49242
-- Then navigate to http://localhost:49242 in your browser.
5. Practice mode – enter your login in the practice tab
6. Evaluation mode – generate a random configuration for peer review

### How to Use !!!

- Enter your intra login in the provided field. This ensures your name is embedded in the configuration files.
- Complete the 10 levels by clicking on the white input fields and adjusting the IP addresses, subnet masks, and gateways.
- Click "Check again" to test your configuration.
- If the configuration is correct, a button to proceed to the next level will appear.
- Export your configuration: Before moving to the next level, click "Get my config" to download the .json file for that level.

### Submission Requirements

- **10 configuration files** (one per level) must be submitted at the repository root
- Files should be named according to the level (e.g., `level1.json`, `level2.json`, etc.)
- All files must be exported using the "Get my config" button from the training interface

### Evaluation

- **Peer evaluation**
-- complete 3 random levels within a time limit

- **External tools**
-- not allowed

- **Permitted** 
-- simple calculator (bc)

## Resources

### Networking Concepts Studied

This project required understanding the following core networking concepts:

#### TCP/IP Addressing
- **IP Address structure**: Four octets, network vs host portions
- **CIDR notation**: Slash notation (/24, /25, /30, etc.) to represent subnet masks
- **Network classes**: Class A, B, and C addressing (historical — modern networks use CIDR)

#### Subnet Mask
- **Purpose**: Separates the network and host portions of an IP address
- **Binary representation**: How masks operate at the bit level
- **Common masks**: /24 (255.255.255.0), /25 (255.255.255.128), /26 (255.255.255.192), /30 (255.255.255.252)
- **Subnet calculation**: Determining valid IP ranges, network ID, and broadcast address

#### Subnetting
- **Network segmentation**: Dividing a larger network into smaller subnetworks
- **Avoiding overlap**: Ensuring different subnets do not share IP address space
- **Host calculation**: Usable IPs = 2^(32 - CIDR) - 2
- **Practical application**: Organizing network architecture efficiently

#### Default Gateway
- **Definition**: The router interface that serves as the exit point from a local network
- **Configuration**: Must be an IP address in the same subnet as the host
- **Routing role**: Forwards packets destined for networks outside the local subnet

#### Routers
- **Function**: Connect different networks and route packets between them (Layer 3)
- **Interfaces**: Each router interface must be on a different subnet
- **Routing tables**: Manually configured static routes
- **Multi-hop routing**: Packets may traverse multiple routers to reach their destination

#### Switches
- **Layer 2 operation**: Operate at the data link layer (MAC addresses)
- **Single network**: All devices connected to a switch must share the same subnet
- **No routing**: Switches do not route between different networks

#### Static Routes
- **Purpose**: Manually configured paths to specific networks
- **Components**: Destination network + next-hop gateway IP
- **Default route (0.0.0.0/0)**: Catch-all for any destination not explicitly defined
- **Route specificity**: More specific routes take precedence over general ones

#### Special IP Ranges
- **Loopback (127.0.0.0/8)**: Reserved for internal device communication
- **Private ranges**: 10.0.0.0/8, 172.16.0.0/12, 192.168.0.0/16 (require NAT for Internet access)
- **Public IPs**: Routable on the Internet
- **Network address**: First IP in a subnet (all host bits = 0)
- **Broadcast address**: Last IP in a subnet (all host bits = 1)

#### Avoiding IP Conflicts and Network Overlap
- **Duplicate IPs**: Two devices cannot share the same IP within a subnet
- **Overlapping subnets**: Different interfaces must not share address space
- **Gateway misconfiguration**: Gateway must be reachable and correctly assigned


## Level-by-Level Breakdown

### Network Mask Quick Reference

Subnetting cheat sheet for common CIDR masks:

| CIDR | Subnet Mask       | Hosts/Subnet | Subnets in /24 |
|------|-------------------|--------------|----------------|
| /30  | 255.255.255.252   | 2            | 64             |
| /29  | 255.255.255.248   | 6            | 32             |
| /28  | 255.255.255.240   | 14           | 16             |
| /27  | 255.255.255.224   | 30           | 8              |
| /26  | 255.255.255.192   | 62           | 4              |
| /25  | 255.255.255.128   | 126          | 2              |
| /24  | 255.255.255.0     | 254          | 1              |


<img width="1901" height="1977" alt="image" src="https://github.com/user-attachments/assets/3e8a24c3-03a9-417b-8ae6-9664aa4ce41a" />



<img width="1901" height="1977" alt="image" src="https://github.com/user-attachments/assets/d019999a-d848-4481-9f36-2df477d15f49" />



<img width="1901" height="1977" alt="image" src="https://github.com/user-attachments/assets/50b68e2e-8d12-4b70-9c43-659420195b05" />




<img width="1901" height="1977" alt="image" src="https://github.com/user-attachments/assets/90e4c535-1b09-4dcf-ad32-1faaaab66cd1" />




<img width="1901" height="1977" alt="image" src="https://github.com/user-attachments/assets/c03e28a2-b8af-4790-a891-85a3f6e2568b" />



<img width="1901" height="1977" alt="image" src="https://github.com/user-attachments/assets/242283bc-b6ee-4dff-a677-4d90e9498f5a" />



<img width="2112" height="1989" alt="image" src="https://github.com/user-attachments/assets/ebd3750c-0558-49ab-917c-da611bc3ecee" />



<img width="2112" height="1989" alt="image" src="https://github.com/user-attachments/assets/4e7b7da9-3761-40ce-8518-bd7caf08ed19" />



<img width="2112" height="1989" alt="image" src="https://github.com/user-attachments/assets/d57cd285-9b41-4392-be5e-cc40026efa49" />



<img width="2112" height="1989" alt="image" src="https://github.com/user-attachments/assets/da154d04-4000-4428-ab46-6a8d23ffcb8d" />
