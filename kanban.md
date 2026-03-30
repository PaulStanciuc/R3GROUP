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

sprint: S2
sprint_start: 2026-03-16
sprint_end: 2026-04-03
last_updated: 2026-03-30  # Stand-up 30.03.2026

depends_on: [ai-rise]
tags: [r3group, digital-twin, capacity-planner, manufacturing]
---

# Project Kanban — R3GROUP Katty Fashion (M36+)

> **Ultima actualizare:** Stand-up 30.03.2026  
> **Legendă status:** ✅ Done · 🔄 In Progress · ⏭️ Next · ⚠️ Blocat · 📋 Todo

---

## Project Context (Updated M36)

Katty Fashion implementează **pilotul R3GROUP Horizon Europe** pentru integrare digitală între dezvoltarea produsului și procesele de producție.

Ecosistemul digital cuprinde:

1. **Co-Creation Platform (T2.1)** — Nuoform B2B, complet implementat cu 2 clienți pilot; integrat cu Made2Flow API
2. **Product Digital Twin (T3.2)** — structură AAS-compliantă finalizată
3. **Process Digital Twin (T3.2)** — Siemens Tecnomatix, validat cu date istorice
4. **Technician Capacity Planner (T2.4)** — UI implementat; integrare cu LMS Scheduler în curs
5. **IoT Monitoring (T3.3)** — senzori radar 60GHz + consum energie, în testare

> **Obiectiv final:** Digital thread produs → planificare → producție, sistem de producție reconfigurabil.

---

## Status General M36

| Pillar | Component | Status |
|---|---|---|
| WP1 — Digital Infrastructure | AAS platform integration | 90% |
| T2.1 — Co-creation platform | Nuoform platform | ✅ Completed |
| T3.2 — Product Digital Twin | AAS model | ✅ Completed |
| T3.2 — Process Digital Twin | Tecnomatix simulation | ✅ Implemented & validated |
| T2.4 — Capacity Planner | LMS Scheduler Backend | ✅ Completed |
| T2.4 — Capacity Planner | KF Planner UI | 🔄 Near completion |
| T2.4 — Capacity Planner | KF ↔ LMS Integration | 🔄 In progress |
| T3.3 — IoT Monitoring | Sensors deployment | 🧪 Testing |
| T2.3 — Supply Chain Digital Twin | Risk modelling | 🔄 Running |

---

## KPI Targets

| KPI | Target |
|---|---|
| Scrap reduction | −20% |
| Reconfiguration time reduction | −35% |
| Production lead time reduction | −50% |
| Pre-production waste reduction | −95% |

---

## ⚠️ BLOCKERE ACTIVE

> Aceste taskuri blochează progres și necesită acțiune urgentă.

| # | Task | Blocker | Owner | Status |
|---|---|---|---|---|
| B1 | Deploy AAS în Cloud (hosting) | ⚠️ Lipsă cont plătit Cloud; Eduard Lazăr deblochează | Răzvan Boița / Eduard Lazăr | ⚠️ Blocat |
| B2 | Clarificare acces server R3 (Vangelis) | ⚠️ Solicitare trimisă din 06.03; fără răspuns de la Vangelis | Paul Stanciuc | ⚠️ Blocat extern |
| B3 | Clarificare format date platforma R3 | ⚠️ Vangelis/LMS nu au specificat formatul exact | Alexandru Bejenari | ⚠️ Blocat de parteneri |
| B4 | Decizie Made2Flow (demo vs integrare reală) | ⚠️ Funcționează cu fake data; decizie de business în pending | Eduard Lazăr / Paul Stanciuc | ⚠️ Decizie pending — 🔴 P1 |

---

## 🧩 1. Product & Go-to-Market

### Definire

| Task | Owner | Prioritate | Status | Note |
|---|---|---|---|---|
| Feature set pentru lansare (MVP) | Eduard Lazăr / Paul Stanciuc | 🔴 P1 | 📋 Todo | Workshop de lansare mutat ~1 săpt; planuri Basic/Premium/Enterprise de definit |
| Ce este „Done" vs „Ready" pentru release | Eduard Lazăr / Paul Stanciuc | 🔴 P1 | 📋 Todo | Neclarificat încă |
| Decizie Made2Flow (demo vs integrare reală) | Eduard Lazăr / Paul Stanciuc | 🔴 P1 | ⚠️ Decizie pending | Funcționează cu fake data; neclar dacă merită timp de development real |

