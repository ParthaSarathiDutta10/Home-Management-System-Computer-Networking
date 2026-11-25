# Smart City Network Infrastructure

A simulated smart-city network designed and implemented in **Cisco
Packet Tracer**. The project demonstrates how a segmented, multi-zone
network can connect users, centralized services, wireless clients, and
IoT devices while applying routing and security controls.

## Project Overview

Modern smart-city environments depend on reliable communication between
departments, users, infrastructure services, and connected devices. This
project models that environment through a structured enterprise-style
network architecture.

The topology is divided into four functional zones:

1.  **Core Network Zone** -- Provides backbone connectivity and routing
    between network segments.
2.  **User Zone** -- Connects end-user devices such as desktop PCs and
    laptops.
3.  **Data Center & Management Zone** -- Groups centralized services and
    network administration resources.
4.  **IoT & Wireless Zone** -- Supports wireless clients, an IoT
    controller, and smart devices such as a smart light.

The design uses logical segmentation and controlled communication to
improve manageability, security, and scalability.

## Project Objectives

-   Design a multi-zone smart-city network topology.
-   Connect different network segments through a routed core.
-   Separate user, IoT, and management traffic using VLANs.
-   Configure dynamic routing with OSPF.
-   Enable communication between VLANs.
-   Apply ACL rules to restrict unauthorized access to protected
    resources.
-   Configure NAT/PAT for communication with an external network.
-   Integrate wireless connectivity and IoT devices.
-   Verify network operation through device and connectivity tests.

## Network Architecture

The network follows a hierarchical, zone-based design. Core networking
devices provide connectivity between zones, while access switches
connect endpoint devices. Centralized services and IoT components are
organized into dedicated segments.

### Main Network Zones

  -----------------------------------------------------------------------
  Zone                                Role
  ----------------------------------- -----------------------------------
  Core Network                        Backbone connectivity, routing, and
                                      inter-zone communication

  User                                Access for PCs, laptops, and other
                                      end-user devices

  Data Center & Management            Centralized network services and
                                      administration

  IoT & Wireless                      Wireless access and smart-device
                                      communication
  -----------------------------------------------------------------------

### Topology

Add an exported image of your Packet Tracer topology to
`docs/images/topology.png` and it will appear here:

![Smart City Network Topology](docs/images/topology.png)

> **Note:** The topology image is a repository asset. Add the image at
> the path above, or update the image path to match your filename.

## Technologies and Concepts

  -----------------------------------------------------------------------
  Technology / Concept                Purpose in the Project
  ----------------------------------- -----------------------------------
  Cisco Packet Tracer                 Network design, configuration, and
                                      simulation

  IPv4 addressing                     Addressing devices and network
                                      segments

  VLSM and subnetting                 Planning address allocation for
                                      network segments

  VLANs                               Logical network segmentation

  IEEE 802.1Q trunking                Carrying VLAN traffic across switch
                                      links

  Inter-VLAN routing                  Enabling communication between
                                      permitted VLANs

  OSPF                                Dynamic route exchange between
                                      routers

  Access Control Lists (ACLs)         Filtering traffic and protecting
                                      restricted resources

  NAT/PAT                             Translating private addresses for
                                      external connectivity

  Wireless networking                 Connecting wireless clients and IoT
                                      devices

  WPA2-PSK                            Wireless network authentication and
                                      protection

  IoT integration                     Connecting and managing simulated
                                      smart devices
  -----------------------------------------------------------------------

## VLAN Design

The project uses VLANs to separate devices by function and reduce
unnecessary exposure between network segments.

  ------------------------------------------------------------------------
                       VLAN ID VLAN Name             Purpose
  ---------------------------- --------------------- ---------------------
                            10 USERS                 User PCs and client
                                                     devices

                            20 IoT                   IoT devices and
                                                     smart-device
                                                     communication

                            99 MANAGEMENT            Network-device
                                                     administration and
                                                     management traffic
  ------------------------------------------------------------------------

Inter-VLAN routing provides communication between VLANs where permitted
by the network configuration and security policies.

## Routing and Network Services

### OSPF

Open Shortest Path First (OSPF) is used as the dynamic routing protocol
in the core network. It allows routers to exchange routing information
and learn routes to networks beyond their directly connected interfaces.

