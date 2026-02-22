---
title: "Beyond the vibe code: The steep mountain MCP must climb to reach production"
date: 2026-02-21
source: "The New Stack"
link: "https://thenewstack.io/model-context-protocol-evolution/"
categorie: "Architecture"
action: keep
pertinence: 4.5
contrarian: true
vendor_bias: false
uid: "https://thenewstack.io/model-context-protocol-evolution/"
tags:
  - MCP
  - AI Agents
  - Non-Human Identity
  - API Security
  - Agentic AI
---

# Beyond the vibe code: The steep mountain MCP must climb to reach production

| | |
|---|---|
| **Pertinence** | 4.5/5 |
| **Catégorie** | Architecture |
| **Source** | [The New Stack](https://thenewstack.io/model-context-protocol-evolution/) |

## Résumé
🔄 CONTRARIAN — Le Model Context Protocol (MCP) suscite un engouement intense dans les cercles dev, mais cet article argumente que sa route vers la production est semée d'embûches majeures : absence de standards d'authentification robustes pour les agents, problèmes de gouvernance inter-opérateurs, et manque de primitives de sécurité formelles. L'auteur challenge l'hypothèse que MCP deviendra rapidement le standard universel d'interopérabilité agentique. Pour les architectes bancaires/santé, cela remet directement en question la tentation de standardiser sur MCP sans attendre la maturité sécuritaire. La dimension NHI (Non-Human Identity) est centrale : comment authentifier un agent MCP appelant une API réglementée ?

## Actions recommandées
- [ ] Cartographier les gaps sécurité MCP vs exigences FAPI 2.0 pour les cas d'usage open banking agentique
- [ ] Évaluer si les Authorization Servers existants (Keycloak, ForgeRock, etc.) supportent les flows MCP sans contournement
- [ ] Définir une politique interne : MCP autorisé uniquement en sandbox jusqu'à stabilisation du spec d'authn
- [ ] Suivre l'évolution du groupe de travail IETF/OpenID sur l'identité des agents IA

---
## 📝 Notes personnelles
