# Multi Data Center Infrastructure

This project represents a real-world infrastructure deployment across 4 locations:

- Jakarta (Primary)
- Bekasi
- Batam
- Bandung

## Architecture

- WireGuard VPN (Hub-Spoke → planned Mesh)
- MinIO replication (cross-site)
- MariaDB replication
- Kubernetes workloads

## Goals

- High Availability
- Data Redundancy
- Disaster Recovery
