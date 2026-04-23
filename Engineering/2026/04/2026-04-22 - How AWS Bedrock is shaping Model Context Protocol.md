---
title: "How AWS Bedrock is shaping Model Context Protocol"
date: 2026-04-22
source: "The New Stack"
link: "https://thenewstack.io/mcp-summit-aws-bedrock/"
categorie: "Engineering / AI Infrastructure"
action: "keep"
pertinence: 3.5
contrarian: false
vendor_bias: false
uid: "9016bc61c7ae"
tags:
  - MCP
  - AWS-Bedrock
  - Open-Source-Governance
  - Agent-Protocols
  - Cloud-Platform
  - MCP-Tasks
  - MCP-Elicitations
---

# How AWS Bedrock is shaping Model Context Protocol

| | |
|---|---|
| **Pertinence** | 3.5/5 |
| **Catégorie** | Engineering / AI Infrastructure |
| **Source** | [The New Stack](https://thenewstack.io/mcp-summit-aws-bedrock/) |

## Résumé

Interview Luca Chang (AWS Bedrock, MCP Specification Maintainer) au MCP Summit NYC. Révèle la **gouvernance open-source de MCP** : maintainers décident des évolutions par consensus, priorités multiples (trop de topics pour une réunion). **Contributions AWS = customer-driven** : Tasks et Elicitations ajoutées pour combler gaps cloud platform ↔ MCP. Chang : "contributions fall out of customer use cases, not rushed". Signal sur **architecture MCP servers** : Chang ne veut pas de servers agent-specific (risque fragmentation). **Culture** : comment Big Tech contribue utilement à l'open-source sans capturer le standard.

## Actions recommandées

- [ ] Suivre roadmap MCP officielle : Tasks et Elicitations sont-elles specs stables ou draft ?
- [ ] Analyser impact AWS contributions sur neutralité MCP (Tasks = lock-in Lambda/Step Functions ?)
- [ ] Vérifier si MCP maintainers incluent des acteurs non-US/non-BigTech (risque biais occidental)
- [ ] Documenter pattern "customer use case → protocol gap → contribution" comme best practice open-source governance
- [ ] Challenger position "no agent-specific servers" : et les servers métier verticaux (banking MCP server) ?

---

## 📝 Notes personnelles

**MCP Governance** :
- Maintainers meeting réguliers (pre-conference MCP Summit)
- Cohort suffisamment large/divers → "too many topics to fit in meeting"
- Décisions par consensus : peser problems to solve vs. smaller changes unlock creative capabilities
- **Pas de groupthink** grâce à diversité maintainers (mais quels acteurs ? article ne liste pas)

**AWS Contribution Strategy** :
- **Reactive, pas proactive** : "we don't look to make contributions as quickly as possible"
- Processus : AWS map cloud products → MCP protocol → identify gaps → contribute
- Exemples concrets : **Tasks**, **Elicitations** (ajoutés pour interaction cloud platforms)
- Citation Chang : "contributions sort of fall out of customer use cases […] once we explore a use case and see a gap in protocol itself"

**MCP Tasks & Elicitations** (à creuser) :
- **Tasks** : Probablement long-running operations (async workflows, Step Functions-like ?)
- **Elicitations** : User input collection ? (prompts structurés, forms ?)
- Gaps comblés : MCP initial = synchronous request/response, cloud workflows = async/stateful
- **Risque** : Ces extensions sont-elles AWS-flavored ou vraiment cloud-agnostic ?

**Architecture MCP Servers** :
- Chang position : "doesn't want agent-specific MCP servers"
- Raison probable : éviter fragmentation (un server par agent → interop morte)
- **Contrarian faible** : Mais verticalization utile (banking MCP server, healthcare MCP server) ?
- Tension : generic servers (interop max) vs. specialized servers (domain logic)

**Token Budget Question** :
- Article teaser : "who is paying whose token budgets!"
- Pas de réponse dans extrait (probablement dans podcast)
- **Question clé** : MCP client (agent) paie tokens LLM, mais server paie tokens tool execution ?
- Implication cost modeling : agent calls 10 MCP servers → qui paie quoi ?

**Open-Source Dynamics** :
- AWS = corporate contributor, mais ne dicte pas roadmap
- Contraste avec : OpenAI (Anthropic ?) qui a créé MCP → plus de poids naturel
- **Healthy sign** : AWS contribue gaps cloud, pas "we need MCP to work only with Bedrock"
- **À surveiller** : Ratio contributions AWS vs. Anthropic vs. community

**Questions ouvertes** :
- **Maintainers roster** : Qui sont les autres maintainers ? Google, Microsoft, Anthropic, OpenAI ?
- **Specs stability** : Tasks/Elicitations = draft proposal ou merged stable ?
- **Security governance** : MCP Authorization (OAuth profile) décidé par qui ? AWS contributed ?
- **Market demand** : Chang mentionne "where he sees most market demand for MCP servers" (dans podcast) — quel secteur ?

**Lien API Security** :
- MCP = API protocol pour agents, donc gouvernance MCP → gouvernance API agent ecosystem
- Si AWS impose Tasks/Elicitations cloud-specific → fragmente MCP → back to proprietary agent APIs
- **Implication** : Neutralité MCP governance = critical pour éviter API walled gardens

**Vendor bias** :
- The New Stack = publication indépendante (pas AWS blog)
- Interview = format neutre, pas promotional
- Mais Chang = AWS employee → naturellement pro-Bedrock
- **Impact scoring** : Aucun bias détecté (interview journalistique)

**Long-form** : 2169 chars → court, mais dense en insights gouvernance

**Pertinence finale** : 3.5/5
- Culture open-source governance utile (pattern réutilisable)
- MCP Tasks/Elicitations = signal technique faible (manque détails)
- Pas directement actionnable sécurité, mais contexte ecosystem important
- Pertinent pour comprendre qui influence MCP (AWS = contributor, pas dictator)

**Opportunité éditoriale** : Faible (trop meta, manque angle contrarian)
