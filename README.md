# Cisco IP Telephony Network

## Overview

This project presents the design and implementation of a **multi-department enterprise network with IP telephony** using Cisco Packet Tracer.

The network connects four departments — **Administration, HR, Finance, and Sales** — through dedicated departmental LANs. It integrates **VLAN-based network segmentation, dynamic routing, DHCP, and IP telephony** to provide reliable communication and efficient network management.

The project also demonstrates the use of **Voice and Data VLANs** to logically separate IP phone traffic from regular computer traffic.

---

## Network Design

The network consists of four departments:

- **Administration** – 6 laptops, 4 IP phones, and 1 printer
- **HR** – 5 laptops, 6 IP phones, and 1 printer
- **Finance** – 7 laptops, 3 IP phones, and 1 printer
- **Sales** – 4 laptops, 6 IP phones, and 1 printer

Each department is connected to a dedicated **Cisco 2811 router**, providing connectivity between the departmental LAN and the rest of the enterprise network.

### Routers

- `R1_Admin`
- `R2_HR`
- `R3_Finance`
- `R4_Sales`

---

## Key Technologies

- **Cisco Packet Tracer**
- **Cisco 2811 Routers**
- **VLAN**
- **DHCP**
- **OSPF**
- **IP Telephony / VoIP**
- **Cisco CME (CallManager Express)**
- **Voice VLANs**
- **Data VLANs**
- **Serial WAN Links**

---

## Network Architecture

The four Cisco 2811 routers are interconnected using a **ring topology**, providing multiple paths between departments and improving network resilience.

Each router connects its respective departmental LAN to the enterprise network. Within each department, devices are organized using separate **Data and Voice VLANs**.

### Router Topology


                 R1_Admin
                /        \
               /          \
          R2_HR          R3_Finance
               \          /
                \        /
                 R4_Sales
Each router is connected to its respective departmental switch and end devices.

The network uses **serial links** between routers for inter-router communication. **WIC-2T modules** are used with the Cisco 2811 routers to provide the required serial interfaces.

---

## IP Addressing

The departmental data networks are organized using separate private IPv4 subnets:

| Department | Data Network |
|------------|--------------|
| Administration | `192.168.10.0/24` |
| HR | `192.168.20.0/24` |
| Finance | `192.168.30.0/24` |
| Sales | `192.168.40.0/24` |

Separate IP address ranges are used for the **Voice VLANs** to maintain voice and data segmentation.

---

## IP Telephony

Each department contains dedicated **IP phones** for internal voice communication.

The project uses **Cisco CME (CallManager Express)** to provide IP telephony services and manage the IP phones.

IP phones are assigned to dedicated **Voice VLANs**, while laptops and other data devices use **Data VLANs**.

This separation allows voice and regular network traffic to share the same physical infrastructure while remaining logically isolated.

The IP phones also provide an Ethernet pass-through connection for laptops, allowing a laptop and IP phone to share a switch port while maintaining separate voice and data traffic through VLAN configuration.

---

## Project Goals

The main goal of this project is to demonstrate the design of a **scalable and reliable enterprise network** that supports both data communication and IP telephony.

The project combines **routing, switching, VLAN segmentation, DHCP, OSPF, and VoIP** to simulate a practical enterprise networking environment using Cisco technologies.
