# AstraPolar — Antarctic Digital Twin & Operations Platform

<p align="center">
  <strong>Offline-First Digital Twin & Remote Operations Platform for India's Antarctic Research Stations (Maitri & Bharati)</strong>
</p>

<p align="center">
  <a href="https://github.com/anshu-0132/AstraPolar"><img src="https://img.shields.io/badge/Author-Divyanshu%20Gupta-blue.svg?style=flat-square" alt="Author"></a>
  <a href="https://github.com/anshu-0132/AstraPolar/blob/main/LICENSE"><img src="https://img.shields.io/badge/License-MIT-green.svg?style=flat-square" alt="License"></a>
  <a href="https://github.com/anshu-0132/AstraPolar"><img src="https://img.shields.io/badge/TypeScript-5.7%2B-3178C6?logo=typescript&logoColor=white&style=flat-square" alt="TypeScript"></a>
  <a href="https://github.com/anshu-0132/AstraPolar"><img src="https://img.shields.io/badge/Node.js-20%2B-339933?logo=node.js&logoColor=white&style=flat-square" alt="Node.js"></a>
  <a href="https://github.com/anshu-0132/AstraPolar"><img src="https://img.shields.io/badge/React-19-61DAFB?logo=react&logoColor=white&style=flat-square" alt="React"></a>
  <a href="https://github.com/anshu-0132/AstraPolar"><img src="https://img.shields.io/badge/TimescaleDB-PostgreSQL_16-FDB515?logo=postgresql&logoColor=white&style=flat-square" alt="TimescaleDB"></a>
  <a href="https://github.com/anshu-0132/AstraPolar"><img src="https://img.shields.io/badge/MQTT-Mosquitto_2-660066?logo=eclipsemosquitto&logoColor=white&style=flat-square" alt="MQTT"></a>
  <a href="https://github.com/anshu-0132/AstraPolar"><img src="https://img.shields.io/badge/Offline_AI-Gemma_4-FF6F00?logo=google&logoColor=white&style=flat-square" alt="Offline AI"></a>
  <a href="https://github.com/anshu-0132/AstraPolar"><img src="https://img.shields.io/badge/Docker-Compose-2496ED?logo=docker&logoColor=white&style=flat-square" alt="Docker"></a>
</p>

---

## 🚀 Overview

**AstraPolar** is an advanced, offline-first digital twin and remote operations platform built to monitor, model, and safeguard India's polar research stations:
- **Maitri** — Schirmacher Oasis
- **Bharati** — Larsemann Hills

Antarctic research facilities face sub-zero temperatures, intense blizzards, satellite blackouts, and critical physical infrastructure dependencies. **AstraPolar** moves beyond traditional monitoring dashboards to deliver proactive situational awareness, dependency cascade mapping, what-if disaster simulation, and local edge intelligence.

---

## 🎯 Key Capabilities

| Capability | Description |
|---|---|
| 🌐 **3D Digital Twin** | Interactive Three.js spatial view of station facilities, modules, and physical subsystems. |
| ⚡ **Microgrid & Energy Logistics** | Live tracking of generators, solar arrays, battery bank states, and fuel consumption rates. |
| 🔗 **Dependency Graph Engine** | Maps dependencies across life-support, power, communication, and heating networks. |
| 💥 **Cascade Failure Analysis** | Predicts downstream repercussions before a primary system breakdown triggers critical failures. |
| 🧪 **What-If Simulation Sandbox** | Safely tests multi-hazard disaster scenarios (e.g., blizzards, fuel freezes) in an isolated state without disrupting live telemetry. |
| 📡 **High-Throughput Telemetry** | Low-latency telemetry pipeline powered by Mosquitto MQTT, TimescaleDB, and WebSockets. |
| 🤖 **Offline AI Ops Copilot** | Advisory incident explanations and emergency checklists powered by local Gemma 4 via Ollama. |
| 🛡️ **Audit Logging** | Complete audit trace of operator commands and system state transitions. |

---

## 🏗️ System Architecture

