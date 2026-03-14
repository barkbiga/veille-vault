---
title: "NanoClaw and Docker team up to isolate AI agents inside MicroVM sandboxes"
date: 2026-03-13
source: "The New Stack"
link: "https://thenewstack.io/nanoclaw-docker-sandboxes-ai-agents/"
categorie: "Sécurité IA"
action: "keep"
pertinence: 5.0
contrarian: true
vendor_bias: false
uid: "3572fecb1723"
tags:
  - AIAgents
  - NHI
  - MicroVM
  - Isolation
  - DefenseInDepth
  - OpenClaw
  - Docker
  - Firecracker
  - BlastRadius
---

# NanoClaw and Docker team up to isolate AI agents inside MicroVM sandboxes

| | |
|---|---|
| **Pertinence** | 5/5 |
| **Catégorie** | Sécurité IA |
| **Source** | [The New Stack](https://thenewstack.io/nanoclaw-docker-sandboxes-ai-agents/) |

## Résumé

🔄 **CONTRARIAN** — Critique frontale d'OpenClaw (runtime AI agent populaire) pour sa "sécurité abyssale". NanoClaw (alternative open-source, minimal attack surface) s'intègre avec Docker Sandboxes (MicroVMs dédiées) pour isoler chaque agent IA dans son propre noyau + Docker daemon. **Architecture : assume agents are malicious** → defense in depth à 2 couches (container + MicroVM). Si un agent fait un container escape ou exploit une 0-day, le blast radius reste confiné au MicroVM. **Principe clé** : ne jamais mettre secrets/credentials dans l'environnement agent, enforcer sécurité *outside the agentic surface*. Pattern émergent : containers = trusted automation, MicroVMs = untrusted AI code.

## Actions recommandées

- [ ] **URGENT** : Auditer les déploiements actuels d'agents IA (coding assistants, automation) — tournent-ils sur host ou en isolation ?
- [ ] Intégrer ce pattern MicroVM dans le chapitre NHI du livre : agent identity ≠ developer identity, blast radius control
- [ ] Évaluer Firecracker/Kata Containers vs. Docker Sandboxes pour runtime agent en prod (AWS Lambda Firecracker = proven at scale)
- [ ] Challenger les API gateways : peuvent-ils router vers des backends MicroVM-isolated pour les requêtes générées par agents ?
- [ ] Documenter la matrice d'isolation : User → Service Account → Agent (3 niveaux d'identité, 3 périmètres de confiance)

---

## 📝 Opportunité éditoriale (score: 9/10)

**Thème** : Agent Identity & Blast Radius Control
**Angle** : "Les agents IA ne sont pas des utilisateurs — ce sont des menaces internes potentielles"

> 🪝 Hook : "Votre équipe utilise des coding agents pour automatiser les déploiements. Mais si un agent hallucine et exécute `rm -rf /`, combien de systèmes tombent ? Un ? Dix ? Toute l'infra ?"

**Points clés** :
1. OpenClaw = hype sans sécurité (assume trust, pas d'isolation)
2. NanoClaw + MicroVM = defense in depth : container escape → still sandboxed in VM
3. **Principe architectural** : "If a hallucination can cause a security issue, the security model is broken"

**Question ouverte** : Les API gateways traditionnels (Kong, Apigee, AWS API Gateway) ont-ils un modèle d'isolation pour les requêtes générées par agents ? Ou traitent-ils agent traffic = user traffic ?

**Angle contrarian** : "Stop treating AI agents like users. They're untrusted code execution engines that need the same isolation as third-party plugins or WASM modules."

**Hashtags** : #AIAgents #NHI #MicroVM #ZeroTrust #BlastRadius #DefenseInDepth #Firecracker

---

## 📝 Notes personnelles

**Architecture défensive** :
- Layer 1 : Container (isole l'agent des autres agents)
- Layer 2 : MicroVM (isole le container du host + kernel séparé)
- Credentials : **jamais** dans l'env agent → API externe avec least-privilege token

**Pattern émergent** :
Containers (Docker classique) = trusted internal automation
MicroVMs (Firecracker, Kata, Sandboxes) = untrusted AI/third-party code

**Lien avec AXIOME #4 (L'identité est le nouveau périmètre)** :
CHALLENGE partiel : L'identité ne suffit pas si l'identité elle-même est malveillante ou compromise (agent hallucination). Le périmètre devient **identité + blast radius control**. L'isolation doit être *en plus* de l'authentification, pas à la place.

**Analogie NHI** :
- Service account (machine identity) → assume trusted behavior
- AI agent identity → assume **untrusted** behavior, enforce isolation
→ Nouvelle classe d'identité : **Non-Human Untrusted Identity** (NHUI ?)

**Technologies sous-jacentes** :
- Firecracker (AWS Lambda, utilisé massivement en prod)
- Kata Containers (CNCF, isolation VM pour Kubernetes)
- Docker Sandboxes (expérimental, macOS/Windows d'abord, Linux bientôt)

**Critique finale de l'article** :
"Critics have noted that sandboxing alone is insufficient for 'agent safety'. They emphasize the need for fine-grained authentication an[d]..." — article coupé, mais pointe vers le besoin de **AuthZ granulaire** en plus de l'isolation. C'est le lien avec OAuth/GNAP pour agents.

**À creuser** :
- NanoClaw codebase (GitHub, audit sécurité ?)
- OpenClaw security model (ou absence de)
- Docker Sandboxes roadmap Linux
- Firecracker vs. gVisor vs. Kata : trade-offs perf/sécu