### Evaluare produse existente

| Task | Owner | Prioritate | Status | Note |
|---|---|---|---|---|
| Review arhitectură | Răzvan Boița | 🔴 P4 | 🔄 In Progress | — |
| Identificare gaps / incomplete features | Alexandru Bejenari | — | 🔄 In Progress | Gap Analysis trimis la Eduard pentru review |

### Organizare

| Task | Owner | Prioritate | Status | Note |
|---|---|---|---|---|
| Sesiune demo produse (intern) | Paul Stanciuc | 🔴 P4 | ⏭️ Next | Planificată |

### Implementare

| Task | Owner | Prioritate | Status | Note |
|---|---|---|---|---|
| Pregătire feature flags (ascundere features incomplete) | Răzvan Boița | — | 📋 Todo | Neînceput |

### Suport GTM

| Task | Owner | Prioritate | Status | Note |
|---|---|---|---|---|
| Clarificare value proposition (perspectivă tehnică) | Paul Stanciuc | 🔴 P1 | 📋 Todo | Workshop în planificare; separare funcționalități pe planuri abonament |
| Validare integrare end-to-end (expunere API Nuoform) | Răzvan Boița | — | ✅ Done | API docs finalizate via Scalar + GitHub Pages |

---

## 🏗️ 2. Arhitectură & Platformă

### Definire

| Task | Owner | Prioritate | Status | Note |
|---|---|---|---|---|
| Arhitectură multi-tenant (in place) | Eduard Modreanu | 🔴 P5 | ✅ Done | Confirmată; separare date la nivel de `org_id` emis din Keycloak |
| Separare date per client (in place) | Eduard Modreanu | 🔴 P5 | ✅ Done | Realizată prin `org_id` Keycloak; RBAC gestionat în Keycloak |

### Clarificare

| Task | Owner | Prioritate | Status | Note |
|---|---|---|---|---|
| Flow sistem (UI → AAS → backend) | Răzvan Boița | — | 📋 Todo | Necesită clarificare |
| Clarificare acces server R3 (Vangelis) | Paul Stanciuc | — | ⚠️ Blocat extern | Solicitare trimisă 06.03; fără răspuns de la Vangelis |

### Validare

| Task | Owner | Prioritate | Status | Note |
|---|---|---|---|---|
| Integrare între sisteme (Katty / LMS) | Alexandru Bejenari | — | 🔄 In Progress | Blocat acces server R3 |

### Analiză

| Task | Owner | Prioritate | Status | Note |
|---|---|---|---|---|
| Multiple tipuri AAS → standardizare | Răzvan Boița | — | 🔄 In Progress | Analiză în curs |

### Creare

| Task | Owner | Prioritate | Status | Note |
|---|---|---|---|---|
| Layout simplificat pilot (stații + flux + senzori) | Eduard Lazăr / Paul Stanciuc | — | ⏭️ Next | De livrat înainte de următoarea întâlnire cu partenerii |

---

## 🔌 3. Integrare & Development

### Integrare

| Task | Owner | Prioritate | Status | Deadline | Note |
|---|---|---|---|---|---|
| Integrare LMS (AAS extern) | Alexandru Bejenari | 🔴 P2 | 🔄 In Progress | ~1 lună | Credențiale primite 19.03; în testare; deadline ~1 lună |
| Sketch → JSON → sistem | Alexandru Bejenari | 🔴 P2 | ✅ Done | — | Există în Co-creation |

### Verificare

| Task | Owner | Prioritate | Status | Note |
|---|---|---|---|---|
| LMS specs + credentials | Alexandru Bejenari | 🔴 P2 | 🔄 In Review | Credențiale primite; în așteptare confirmare date complete |

### Finalizare

| Task | Owner | Prioritate | Status | Note |
|---|---|---|---|---|
| UI flow (parțial complet) | Alexandru Bejenari | — | 🔄 In Progress | DOD de revizuit |

### Continuare

| Task | Owner | Prioritate | Status | Note |
|---|---|---|---|---|
| Backend alignment (după modificări Răzvan) | Alexandru Bejenari | — | ⏭️ Next | Continuare după modificările lui Răzvan |

### Fixuri

| Task | Owner | Prioritate | Status | Note |
|---|---|---|---|---|
| Bug-uri identificate în sistem | Alexandru Bejenari | — | 📋 Todo | TDD de revizuit; unit/integration/regression tests necesare pe API-uri |

