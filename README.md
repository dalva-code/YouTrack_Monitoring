# 🧩 YouTrack Monitoring Stack

![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?logo=grafana&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?logo=prometheus&logoColor=white)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)

A complete monitoring environment built with **Docker Compose**, integrating **Prometheus**, **Grafana**, **Loki**, **Alertmanager**, and **PostgreSQL**.  
This project demonstrates how to collect, store, and visualize system metrics — focusing on CPU usage monitoring through Prometheus and Grafana dashboards.

---

## ⚙️ Stack Overview

| Service | Port | Description |
|----------|------|-------------|
| **Prometheus** | `9090` | Metrics collection and time-series storage |
| **Grafana** | `3000` | Dashboard visualization and alerting |
| **Loki** | `3100` | Log aggregation system |
| **Alertmanager** | `9093` | Alert routing and notification management |
| **PostgreSQL** | `5488` | Sample database for metric correlation |
| **Node Exporter** | `9100` | Host-level CPU & memory metrics exporter |

---

## 🧠 Objective

The goal of this setup is to provide a **working monitoring environment** that shows how to:

- Deploy Grafana + Prometheus + Loki + Alertmanager with Docker.
- Collect and visualize metrics (like CPU usage).
- Treat observability as code (versioned, reproducible setup).
- Export dashboards as JSON and include them in Git repositories.

---

## 📊 CPU Usage Dashboard

This Grafana dashboard visualizes average CPU usage per instance based on Prometheus metric:
job:cpu_usage:5m

**Thresholds:**
- 🟢 Normal → < 70 %
- 🟡 Warning → 70–90 %
- 🔴 Critical → > 90 %

---

## 🚀 How to Run

```bash
cd ~/YouTrack_Monitoring/demo-stack
docker compose up -d

Then access:

	•	Grafana → http://localhost:3000￼
	•	Prometheus → http://localhost:9090￼
	•	Alertmanager → http://localhost:9093￼

To stop the environment:
docker compose down


📁 Directory Structure

YouTrack_Monitoring/
└── demo-stack/
    ├── docker-compose.yaml
    ├── prometheus/
    │   ├── prometheus.yml
    │   └── rules/
    │       └── cpu.rules.yml
    ├── grafana/
    │   ├── dashboards/
    │   │   ├── cpu_usage.json
    │   │   └── definitions/
    │   └── dashboard.yaml
    ├── loki/
    ├── alertmanager/
    ├── postgres/
    └── README.md

## 👤 Author  
**David Esteban Correa**  
Dual Degree in Computer Science & Business Administration  
AWS & Machine Learning Certified | Solidity Developer  
[GitHub → dalva-code](https://github.com/dalva-code)

## 📜 License  
MIT License © 2025 David Esteban Correa
