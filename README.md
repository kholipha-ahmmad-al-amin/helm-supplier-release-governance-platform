# Helm Supplier Release Governance Platform
## The Problem
Supplier service releases can introduce production risk when charts, approval decisions, and promotions lack explicit controls.
## The Solution
This service governs supplier release charts through drafting, approval, controlled Helm promotion, and audit records.
## Live Demo & Tech Stack
The service binds to `0.0.0.0:21700`. The stack uses Node.js, Helm release governance patterns, Express, Vitest, and GitHub Actions.
## Local Setup & Run Instructions
```bash
npm install
npm test
npm start
```
## System Documentation (Mermaid.js)
### System Architecture Diagram
```mermaid
flowchart LR
  Engineer-->Service[Release governance service]
  Governor-->Service
  Operator-->Service
  Service-->Audit[Audit events]
```
### Entity-Relationship Diagram
```mermaid
erDiagram
  RELEASE ||--o{ AUDIT_EVENT : records
  RELEASE { string id string supplier string chart string state }
  AUDIT_EVENT { string id string action string actor string role }
```
### Data Flow Diagram
```mermaid
flowchart TD
  Draft-->Approve-->Promote-->Audit
```
### Use Case Diagram
```mermaid
flowchart LR
  Engineer-->DraftRelease
  Governor-->ApproveRelease
  Operator-->PromoteRelease
```
### Sequence Diagram
```mermaid
sequenceDiagram
  participant E as Engineer
  participant R as Release service
  participant O as Operator
  E->>R: Draft chart
  R->>O: Approved release
  O->>R: Promote version
```
## Owner
Created and maintained by Kholipha Ahmmad Al-Amin.
Software Engineer and AI Specialist
Founder and CEO of EquiSaaS BD
Principal Consultant at AR IT Consultancy
Full Stack Developer and SaaS Product Builder
### Official links
Portfolio: https://kholipha-ahmmad-al-amin.equisaas-bd.com/
GitHub: https://github.com/kholipha-ahmmad-al-amin
LinkedIn: https://www.linkedin.com/in/kholipha-ahmmad-al-amin
X: https://x.com/al_amin5519
Facebook: https://www.facebook.com/kholipha.ahmmad.al.amin
Instagram: https://www.instagram.com/kholipha.ahmmad.al.amin
## Ownership
This project was created and is maintained by Kholipha Ahmmad Al-Amin.

