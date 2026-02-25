---
title: "How to Handle JSON Web Tokens (JWTs) in Agentic AI"
date: 2026-02-25
source: "Nordic APIs"
link: "https://nordicapis.com/how-to-handle-json-web-tokens-jwts-in-agentic-ai/"
categorie: "API"
action: keep
pertinence: 5.0
contrarian: false
vendor_bias: false
uid: "https://nordicapis.com/how-to-handle-json-web-tokens-jwts-in-agentic-ai/"
tags:
  - jwt
  - agentic-ai
  - nhi
  - oauth
  - api-security
  - non-human-identity
---

# How to Handle JSON Web Tokens (JWTs) in Agentic AI

| | |
|---|---|
| **Pertinence** | 5/5 |
| **Catégorie** | API / NHI |
| **Source** | [Nordic APIs](https://nordicapis.com/how-to-handle-json-web-tokens-jwts-in-agentic-ai/) |

## Résumé
L'article adresse la problématique centrale des JWT dans un contexte d'agents IA autonomes : propagation d'identité inter-agents, durée de vie des tokens, chaînes de délégation et risques d'élévation de privilèges non intentionnelle. La question de **qui est le principal** dans une chaîne agent→sous-agent→API est directement liée aux patterns FAPI 2.0 et OAuth 2.0 Token Exchange (RFC 8693). L'article met en lumière que les conventions JWT traditionnelles (audience fixe, scopes larges) sont inadaptées aux workflows agentiques multi-hop. Le sujet est au cœur de la thématique "Securing APIs in the Age of AI Agents" et des enjeux NHI en banque/assurance.

## Actions recommandées
- [ ] Évaluer l'applicabilité de RFC 8693 (Token Exchange) pour la délégation inter-agents dans les architectures open banking
- [ ] Vérifier si les Authorization Servers en place supportent le `act` claim et le `may_act` claim pour les chaînes de délégation agentiques
- [ ] Intégrer les patterns JWT agentiques dans le chapitre NHI du livre "Securing APIs in the Age of AI Agents"
- [ ] Tester la réduction des scopes JWT au minimum par agent (principe de moindre privilège NHI)
- [ ] Documenter les risques de token replay dans les workflows agentiques asynchrones

---
## 📝 Notes personnelles
<!-- Relier à FAPI 2.0 Message Signing pour traçabilité des appels inter-agents. Angle contrarian possible : les JWT sont-ils le bon format pour NHI agentique, ou faut-il des credentials éphémères type SPIFFE/SVID ? -->