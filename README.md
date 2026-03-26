<div align="center">
  <img src="https://d12rh965z7jvqw.cloudfront.net/images/HSECOMMNY-RG/image/catalog/2026-01-27-23-51-44-ny-rg-224b4e0c-fbdb-11f0-8ed2-0eeaf36f30d9.png" alt="Royal Green Logo" width="350"/>
  
  <h2>IT Infrastructure & Automation Core</h2>
  <p><b>Centralized repository for digital routing, e-commerce middleware, and zero-trust mesh architecture.</b></p>
  
  <img src="https://img.shields.io/badge/Power_Automate-Active-0078D4?style=flat-square&logo=powerautomate&logoColor=white" />
  <img src="https://img.shields.io/badge/Azure_AD-Secured-0052D9?style=flat-square&logo=microsoftazure&logoColor=white" />
  <img src="https://img.shields.io/badge/Cloudflare-WAF_Enabled-F38020?style=flat-square&logo=cloudflare&logoColor=white" />
  <img src="https://img.shields.io/badge/Uptime-99.99%25-brightgreen?style=flat-square" />
</div>

<hr>

## 🏗️ System Topology

Our infrastructure operates on a tightly integrated multi-tenant mesh, routing cognitive edge processing directly into our ERP data lakes.

```mermaid
graph TD
    %% Clean, Corporate Styling
    classDef default fill:#ffffff,stroke:#d1d5db,stroke-width:1px,color:#111827,font-family:sans-serif;
    classDef edge fill:#f0f9ff,stroke:#0284c7,stroke-width:2px,color:#0369a1,font-family:sans-serif;
    classDef core fill:#f0fdf4,stroke:#16a34a,stroke-width:2px,color:#15803d,font-family:sans-serif;
    classDef data fill:#fefce8,stroke:#ca8a04,stroke-width:2px,color:#a16207,font-family:sans-serif;

    subgraph INGRESS ["[ Edge Routing & Ingress ]"]
        DNS["Multi-Zone DNS Fleet"]:::edge
        WAF["Cloudflare Web Ingress / WAF"]:::edge
        QR["Dynamic QR Matrix / Jotform"]:::edge
        VOICE["Cognitive Voice Node"]:::edge
        
        DNS --> WAF
        WAF --> QR
        WAF --> VOICE
    end

    subgraph AUTOMATION ["[ Intranet Mesh & Automation ]"]
        AAD["Azure AD Security Gateway"]:::core
        PAM["Power Automate Core Engine"]:::core
        SMTP["SMTP Relay Sink"]:::core
        FULFILL["Fulfillment Routing Node"]:::core

        AAD --> PAM
        PAM --> SMTP
        SMTP --> FULFILL
    end

    subgraph ERP ["[ ERP & Middleware Data Lake ]"]
        ECOMM["Nationwide E-Comm Gateway"]:::data
        WEBHOOK["Asynchronous Webhooks"]:::data
        API["Custom API Bridge"]:::data
        POS["HomeSource POS Core"]:::data

        ECOMM --> API
        WEBHOOK --> API
        API --> POS
    end

    %% Cross-Mesh Routing
    QR -- "JSON Payload" --> PAM
    VOICE -- "State Sync" --> WEBHOOK
    PAM -- "Zero-Trust Bridge" --> API
```

## 📖 Directory Index

* **`/assets`** — Approved branding and static UI components.
* **`/automations`** — Power Automate workflow templates and JSON configurations.
* **`/web`** — E-commerce UI components and Jotform portal configurations.
