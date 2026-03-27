---
title: "OpenTelemetry Adoption: A Strategic Blueprint"
date: 2026-03-27
source: "BankInfoSecurity"
link: "https://www.bankinfosecurity.com/blogs/opentelemetry-adoption-strategic-blueprint-p-4064"
categorie: "Architecture"
action: borderline
pertinence: 2.5
contrarian: false
vendor_bias: false
uid: "https://www.bankinfosecurity.com/blogs/opentelemetry-adoption-strategic-blueprint-p-4064"
tags:
  - opentelemetry
  - observabilite
  - architecture
  - API-security
  - DORA
---

# OpenTelemetry Adoption: A Strategic Blueprint

| | |
|---|---|
| **Pertinence** | 2.5/5 |
| **Catégorie** | Architecture |
| **Source** | [BankInfoSecurity](https://www.bankinfosecurity.com/blogs/opentelemetry-adoption-strategic-blueprint-p-4064) |

## Résumé
Blueprint pratique pour l'adoption d'OpenTelemetry avec une architecture collector-first. L'article propose une migration par phases combinant edge design, gateway et instrumentation hybride. La pertinence pour le contexte financier réglementé est indirecte mais réelle : DORA impose des capacités de logging et de détection d'incidents ICT — OTel est un standard de fait pour outiller cette obligation. La connexion avec la sécurité API (traces distribuées cross-services) et l'observabilité des agents IA (tracer les appels NHI/MCP) est un signal faible intéressant. 🌱 SIGNAL FAIBLE

↔️ Engineering → API Security — L'observabilité OTel des flux API peut alimenter une détection d'anomalies comportementales sur les identités non-humaines

## Actions recommandées
- [ ] Évaluer OTel comme couche d'observabilité pour les API gateways dans un contexte DORA
- [ ] Explorer le potentiel de traces OTel pour détecter les dérives de comportement des agents IA (NHI)

---
## Notes personnelles
