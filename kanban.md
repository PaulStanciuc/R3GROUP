---
project: r3group-kf
description: "R3GROUP Katty Fashion pilot – digital tools for co-creation, digital twins and technician capacity planning"
type: eu-project

team:
CPTO: el.tech@katty-fashion.ro
Tech Lead: eduard.modreanu@katty-fashion.ro   
Front-End: alexandru.bejenari@katty-fashion.ro  
Back-End: razvan.boita@katty-fashion.ro 
Product Owner: ps.tech@katty-fashion.ro 

sprint: S1
sprint_start: 2026-03-02
sprint_end: 2026-03-13
depends_on: [ai-rise]
tags: [r3group, digital-twin, capacity-planner, manufacturing]
---

# Project Kanban

## Team
- **Product Owner:** ps.tech@katty-fashion.ro  
- **Tech Lead:** el.tech@katty-fashion.ro  
- **Front-End:** alexandru.bejenari@katty-fashion.ro  
- **Back-End:** razvan.boita@katty-fashion.ro  

---

## Project Context

This repository supports the **Katty Fashion pilot implementation within the R3GROUP Horizon Europe project**.

The goal is to enable **digital integration between product development and manufacturing processes** in garment production through several key tools:

- **Co-creation platform (Nuoform / T2.1)** — implementată și testată cu doi clienți pilot; include Technical Pack, managementul comenzilor, inventar, recepție și integrare Made2Flow pentru impact de sustenabilitate  
- **Product Digital Twin (T3.2)** — finalizat; conectează pachetele tehnice cu datele de producție  
- **Process Digital Twin (T3.2)** — implementat cu Siemens Tecnomatix; simulează fluxul de producție (stații cusut/călcat, mișcări lucrători) și validat cu date istorice  
- **Technician Capacity Planner (T2.4)** — backend 100% finalizat; UI aproape finalizat; integrarea cu modelul matematic LMS în curs  
- **IoT Monitoring (T3.3)** — în testare: senzori radar 60 GHz (prezență operator) și monitorizare consum energie mașini de cusut  

These tools aim to improve **resilience, reconfigurability and digitalization of the garment production workflow**.

---

## Status General M36

| Pilon | Componentă | Status M36 |
| :--- | :--- | :--- |
| WP1 — Infrastructură Digitală | Adaptare platformă AAS | 90% finalizat |
| WP1 — Infrastructură Digitală | Structură Product Digital Twin | ✅ Finalizat & integrat |
| T2.1 — Co-creare Nuoform | Platformă co-creare | ✅ Implementat & testat (2 clienți pilot) |
| T3.2 — Digital Twins | Product DT | ✅ Finalizat |
| T3.2 — Digital Twins | Process DT (Tecnomatix) | ✅ Implementat & validat cu date istorice |
| T2.4 — Capacity Planner | Backend LMS Scheduler | ✅ 100% finalizat |
| T2.4 — Capacity Planner | KF Frontend UI | 🔄 Aproape finalizat |
| T2.4 — Capacity Planner | Integrare UI ↔ LMS | 🔄 În curs |
| T3.3 — IoT Monitoring | Senzori radar 60 GHz + energie | 🧪 În testare |

**KPI-uri țintă:**

| Indicator | Țintă |
| :--- | :--- |
| Reducere deșeuri (scrap) | −20% |
| Reducere timp reconfigurare | −35% |
| Reducere lead time | −50% |
| Eliminare deșeuri pre-consum (prototipare virtuală) | −95% |

---

<!-- Valid statuses: Todo, In Progress, Review, Done -->
<!-- Effort format: Nd (e.g. 1d, 0.5d, 3d) -->

| Task | Assignee | Effort | Start | End | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Repository setup and Kanban initialization | @tech-lead | 1d | 2026-03-02 | 2026-03-02 | Done |
| Define system architecture (planner + digital twins) | @tech-lead | 2d | 2026-03-03 | 2026-03-04 | In Progress |
| Setup project documentation (R3GROUP context) | @tech-lead | 1d | 2026-03-04 | 2026-03-04 | In Progress |
| Define technician task model and scheduling logic | @backend | 2d | 2026-03-05 | 2026-03-06 | Done |
| Implement backend service for technician capacity planner | @backend | 3d | 2026-03-06 | 2026-03-10 | Done |
| Implement planner UI dashboard (calendar + workload view) | @frontend | 3d | 2026-03-06 | 2026-03-10 | In Progress |
| Integrate planner with order and task data model | @backend | 2d | 2026-03-10 | 2026-03-11 | In Progress |
| Connect UI with backend API (LMS integration) | @frontend | 1.5d | 2026-03-11 | 2026-03-12 | Todo |
| Finalize AAS firmware integration (BLE box tracking) | @backend | 2d | 2026-03-11 | 2026-03-12 | Todo |
| Connect IoT sensors to AAS platform | @backend | 2d | 2026-03-12 | 2026-03-13 | Todo |
| Sprint review and technical validation | @tech-lead | 0.5d | 2026-03-13 | 2026-03-13 | Todo |

---

## Pași Următori (M36 → M40+)

| Prioritate | Acțiune | Responsabil |
| :--- | :--- | :--- |
| 🔴 High | Finalizare conexiune UI KF ↔ model LMS (Capacity Planner) | @frontend + @backend |
| 🔴 High | Finalizare integrare firmware AAS (cutii producție BLE) | @backend |
| 🟡 Med | Conectare senzori IoT la platforma AAS | @backend |
| 🟢 Low | Trecere la demonstrație la scară largă TRL7 (M40, coordonat IPC) | @tech-lead |
