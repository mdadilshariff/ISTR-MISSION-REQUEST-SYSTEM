# ISTR — Intergalactic Space Travel Request System

![Platform](https://img.shields.io/badge/platform-ServiceNow-1e3a8a?style=flat-square)
![Type](https://img.shields.io/badge/type-Scoped%20Application-2563eb?style=flat-square)
![Status](https://img.shields.io/badge/status-Complete-4ade80?style=flat-square)
![License](https://img.shields.io/badge/license-Academic%20Project-64748b?style=flat-square)

> A ServiceNow scoped application that automates the full lifecycle of intergalactic mission requests — submission, multi-level approval, notifications, and reporting — replacing manual, email-based coordination with a single auditable workflow.

**[View the interactive project showcase →](./ISTR_README.html)**
**[Read the full project report (PDF) →](docs/ISTR_Final_Project_Report.pdf)** &nbsp;·&nbsp; **[Live demo →](#)**

---

## Overview

Mission requesters (scientists, astronauts, research officers) submit travel requests through a guided Service Catalog form. Each request is routed through a three-stage approval chain — **Manager → Finance Officer → Mission Control** — with automated notifications, role-based access control, and real-time reporting at every step.

Built entirely on native ServiceNow capabilities. No external services, no separate backend.

## Features

- **Mission Request Management** — create, edit, cancel, and track requests via a Service Catalog Record Producer
- **Multi-level Approval Workflow** — orchestrated with Flow Designer (Manager → Finance → Mission Control → Scheduled → Completed → Closed)
- **Role-Based Security** — 10 ACLs enforced across 5 roles and groups
- **Dynamic Forms** — UI Policies and Client Scripts (e.g. Diplomatic Officer field appears only for Alien Negotiation missions)
- **Automated Notifications** — email alerts on submission, approval, rejection, and completion
- **Reporting & Analytics** — Mission Status, Approval Summary, Risk Analysis, and Monthly Request reports, plus a Performance Analytics dashboard

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Service Portal, Service Catalog |
| Automation | Flow Designer, Business Rules, Client Scripts, UI Policies |
| Database | ServiceNow Custom Table (`x_2065295_istr_i_space_travel_request`, extends `Task`) |
| Security | ACLs, Roles, Groups |
| Notifications | Email Engine |
| Reporting | ServiceNow Reports, Performance Analytics |
| Hosting | ServiceNow SaaS (Personal Developer Instance) |

## Architecture

```
Mission Requester
      ↓
Service Catalog (Mission Request Form)
      ↓
Business Rules  →  Custom Table (x_2065295_istr_i_space_travel_request)
      ↓
Flow Designer  →  Manager → Finance → Mission Control
      ↓
Notifications  →  Dashboard / Reports
```

Full architecture, ER diagram, and security model are documented in the [Solution Architecture](#) report.

## Data Model

**Table:** `x_2065295_istr_i_space_travel_request` (extends `Task`)

Key fields: Mission Name · Mission Type · Destination Planet · Travel Date · Return Date · Risk Level · Mission Description · Crew Members · Budget · Manager · Finance Officer · Mission Control Officer · Diplomatic Officer · Mission Status · Approval Status · Attachments

## Roles & Groups

| Role | Group |
|---|---|
| Mission Requester | Mission Requesters |
| Manager | Managers |
| Finance Officer | Finance Team |
| Mission Control | Mission Control Team |
| System Administrator | System Administrators |

## Project Planning

Delivered across 3 sprints using Agile/Scrum estimation (12 user stories, Fibonacci story points):

| Sprint | Focus | Story Points |
|---|---|---|
| Sprint 1 | Mission Request Management, Manager & Finance Approval | 13 |
| Sprint 2 | Mission Control Approval, Security & Access Control, Dynamic Forms | 10 |
| Sprint 3 | Notifications, Dashboard, Reports | 11 |

**Total: 34 story points · Velocity ≈ 11.3 SP/sprint**

## Testing

- ✅ Functional & performance testing (9 test cases — form validation, workflow routing, ACL enforcement, notification delivery, load/response time)
- ✅ User Acceptance Testing (6 test cases, 2 bugs found and resolved)
- ✅ Catalog item, UI Policy, Client Script, Business Rules, Flow, ACLs, Reports, Dashboard, and Notifications all verified on the Personal Developer Instance

See the See the [Functional & Performance Testing](docs/GenAI_Functional_Performance_Testing_ISTR.pdf) and [UAT](docs/User_Acceptance_Testing_ISTR.pdf) reports for full detail.

## Documentation

This repository's full documentation set covers the entire project lifecycle:

- Brainstorming & Empathy Map
- Customer Journey Map & Problem–Solution Fit
- Proposed Solution & Solution Architecture
- Project Planning Phase (backlog, sprints, burndown)
- Functional & Performance Testing / UAT
- Final consolidated Project Report

## Future Scope

- AI-based mission risk prediction
- Predictive approval timelines
- Native mobile application
- Voice-assisted request submission
- Integration with external space agencies
- Live mission tracking & AI chatbot support

## Author

**MD.ADIL SHARIFF** — B.Tech, Computer Science Engineering (AI & ML)

---

<sub>Built on ServiceNow App Engine Studio · 2026</sub>
