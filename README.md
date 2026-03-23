# Homelab

A production-style Kubernetes homelab managed with GitOps. This repository represents my personal infrastructure-as-code practice — not a reproducible template, but a working example of how I design, deploy, and operate self-hosted systems.

## Stack

- **Orchestration:** Kubernetes, Flux CD (GitOps)
- **Ingress & Networking:** Traefik, CoreDNS, Headscale (WireGuard mesh VPN), network policies
- **Databases:** PostgreSQL (two clusters), MariaDB, MongoDB, SQLite
- **Storage:** MinIO (S3-compatible object storage), NFS-backed persistent volumes
- **Secrets:** SOPS + age encryption — all secrets are encrypted at rest in git
- **Observability:** Prometheus + Grafana (kube-prometheus-stack)
- **TLS:** cert-manager with automated certificate lifecycle

## Applications

| App | Purpose |
|-----|---------|
| **CyberProject** | Custom Python/Flask API with MongoDB backend and ML integrations (HuggingFace, OpenAI) |
| **Clearpath** | Full-stack app with Node.js REST API and MongoDB |
| **Nextcloud** | Self-hosted file storage and collaboration |
| **Plane** | Project management, backed by PostgreSQL and MinIO |
| **Home Assistant** | Home automation |
| **Jellyfin** | Media server |
| **Mealie** | Recipe management with PostgreSQL backend |
| **SearXNG** | Self-hosted metasearch engine |
| **RJT** | My little website |

## Highlights

- All infrastructure and application config is declarative and version-controlled
- Secrets are encrypted with SOPS/age and committed safely to git
- Multi-environment structure (`staging`) with Flux-managed sync
- Two independent PostgreSQL clusters serving multiple applications
- Metrics collection and dashboarding across the entire cluster