```text
               ┌───────────────────────────────┐
               │    Sensors & IoT Telemetry    │
               │   (Simulator / Field Devices) │
               └───────────────┬───────────────┘
                               │ MQTT
                               ▼
               ┌───────────────────────────────┐
               │    Mosquitto MQTT Broker      │
               └───────────────┬───────────────┘
                               │
                               ▼
               ┌───────────────────────────────┐
               │     AstraPolar API Core       │
               │  (Express + Digital Twin SM)  │
               └───────┬───────────────┬───────┘
                       │               │
        ┌──────────────┴───────┐       └──────────────┐
        ▼                      ▼                      ▼
┌──────────────┐     ┌───────────────────┐     ┌──────────────┐
│ TimescaleDB  │     │ Dependency Engine │     │ WebSocket    │
│  (Telemetry) │     │ & Simulation Core │     │ Stream Server│
└──────────────┘     └─────────┬─────────┘     └──────┬───────┘
                               │                      │
                               ▼                      ▼
               ┌──────────────────────────────────────┐
               │      AstraPolar Web Console          │
               │   (React 19 + Three.js 3D Canvas)    │
               └──────────────────┬───────────────────┘
                                  │
                                  ▼
               ┌──────────────────────────────────────┐
               │       Local Offline AI Copilot       │
               │         (Gemma 4 via Ollama)         │
               └──────────────────────────────────────┘
```

---

## 📁 Repository Structure

```
AstraPolar/
├── astrapolar/
│   ├── apps/
│   │   ├── api/                # Backend API service (Express, MQTT, Twin engine)
│   │   │   └── src/
│   │   │       ├── copilot/     # Offline LLM advisory service
│   │   │       ├── intelligence/# Anomaly detection & risk evaluation
│   │   │       ├── logistics/   # Fuel & supply window optimization
│   │   │       ├── simulation/  # What-if multi-hazard simulation engine
│   │   │       ├── telemetry/   # MQTT ingest & sensor simulator
│   │   │       └── twin/        # Digital twin state & dependency graph
│   │   └── web/                # Frontend mission control (React 19 + Three.js)
│   │       └── src/
│   │           ├── components/  # Nav, Header, Layout components
│   │           └── features/    # Twin 3D view, Microgrid, Alerts, Copilot
│   ├── packages/
│   │   └── shared/             # Shared TypeScript data models & schemas
│   ├── docker/                 # Container images for API, Web, Mosquitto
│   ├── docker-compose.yml      # Multi-container orchestration
│   └── package.json            # Monorepo workspaces definition
├── .gitignore
├── LICENSE
└── README.md
```

---

## ⚡ Quick Start

### 1. Prerequisites
- **Node.js** >= 20.0.0
- **npm** >= 10.0.0
- **Docker & Docker Compose**
- **Ollama** *(optional, for offline copilot)*

### 2. Clone and Enter Project

```bash
git clone https://github.com/anshu-0132/AstraPolar.git
cd AstraPolar/astrapolar
```

### 3. Spin Up Infrastructure

```bash
# Launch TimescaleDB and Mosquitto MQTT broker
docker compose up -d db mqtt
```

### 4. Install Dependencies & Setup Database

```bash
# Install monorepo dependencies
npm install

# Initialize and seed TimescaleDB schema
npm run db:setup
```

### 5. Launch Development Servers

Start the backend API:
```bash
npm run dev:api
```

In another terminal, start the web mission console:
```bash
npm run dev:web
```

- **Mission Operations Console:** `http://localhost:5173`
- **Backend API:** `http://localhost:3001`

---

## 🤖 Offline AI Copilot Setup (Optional)

To enable the local advisory assistant without an active internet connection:

```bash
# Start local Ollama server
ollama serve

# Pull lightweight Gemma model
ollama pull gemma4:e2b
```

The AstraPolar core twin, dependency evaluator, and simulation engine operate completely independently of the AI model.

---

## 👤 Author & Maintainer

**Divyanshu Gupta**
- **GitHub:** [@anshu-0132](https://github.com/anshu-0132)
- **Repository:** [AstraPolar](https://github.com/anshu-0132/AstraPolar)
- **Email:** divyanshu0132@gmail.com

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.