### Inter-VLAN Routing

Layer 3 routing is configured to support communication between the
logical VLAN segments. Switch trunk links carry the required VLAN
traffic between network devices.

### NAT/PAT

Network Address Translation and Port Address Translation are configured
on the network's edge router to translate internal private addresses for
external network communication. PAT allows multiple internal devices to
share an outside address.

## Network Security

Security is implemented through multiple layers:

-   **VLAN segmentation:** Separates user, IoT, and management traffic.
-   **ACL filtering:** Controls traffic between network segments and
    restricts access to protected management resources.
-   **IoT isolation:** Limits unnecessary communication between IoT
    devices and other internal resources.
-   **Wireless security:** Uses WPA2-PSK authentication for wireless
    access.
-   **NAT/PAT:** Provides address translation for internal devices
    communicating with external networks.

These controls are intended to allow required communication while
limiting unauthorized access.

## Wireless and IoT Integration

The IoT & Wireless Zone demonstrates how wireless clients and smart
devices can be incorporated into the wider network.

The implementation includes:

-   A wireless access point.
-   A wireless laptop/client.
-   An IoT controller.
-   A smart light and simulated IoT connectivity.

Wireless connectivity is configured with WPA2-PSK. IoT devices are
registered with the controller and tested for network connectivity and
device operation.

## Verification and Testing

The project report documents verification using Cisco IOS commands and
end-device tests.

  -------------------------------------------------------------------------
  Test Area               Verification Method       Reported Result
  ----------------------- ------------------------- -----------------------
  OSPF routing            `show ip ospf neighbor`   Successful

  VLAN connectivity       Ping to the VLAN gateway  Successful

  IoT gateway             Ping to the IoT gateway   Successful
  connectivity                                      

  ACL security            Test access to a          Verified
                          restricted network        

  Wireless connectivity   SSID connection and ping  Successful
                          test                      

  IoT operation           Test device control       Successful
                          through the IoT           
                          controller                

  NAT/PAT                 NAT configuration and     Verified
                          translation checks        
  -------------------------------------------------------------------------

Useful Cisco IOS verification commands include:

``` text
show ip interface brief
show vlan brief
show interfaces trunk
show ip route
show ip ospf neighbor
show access-lists
show ip nat translations
show ip nat statistics
```

The commands available on a device may vary depending on its model and
Packet Tracer support.

## Repository Structure

A suggested GitHub repository layout:

``` text
smart-city-network/
├── README.md
├── Smart-City-Network.pkt
└── docs/
    ├── project-report.pdf
    └── images/
        └── topology.png
```

Add your actual Packet Tracer file (`.pkt`), report, and topology
screenshot to the repository. Rename the example files or update this
section to match your actual filenames.

## How to Open the Project

1.  Install **Cisco Packet Tracer**.
2.  Clone or download this repository.
3.  Open the `.pkt` project file using Cisco Packet Tracer.
4.  Inspect the topology and device configurations.
5.  Use the verification commands above, where supported, to review
    routing, VLANs, ACLs, and NAT/PAT.

``` bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
```

Replace `<YOUR_GITHUB_REPOSITORY_URL>` with your repository's actual
URL.

## Project Scope and Notes

This is an academic network simulation project developed in Cisco Packet
Tracer. It demonstrates network design and configuration concepts in a
simulated environment; it is not a production-ready smart-city
deployment.

For exact interface assignments, device configurations, and addressing
details, refer to the included `.pkt` file and project report. Confirm
that the final addressing plan in the report matches the submitted
Packet Tracer configuration before publishing detailed subnet values.

## Learning Outcomes

Through this project, the implementation demonstrates practical
experience with:

-   Enterprise-style network topology design.
-   IPv4 addressing and subnet planning.
-   VLAN creation, trunking, and inter-VLAN routing.
-   Dynamic routing with OSPF.
-   ACL-based traffic filtering.
-   NAT/PAT configuration.
-   Wireless network setup and security.
-   IoT device integration.
-   Network verification and troubleshooting.

## Acknowledgements

Developed as a Computer Networking Laboratory (CNL) project using Cisco
Packet Tracer.

------------------------------------------------------------------------

**If you find this project useful, feel free to star the repository.**
