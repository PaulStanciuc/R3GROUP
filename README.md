# R3GROUP — Katty Fashion Digital Manufacturing Platform

> Katty Fashion pilot implementation for the **R3GROUP Horizon Europe project**, enabling resilient and rapidly reconfigurable garment production through Digital Twins and AAS-based manufacturing architecture.

---

# Quick Links

- KF Team Dashboard  
https://katty-fashion.github.io/kf-cpto/

- Unified Kanban  
https://katty-fashion.github.io/kf-cpto/unified-kanban.html

- R3GROUP Project (CORDIS)  
https://cordis.europa.eu/project/id/101091869

---

# Project Overview

**R3GROUP (Resilient Rapid Reconfigurable Production Process Chains)** is a Horizon Europe research project aimed at enabling **flexible, digital, and resilient manufacturing ecosystems**.

The project focuses on:

- rapid reconfiguration of production systems
- digital integration between design and manufacturing
- interoperability across supply chain partners
- human-centered manufacturing environments.

The **Katty Fashion pilot** demonstrates these capabilities within the **garment manufacturing industry**, integrating digital tools across the full product lifecycle.

---

# Core Digital Concepts

The platform integrates several Industry 4.0 concepts:

### Digital Twin
Digital representation of:

- garments
- manufacturing processes
- production resources

### Asset Administration Shell (AAS)

Standardized digital interface representing assets in the manufacturing system.

Allows interoperability between:

- machines
- software systems
- digital twins.

### Digital Thread

Continuous data flow connecting:

- design
- production planning
- manufacturing execution
- product lifecycle monitoring.

---

# Platform Architecture

## System Architecture Overview

```mermaid
graph TD

A[Designer] --> B[Co-Creation Platform]
B --> C[API Gateway]

C --> D[Product Digital Twin]
C --> E[Process Digital Twin]
C --> F[Capacity Planner]

D --> G[(Digital Product Data)]
E --> H[(Process Models)]
F --> I[(Planning Database)]

D --> J[AAS Layer]
E --> J
F --> J

J --> K[Manufacturing Systems]

---

# Main Platform Components

## 1. Co-Creation Platform

Collaborative workspace where stakeholders can:

- define product specifications
- exchange design information
- coordinate manufacturing requirements
- track order lifecycle.

Supports collaboration between:

- designers
- suppliers
- manufacturers.

The platform enables digital collaboration across the product lifecycle and connects design activities with manufacturing preparation.

---

## 2. Product Digital Twin

The **Product Digital Twin** represents the digital identity of each garment.

It includes:

- design specifications
- material data
- technical packs
- production parameters.

### Benefits

- lifecycle traceability
- centralized digital product documentation
- interoperability between design and manufacturing tools
- consistent data exchange across systems.

The digital twin allows product information to remain synchronized across the entire manufacturing workflow.

---

## 3. Process Digital Twin

The **Process Digital Twin** models the manufacturing process itself.

It is used for:

- production simulation
- capacity analysis
- workflow optimization
- reconfiguration planning.

This allows planners to simulate manufacturing scenarios before execution and evaluate potential changes to production workflows.

---

## 4. Technician Capacity Planner

The **Technician Capacity Planner** is designed to assist the **development manager and technician department**.

### Core functions

- technician workload visualization
- scheduling production preparation tasks
- evaluating department capacity
- adapting planning based on order changes.

### Interface capabilities

- interactive planning calendar
- workload indicators
- drag-and-drop scheduling
- dynamic resource allocation.

The tool helps optimize preparation activities required before production begins.

---

# Microservice Architecture

```mermaid
graph TD

API[API Gateway]

API --> CC[Co-Creation Service]
API --> PDT[Product Digital Twin]
API --> PRDT[Process Digital Twin]
API --> CP[Capacity Planner]

CC --> DB[(PostgreSQL)]
PDT --> DB
PRDT --> DB
CP --> DB

CC --> MQ[RabbitMQ]
PDT --> MQ
PRDT --> MQ
CP --> MQ

DB --> STORAGE[File Storage]

## Data Flow 
### sequenceDiagram

participant Designer
participant Platform
participant DigitalTwin
participant Planner
participant Manufacturing

Designer->>Platform: Submit product design
Platform->>DigitalTwin: Create product digital twin
DigitalTwin->>Planner: Request planning evaluation
Planner->>Planner: Calculate capacity
Planner-->>Platform: Production feasibility
Platform-->>Designer: Production schedule

Planner->>Manufacturing: Send planning data

## Development

### Prerequisites

```
Node.js 20+
Python 3.11+
Docker
Docker Compose
Kubernetes (optional)
```

### Setup

```bash
git clone https://github.com/katty-fashion/r3group-kf.git
cd r3group-kf
```

Install dependencies:

```bash
npm install
```

### Run Locally

```bash
docker compose up
```

---

## Kanban Management

This repository integrates with the **KF-CPTO Git-native project management dashboard**.

The project uses:

```
kanban.md
```

as the single source of truth for task tracking.

Updating this file automatically updates:

- unified Kanban board
- sprint calendar
- LOE reports
- dependency graph

---

## Repository Structure

```
r3group-kf/

├── kanban.md
├── README.md
├── .github/workflows/
│   └── notify-kf-cpto.yml
│
├── src/
│   ├── api/
│   ├── planner/
│   ├── digital-twin/
│   ├── services/
│   └── utils/
│
├── docs/
├── tests/
│
├── Dockerfile
└── docker-compose.yml
```

---

## Team

| Role | Contact |
|---|---|
| Product Owner | ps.tech@katty-fashion.ro |
| Tech Lead | el.tech@katty-fashion.ro |
| Front-End | alexandru.bejenari@katty-fashion.ro |
| Back-End | razvan.boita@katty-fashion.ro |

---

## Project Information

| | |
|---|---|
| **Project** | R3GROUP |
| **Full name** | Resilient Rapid Reconfigurable Production Process Chains |
| **Programme** | Horizon Europe |
| **Grant Agreement** | 101091869 |

The project develops technologies enabling rapidly reconfigurable manufacturing systems using digital twins and advanced digital platforms.

The Katty Fashion pilot demonstrates these technologies in the garment manufacturing industry.

---

## Part of the Katty Fashion Digital Manufacturing Ecosystem

Connected projects include:

- AI-RISE
- NUOFORM
- AI-REGIO
- Waste Management Platform

