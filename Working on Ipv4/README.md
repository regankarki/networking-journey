# Working With IPv4 Addresses — CCNA Lab

## Overview
This lab demonstrates how to configure IPv4 addressing on a router and end devices, verify interface status, and test connectivity between three different networks using Cisco Packet Tracer.

## Topology Summary
The network consists of:
- **Router R1** with three interfaces:
  - G0/0 → 15.255.255.254/8
  - G0/1 → 182.98.255.254/16
  - G0/2 → 201.191.20.254/24
- **Three switches** (SW1, SW2, SW3)
- **Three PCs**:
  - PC1 → 15.0.0.1
  - PC2 → 182.98.0.1
  - PC3 → 201.191.20.1

Each PC is connected to its own switch, and each switch connects to R1.

## Objectives
1. Configure R1’s hostname  
2. View R1’s interfaces using `show ip interface brief`  
3. Assign IP addresses and enable interfaces  
4. Add interface descriptions  
5. Verify configuration using `show` commands  
6. Configure IP addresses on PC1, PC2, and PC3  
7. Test connectivity using ping  

## Procedure

### 1. Configure hostname
R1(config)# hostname R1

### 2. Verify interfaces
R1# show ip interface brief

### 3. Configure router interfaces
R1(config)# interface g0/0
R1(config-if)# ip address 15.255.255.254 255.0.0.0
R1(config-if)# no shutdown
R1(config-if)# description Link to SW1

(Repeat for G0/1 and G0/2 with their respective IPs)

### 4. Verify configuration
R1# show running-config
R1# show ip interface brief

Code

### 5. Configure PC IP addresses
Example for PC1:
- IP: 15.0.0.1  
- Mask: 255.0.0.0  
- Gateway: 15.255.255.254  

(Repeat for PC2 and PC3)

### 6. Test connectivity
Successful pings:
- PC1 → PC2  
- PC1 → PC3  
- PC2 → PC3  

## Files Included
- `ipv4-lab.pkt` — Packet Tracer project  
- `configs/` — Router and PC configuration files  
- `screenshots/` — Topology, interface outputs, ping results  

## Results
All devices successfully communicated across different networks, confirming correct 
