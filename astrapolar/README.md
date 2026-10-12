# AstraPolar — Antarctic Digital Twin & Operations Platform

<p align="center">
  <strong>Offline-First Digital Twin & Remote Operations Platform for India's Antarctic Research Stations (Maitri & Bharati)</strong>
</p>

<p align="center">
  <a href="https://github.com/anshu-0132/AstraPolar"><img src="https://img.shields.io/badge/Author-Divyanshu%20Gupta-blue.svg?style=flat-square" alt="Author"></a>
  <a href="https://github.com/anshu-0132/AstraPolar/blob/main/LICENSE"><img src="https://img.shields.io/badge/License-MIT-green.svg?style=flat-square" alt="License"></a>
  <a href="packages/shared/package.json"><img src="https://img.shields.io/badge/TypeScript-5.7%2B-3178C6?logo=typescript&logoColor=white&style=flat-square" alt="TypeScript"></a>
  <a href="apps/api/package.json"><img src="https://img.shields.io/badge/Node.js-20%2B-339933?logo=node.js&logoColor=white&style=flat-square" alt="Node.js"></a>
  <a href="apps/web/package.json"><img src="https://img.shields.io/badge/React-19-61DAFB?logo=react&logoColor=white&style=flat-square" alt="React"></a>
  <a href="docker-compose.yml"><img src="https://img.shields.io/badge/TimescaleDB-PostgreSQL_16-FDB515?logo=postgresql&logoColor=white&style=flat-square" alt="TimescaleDB"></a>
  <a href="docker-compose.yml"><img src="https://img.shields.io/badge/MQTT-Mosquitto_2-660066?logo=eclipsemosquitto&logoColor=white&style=flat-square" alt="MQTT"></a>
  <a href="apps/api/src/copilot/copilot.service.ts"><img src="https://img.shields.io/badge/Ollama-gemma4%3Ae2b-FF6F00?logo=google&logoColor=white&style=flat-square" alt="Offline LLM"></a>
  <a href="docker-compose.yml"><img src="https://img.shields.io/badge/Docker-Compose-2496ED?logo=docker&logoColor=white&style=flat-square" alt="Docker"></a>
</p>

**Status:** High-fidelity operational platform featuring digital twin state management, live telemetry streaming, dependency cascade evaluation, multi-hazard what-if simulation sandbox, offline LLM advisory copilot, and audit trails.

---

## 🚀 Overview

Antarctic research stations operate under extreme weather, sub-zero conditions, scarce satellite bandwidth, and mission-critical infrastructure interdependencies.

**AstraPolar** provides a comprehensive digital representation of India's polar stations:
- **Maitri** — Schirmacher Oasis
- **Bharati** — Larsemann Hills

It integrates multi-sensor telemetry, 3D spatial models, deterministic dependency graphs, anomaly detectors, energy/logistics microgrid optimization, and isolated what-if simulations in a unified mission operations console.

---

## 🎯 Key Capabilities

A conventional dashboard only shows *what is happening*.  
**AstraPolar** answers: **"What happens if this component fails?"**

| Capability | Purpose |
|---|---|
| **3D Digital Twin** | Maintains real-time spatial and operational states for station assets |
| **Dependency Graph** | Models topological and inter-system relationships across power, HVAC, and comms |
| **Cascade Analysis** | Computes downstream failure risks before primary outages propagate |
| **What-If Simulation** | Evaluates contingency scenarios in an isolated memory buffer without polluting live telemetry |
| **Energy & Microgrid** | Monitors generation, storage levels, diesel reserves, and solar availability |
| **Anomaly Detection** | Highlights statistical deviations across sensor channels |
| **Offline AI Copilot** | Local Gemma 4 via Ollama provides contextual explanations and emergency checklists |
| **Audit Logging** | Maintains an immutable operational ledger for safety compliance |

---

## 🏗️ Architecture

```text
Telemetry / Sensor Ingest
            ↓
       MQTT Broker
            ↓
  AstraPolar Express API
            ↓
   ┌────────┴────────┐
   ↓                 ↓
TimescaleDB      Analytics
                     ↓
              Dependency Graph
                     ↓
              What-If Simulation
                     ↓
              React + Three.js
                     ↓
            Local Ollama Copilot
                 (Advisory)
```

---

## 🚀 Quick Start

### Prerequisites
- **Node.js** 20+
- **npm**
- **Docker + Docker Compose**
- **Ollama** *(optional, for offline copilot)*

### Local Setup

```bash
# 1. Start database and MQTT broker
docker compose up -d db mqtt

# 2. Install dependencies
npm install

# 3. Setup and seed database
npm run db:setup

# 4. Start API server
npm run dev:api
```

In a separate terminal:

```bash
# 5. Start Web Mission Control
npm run dev:web
```

- **Operations Console:** `http://localhost:5173`
- **Backend API:** `http://localhost:3001`

---

## 🤖 Offline AI Copilot

```bash
ollama serve
ollama pull gemma4:e2b
```

Ollama runs locally at `http://localhost:11434`. The core digital twin and cascade simulation logic function 100% offline without requiring the LLM.

---

## 👤 Author & Maintainer

**Divyanshu Gupta**
- **GitHub:** [@anshu-0132](https://github.com/anshu-0132)
- **Repository:** [AstraPolar](https://github.com/anshu-0132/AstraPolar)
- **Email:** divyanshu0132@gmail.com

---

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](../LICENSE) file.