### Îmbunătățiri

| Task | Owner | Prioritate | Status | Note |
|---|---|---|---|---|
| Vizualizare date / UI | Alexandru Bejenari | — | 🔄 In Review | 1. date analytics (SaaS); 2. data export pentru client/tenant |

### Deploy

| Task | Owner | Prioritate | Status | Note |
|---|---|---|---|---|
| Deploy AAS în Cloud (hosting) | Răzvan Boița / Eduard Lazăr | 🔴 P2 | ⚠️ Blocat | Blocat de lipsă cont plătit Cloud; Eduard Lazăr deblochează; planificat vineri/luni |

### Clarificare

| Task | Owner | Prioritate | Status | Note |
|---|---|---|---|---|
| Clarificare format date pentru platforma R3 | Alexandru Bejenari | — | ⚠️ Blocat de parteneri | Vangelis/LMS nu au specificat formatul exact de date așteptat |
| Instalare senzor 3 (poziție cutie/flux materiale) — T3.3 | Eduard Lazăr / Julia | — | ⏭️ Next | Senzori 1+2 operaționali; senzor 3 programat săptămâna viitoare |

---

## ⚙️ 4. Proces & Tooling

### Setup

| Task | Owner | Prioritate | Status | Note |
|---|---|---|---|---|
| Board central Kanban – single source of truth | Paul Stanciuc | 🔴 P3 | 🔄 In Setup | — |

### Aliniere

| Task | Owner | Prioritate | Status | Note |
|---|---|---|---|---|
| Task-uri ↔ Work Packages (WP mapping) | Paul Stanciuc | 🔴 P3 | 📋 Todo | De aliniat |

### Organizare & Standardizare

| Task | Owner | Prioritate | Status | Note |
|---|---|---|---|---|
| Naming convention pentru task-uri (namespace per proiect) | Paul Stanciuc | — | 📋 Todo | De standardizat |
| Evitarea dublării task-urilor între tools | Paul Stanciuc | — | 📋 Todo | De standardizat |

### Implementare

| Task | Owner | Prioritate | Status | Note |
|---|---|---|---|---|
| Reprezentare Gantt (timeline / corelare temporală) | Paul Stanciuc | — | 📋 Todo | De implementat |

### Automatizare

| Task | Owner | Prioritate | Status | Note |
|---|---|---|---|---|
| GitHub Actions pentru sync task-uri | Paul Stanciuc | — | 🔄 In Review | — |
| Generare automată status / reports | Paul Stanciuc | — | 🔄 In Review | În funcție de tool ales |

---

## 🚀 5. CI/CD, Release & Quality

### Definire

| Task | Owner | Prioritate | Status | Note |
|---|---|---|---|---|
| Pipeline CI/CD (necesar pentru GTM) | Răzvan Boița | 🔴 P7 | 🔄 In Review | Analizăm simplificarea: Docker Compose vs Kubernetes/ArgoCD |

### Implementare

| Task | Owner | Prioritate | Status | Note |
|---|---|---|---|---|
| Feature flags | Răzvan Boița | 🔴 P7 | 📋 Todo | Inexistente momentan; de verificat și implementat |

### Adăugare

| Task | Owner | Prioritate | Status | Note |
|---|---|---|---|---|
| Telemetrie (monitorizare) | Răzvan Boița | — | 📋 Todo | Opțiuni: container logs / Grafana+Loki; necesar logs + tracing pe API calls |

### Validare

| Task | Owner | Prioritate | Status | Note |
|---|---|---|---|---|
| Code quality / stability înainte de release | Răzvan Boița | 🔴 P7 | 📋 Todo | De validat |

### Pregătire

| Task | Owner | Prioritate | Status | Note |
|---|---|---|---|---|
| Suport tehnic post-launch | Paul Stanciuc | — | 📋 Todo | Tool ticketing de ales; momentan doar capacitate L3 support |

---

## 🧪 6. Testing & Access

| Task | Owner | Prioritate | Status | Note |
|---|---|---|---|---|
| Acces VPN + onboarding corect | Eduard Lazăr | — | ✅ Done | Funcțional |
| Acces corect la organizații (login flow issues) | Eduard Modreanu | — | 🔄 In Progress | Corelat cu multi-tenant |
| Conectivitate sisteme externe | Alexandru Bejenari | — | 📋 Todo | Corelat cu task-ul de API |
| Testare demo produse (clienți + testeri interni) | Paul Stanciuc | — | ⏭️ Next | Clienți + testeri interni |

