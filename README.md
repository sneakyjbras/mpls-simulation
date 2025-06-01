
# MPLS VPN Lab (GNS3)

This repository provides a reproducible, multi‑stage lab that demonstrates how to build a carrier‑style MPLS Layer‑3 VPN backbone in **GNS3**.  
Starting with a basic OSPF core, the lab enables LDP, constructs end‑to‑end label‑switched paths, and then scales to multiple VRFs—including an overlapping‑prefix scenario on a shared PE.

## Directory layout

```
.
├── configs          # Start‑up configs for each milestone
│   ├── ospf/        #   – OSPF‑only backbone
│   ├── mpls/        #   – OSPF + LDP (transport pipe)
│   └── vpn/         #   – Full MP‑BGP VPN (PE/P/CE)
├── docs             # PDF report & per‑task hand‑ins
├── pics             # PNG topology diagrams used in the report
└── README.md
```

* **configs** — IOSv configuration files for every router (R1‑R5 for OSPF/MPLS, P1‑P6 & PE1‑PE3 for VPN).  
* **docs** — Compiled step‑by‑step report (`report.pdf`) plus interim submissions.  
* **pics** — High‑resolution network diagrams (`topology.png`, `vpn_topology.png`).

## Requirements

* GNS3 ≥ 2.2 with the **IOSv 15.x** appliance  
* ≈ 1 GiB RAM per virtual router (tested with 5 × IOSv images)  
* Python 3.x plus `gns3‑server` CLI if you prefer scripted deployment

## Quick start

1. Clone the repo and open `vpn_topology.gns3` (or build manually from `pics/topology.png`).  
2. Boot all routers with the OSPF configurations found in `configs/ospf/`.  
3. Progress through `configs/mpls/` and `configs/vpn/`, verifying each milestone with the commands in **docs/report.pdf**.  
4. Simulate link failures to observe sub‑second OSPF/LDP re‑convergence.

## Report

A full lab write‑up—including topology rationale, CLI output, LIB/LFIB snapshots and failure tests—is available at:

```
docs/report.pdf
```

## Licence

MIT.  Use the topology, configs and report fragments as you see fit.
