# Active Directory Attack Lab

A practical, reproducible AD lab that models a small corporate network (DC + 2 clients + Kali).  
It documents end-to-end attack paths—from initial access through domain compromise and post-exploitation—along with the exact commands and scripts used.  
Designed for isolated, local use under a single NAT network.

---

## Topology

![Lab Topology](docs/diagrams/ad_attack_lab_topology.png)

---

## Requirements

- **Host**: 16 GB RAM (minimum), 6+ vCPU recommended, 120+ GB free disk
- **Hypervisor**: VMware Workstation / VirtualBox / Hyper-V
- **ISOs**: Windows Server 2022 (for DC), Windows 10 (for clients), Kali Linux
- **Networking**: Single NAT network for the lab
- **Tools (examples)**: nmap, Impacket, netexec, Responder, mitm6, BloodHound, Mimikatz

---

## VM Summary

| Role                | OS                  | vCPU | RAM  | Disk | Notes                 |
|---------------------|---------------------|:---:|:----:|:----:|------------------------|
| Domain Controller   | Windows Server 2022 |  2  | 4 GB | 30GB | AD DS + DNS            |
| Client 1            | Windows 10          |  2  | 2 GB | 30GB | Domain-joined          |
| Client 2            | Windows 10          |  2  | 2 GB | 30GB | Domain-joined          |
| Attack Machine      | Kali Linux          |  8  | 8 GB | 80GB | Tooling & automation   |

---

## Repository Structure

Each technique entry is documented in a compact, repeatable format : context & scope -> commands executed -> expected results/artifacts with optional OPSEC/detection notes, mitigations, and references.