---

## 👥 7. Recrutare

> **Interviuri programate luni — 3 sloturi x 45 min; focus React + Node + team fit**

| Task | Owner | Prioritate | Status | Note |
|---|---|---|---|---|
| Interviuri tehnice full-stack | Eduard Lazăr | 🔴 P6 | ⏭️ Next | 3 sloturi luni 45 min; în așteptare confirmare candidați |
| Evaluare competențe React + Node | Eduard Lazăr | 🔴 P6 | ⏭️ Next | Evaluare candidați |
| Evaluare team fit (non-toxic, colaborativ) | Eduard Lazăr | 🔴 P6 | ⏭️ Next | Evaluare candidați |
| Selectare profil echilibrat (nu doar tech heavy) | Eduard Lazăr | 🔴 P6 | ⏭️ Next | Decizie finală după interviuri |

---

## 📊 8. Reporting & Planning

| Task | Owner | Prioritate | Status | Note |
|---|---|---|---|---|
| Sprint plan (tranziție către GTM) | Paul Stanciuc | — | 📋 Todo | ~20-30% efort GTM după finalizare recrutare |
| Corelare Sprint tasks ↔ Work Packages | Paul Stanciuc | — | 📋 Todo | De corelat |
| Task-uri cu timeline (start/end) | Paul Stanciuc | — | 📋 Todo | De structurat |
| Rapoarte săptămânale (nu daily) | Paul Stanciuc | — | 📋 Todo | Format de stabilit |
| Gantt / timeline pentru progres | Paul Stanciuc | — | 📋 Todo | De vizualizat |

---

## 🌐 9. Product Support

| Task | Owner | Prioritate | Status | Note |
|---|---|---|---|---|
| Landing page (claritate produs) | Alexandru Bejenari | — | 📋 Todo | De clarificat cu echipa |
| Demo / prezentare produs | Eduard Lazăr / Paul Stanciuc | — | 📋 Todo | De stabilit cu întreaga echipă |
| Definire tehnică monetizare (SaaS readiness) | Răzvan Boița | — | 📋 Todo | SaaS readiness |
| Input pentru CRM / pipeline (structură tehnică) | Eduard Lazăr / Paul Stanciuc | — | 📋 Todo | Input tehnic pentru CRM |

---

## Tasks — Sprint S2 (16 March → 03 April 2026)

> Taskuri originale din sprint, actualizate cu status real din stand-up 30.03.2026.

| Task | Assignee | Effort | Start | End | Status | Note Stand-up |
|---|---|---|---|---|---|---|
| Review LMS API endpoints and AAS structure | @tech-lead | 1d | 2026-03-16 | 2026-03-16 | ✅ Done | — |
| Technical architecture alignment for Planner integration | @tech-lead | 1d | 2026-03-17 | 2026-03-17 | ✅ Done | — |
| Define integration pipeline (KF UI → LMS Scheduler → KF UI) | @tech-lead | 1d | 2026-03-18 | 2026-03-18 | ✅ Done | — |
| Implement automatic AAS JSON export from KF platform | @backend | 2d | 2026-03-16 | 2026-03-18 | ✅ Done | — |
| Implement scheduling request endpoint (KF → LMS) | @backend | 2d | 2026-03-19 | 2026-03-21 | 🔄 In Progress | Blocat acces server R3 |
| Implement scheduler response parser | @backend | 2d | 2026-03-22 | 2026-03-24 | ⏭️ Next | — |
| Integrate scheduling results with planner UI | @frontend | 3d | 2026-03-19 | 2026-03-24 | 🔄 In Progress | Credențiale LMS primite; în testare |
| Implement planner visualization improvements (capacity / gaps) | @frontend | 2d | 2026-03-25 | 2026-03-27 | 🔄 In Progress | In review: analytics + data export |
| Validate suitability constraints and scheduling logic | @backend | 2d | 2026-03-26 | 2026-03-28 | ⏭️ Next | — |
| Run first scheduling tests with real production data | @tech-lead | 1d | 2026-03-28 | 2026-03-28 | ⏭️ Next | Blocat de integrare incompletă |
| Debug integration issues with LMS team | @tech-lead | 1d | 2026-03-31 | 2026-03-31 | ⏭️ Next | — |
| Integration validation review | @tech-lead | 0.5d | 2026-04-03 | 2026-04-03 | ⏭️ Next | — |

