# Homelab Infrastructure

## Overview
A self-hosted home lab focused on DNS filtering, monitoring, centralized logging, reverse proxy routing, and containerized services.

## Goals
- Improve practical networking and systems administration skills
- Work on observability and service hosting
- Document infrastructure

## Components
- DNS ad blocker
- Grafana and Prometheus
- Centralized logging (ELK)
- Reverse proxy
- Docker Compose

## Architecture
```mermaid
flowchart TD
    A[Home Devices<br/>PC, Laptop] --> B[Router / Gateway]
    B --> C[Homelab Host]

    subgraph C1 [Homelab Services]
        D[DNS Filtering<br/>Pi-hole]
        E[Reverse Proxy<br/>NGINX]
        F[Monitoring<br/>Prometheus]
        G[Dashboards<br/>Grafana]
        H[Centralized Logging<br/>ELK Stack]
    end

    C --> D
    C --> E
    C --> F
    C --> G
    C --> H

    D --> J[Upstream DNS]
    J --> K[Internet]

    D --> H
    F --> G
    C --> F
    E --> G
    E --> H
