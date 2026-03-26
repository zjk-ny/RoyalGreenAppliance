<div align="center">
  <img src="https://d12rh965z7jvqw.cloudfront.net/images/HSECOMMNY-RG/image/catalog/2026-01-27-23-51-44-ny-rg-224b4e0c-fbdb-11f0-8ed2-0eeaf36f30d9.png" alt="Royal Green Logo" width="350"/>
  
  <h2>IT Infrastructure & Automation Overview</h2>
  <p><b>High-level architectural topology for enterprise digital routing, e-commerce middleware, and zero-trust mesh.</b></p>
  
  <img src="https://img.shields.io/badge/Status-Online-brightgreen?style=flat-square" />
  <img src="https://img.shields.io/badge/Architecture-Zero_Trust-0052D9?style=flat-square" />
  <img src="https://img.shields.io/badge/Edge_Security-WAF_Enabled-F38020?style=flat-square" />
</div>

<hr>

## 🏗️ System Topology

This diagram provides a sanitized, high-level overview of our multi-tenant mesh, demonstrating how edge processing securely integrates with our core data lakes.

```mermaid
graph TD
    %% Clean, Corporate Styling
    classDef default fill:#ffffff,stroke:#d1d5db,stroke-width:1px,color:#111827,font-family:sans-serif;
    classDef edge fill:#f0f9ff,stroke:#0284c7,stroke-width:2px,color:#0369a1,font-family:sans-serif;
    classDef core fill:#f0fdf4,stroke:#16a34a,stroke-width:2px,color:#15803d,font-family:sans-serif;
    classDef data fill:#fefce8,stroke:#ca8a04,stroke-width:2px,color:#a16207,font-family:sans-serif;

    subgraph INGRESS ["[ Edge Routing & Ingress ]"]
        DNS["Global DNS Routing"]:::edge
        WAF["Edge Security & WAF"]:::edge
        FORMS["Dynamic Customer Portals"]:::edge
        VOICE["Automated Voice Intake"]:::edge
        
        DNS --> WAF
        WAF --> FORMS
        WAF --> VOICE
    end

    subgraph AUTOMATION ["[ Intranet Mesh & Automation ]"]
        IAM["Enterprise IAM Gateway"]:::core
        AUTO["Business Logic Automation Engine"]:::core
        SMTP["Transactional Email Relay"]:::core
        FULFILL["Fulfillment Routing Node"]:::core

        IAM --> AUTO
        AUTO --> SMTP
        SMTP --> FULFILL
    end

    subgraph ERP ["[ ERP & Middleware Data Lake ]"]
        ECOMM["E-Comm Gateway"]:::data
        WEBHOOK["Asynchronous Webhooks"]:::data
        API["Internal API Bridge"]:::data
        POS["Central Retail POS Core"]:::data

        ECOMM --> API
        WEBHOOK --> API
        API --> POS
    end

    %% Cross-Mesh Routing
    FORMS -- "Sanitized JSON Payload" --> AUTO
    VOICE -- "State Sync" --> WEBHOOK
    AUTO -- "Zero-Trust Bridge" --> API
```

## 📖 Directory Index

* **`/assets`** — Approved branding and static UI components.
* **`/automations`** — Workflow logic templates and configurations.
* **`/web`** — E-commerce UI components and portal configurations.