---

## Responsibilities Overview

### Eduard Modreanu — Tech Lead (@tech-lead)
**Responsabilități:** arhitectură · coordonare LMS · supervizare integrare · validare algoritm

| Taskuri active | Status |
|---|---|
| Arhitectură multi-tenant | ✅ Done |
| Separare date per client | ✅ Done |
| Integrare între sisteme (Katty/LMS) — supervizare | 🔄 In Progress |
| Validare acces organizații (login flow) | 🔄 In Progress |
| Debug + validare integrare LMS | ⏭️ Next (31.03 → 03.04) |

### Răzvan Boița — Backend (@backend)
**Responsabilități:** integrare backend · pipeline AAS · comunicare LMS scheduler

| Taskuri active | Status |
|---|---|
| Review arhitectură | 🔄 In Progress |
| Validare integrare end-to-end / API Nuoform | ✅ Done |
| Standardizare AAS (multiple tipuri) | 🔄 In Progress |
| Flow sistem UI → AAS → backend | 📋 Todo |
| Deploy AAS în Cloud | ⚠️ Blocat (lipsă cont plătit) |
| Pipeline CI/CD | 🔄 In Review |
| Feature flags | 📋 Todo |
| Code quality înainte de release | 📋 Todo |
| SaaS readiness / monetizare | 📋 Todo |

### Alexandru Bejenari — Frontend (@frontend)
**Responsabilități:** UI planner · vizualizare scheduling · integrare cu API-uri backend

| Taskuri active | Status |
|---|---|
| Gap analysis produs | 🔄 In Progress (la Eduard pentru review) |
| Integrare LMS (AAS extern) | 🔄 In Progress (~1 lună deadline) |
| LMS specs + credentials | 🔄 In Review |
| UI flow planner | 🔄 In Progress (DOD de revizuit) |
| Vizualizare date / analytics | 🔄 In Review |
| Backend alignment (după Răzvan) | ⏭️ Next |
| Bug-uri + TDD | 📋 Todo |
| Conectivitate sisteme externe | 📋 Todo |
| Landing page | 📋 Todo |
| Format date platforma R3 | ⚠️ Blocat de parteneri |

---

## Next Steps (Project Level)

| Prioritate | Acțiune | Responsabil | Status |
|---|---|---|---|
| 🔴 High | Deblocare cont Cloud pentru Deploy AAS | Eduard Lazăr | ⚠️ Blocat |
| 🔴 High | Răspuns Vangelis — acces server R3 + format date | Paul Stanciuc (urmărire) | ⚠️ Blocat extern |
| 🔴 High | Finalizare integrare KF ↔ LMS scheduler | Backend + Frontend | 🔄 In Progress |
| 🔴 High | Validare algoritm scheduling cu date reale | Tech Lead | ⏭️ Next |
| 🔴 High | Interviuri tehnice full-stack (luni) | Eduard Lazăr | ⏭️ Next |
| 🔴 High | Decizie Made2Flow (demo vs integrare reală) | Eduard Lazăr / Paul Stanciuc | ⚠️ Pending |
| 🟡 Medium | Integrare date senzori cu digital twins | Backend | ⏭️ Next |
| 🟡 Medium | Extindere Process Digital Twin (schimb date) | Tech Lead | 📋 Todo |
| 🟡 Medium | Workshop lansare (feature set + value prop) | Eduard / Paul | 📋 Todo (~1 săpt.) |
| 🟢 Low | Pregătire demonstrație TRL7 | Tech Lead | 📋 Todo |

---

## Milestones

| Milestone | Data | Status |
|---|---|---|
| Integration testing start | Martie 2026 | 🔄 In Progress |
| Capacity planner integration | Iunie 2026 (M42) | ⏭️ On Track |
| Pilot validation | Toamnă 2026 | 📋 Planificat |
| Project completion | Sfârșitul lui 2026 | 📋 Planificat |

---

## Summary

Pilotul Katty Fashion a implementat cu succes cea mai mare parte a **infrastructurii digitale necesare pentru R3GROUP**.

**Focus curent (Stand-up 30.03.2026):**
- 🔄 Integrarea Capacity Planner cu modelul de optimizare LMS — ultimul pas tehnic major
- ⚠️ Două blockere externe active (Cloud account + acces server R3/Vangelis)
- ⏭️ Interviuri recrutare full-stack luni
- 📋 Workshop lansare produs mutat ~1 săptămână
