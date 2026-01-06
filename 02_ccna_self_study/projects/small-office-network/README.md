# Small Office Network – VLAN, Routing & Basic Security

## 📌 Project Overview
This project simulates a small office network using real Cisco hardware.
The goal is to design, configure, and verify a segmented network using VLANs,
inter-VLAN routing, and basic access control.

The lab is built as part of my CCNA self-study preparation and focuses on
hands-on configuration, verification, and documentation.

---

## 🧱 Network Scenario
A small office has multiple departments that must be logically separated
for security and management purposes.

### Departments
- HR Department
- IT Department
- Management

Each department is placed in its own VLAN with controlled access between them.

---

## 🖥 Devices Used
- **Cisco Catalyst WS-C2960+24PC-L** (Layer 2 Switch)
- **Cisco 1921 Router** (Inter-VLAN Routing)
- End devices (PCs / test hosts)

---

## 🌐 VLAN & IP Addressing Plan

| VLAN ID | Name        | Subnet              | Default Gateway     |
|-------:|-------------|---------------------|---------------------|
| 10     | HR          | 192.168.10.0/24     | 192.168.10.1        |
| 20     | IT          | 192.168.20.0/24     | 192.168.20.1        |
| 30     | Management  | 192.168.30.0/24     | 192.168.30.1        |

---

## ⚙ Configuration Tasks

### 🔹 Switching (Cisco 2960)
- Create VLANs 10, 20, and 30
- Assign access ports to the correct VLANs
- Configure trunk port toward the router
- Verify VLAN and trunk configuration

### 🔹 Routing (Cisco 1921 – Router on a Stick)
- Configure sub-interfaces for each VLAN
- Enable 802.1Q encapsulation
- Assign IP addresses as default gateways

### 🔹 Security (Basic ACL)
- HR VLAN (10) is **not allowed** to access IT VLAN (20)
- Management VLAN (30) has full access
- ACLs applied on router sub-interfaces

---

## 🧪 Verification & Testing

### Connectivity Tests
- Ping between hosts in the same VLAN
- Ping between allowed VLANs
- Verify blocked traffic according to ACL rules

### Verification Commands
- `show vlan brief`
- `show interfaces trunk`
- `show ip route`
- `show access-lists`

---

## 🔐 Security Considerations
VLAN segmentation reduces the attack surface by isolating departments.
Access Control Lists provide basic traffic filtering between networks.
In a production environment, additional security mechanisms such as
firewalls, IDS/IPS, and logging would be implemented.

---

## 📂 Repository Structure
small-office-network/
├── docs/
│ ├── topology.png
│ └── requirements.md
├── switch-config/
│ └── c2960.txt
├── router-config/
│ └── c1921.txt
├── testing/
│ └── test-results.md
└── README.md


---

## 📚 What I Learned
- How VLANs provide logical network segmentation
- How inter-VLAN routing works using a single router interface
- How to configure and verify trunk links
- How basic ACLs can control inter-department communication
- Importance of verification and documentation

---

## 🚀 Possible Improvements
- Add DHCP service for dynamic IP addressing
- Implement NAT for internet access
- Extend ACLs with more granular rules
- Migrate the lab to GNS3 for multi-router scenarios

---

## 📝 Notes
This lab was performed using real Cisco hardware and documented as part of
my CCNA preparation and networking portfolio.

