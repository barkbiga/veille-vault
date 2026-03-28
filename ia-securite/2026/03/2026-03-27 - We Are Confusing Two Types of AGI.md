---
title: "We Are Confusing Two Types of AGI"
date: 2026-03-27
source: "Daniel Miessler"
link: "https://danielmiessler.com/blog/two-types-of-agi?utm_source=rss&utm_medium=feed&utm_campaign=website"
categorie: "IA & Sécurité"
action: "keep"
pertinence: 3.5
contrarian: false
vendor_bias: false
uid: "2967a5e15afd"
tags:
  - AGI
  - AI-agents
  - NHI
  - economie
  - workforce
  - automation
  - knowledge-workers
---

# We Are Confusing Two Types of AGI

| | |
|---|---|
| **Pertinence** | 3.5/5 |
| **Catégorie** | IA & Sécurité |
| **Source** | [Daniel Miessler](https://danielmiessler.com/blog/two-types-of-agi?utm_source=rss&utm_medium=feed&utm_campaign=website) |

## Résumé

Daniel Miessler distingue **Soft AGI** (émulation suffisante pour remplacer knowledge workers, impact économique) vs **Hard AGI** (généralisation apprentissage au sens CS académique). Argue que le débat AGI confond les deux : l'industrie vise Soft AGI (Labor → labor interne, $50T workforce global), et ça arrivera 2026-2027 sous forme de "produits" qui s'onboardent comme humains, prennent instructions, shippent résultats, 160h/semaine. **Pertinent pour NHI** : ces agents = nouvelles identités non-humaines massives, avec credentials, accès APIs, droits. Moins technique/archi que culturel, mais contextualise pourquoi NHI devient critique.

## Actions recommandées

- [ ] **Livre - Intro NHI** : utiliser distinction Soft/Hard AGI pour expliquer pourquoi NHI urgent (Soft AGI = déploiement massif identités agents 2026-27)
- [ ] **Threat model** : agent-as-employee = surface attack (compromission credential agent, privilege escalation, persistent access 24/7)
- [ ] **LinkedIn post** : "Soft AGI is coming in 2026. Are your IAM systems ready for 10,000 non-human employees?"
- [ ] **Veille économique** : monitorer annonces produits "AI employee" (Anthropic, OpenAI, startups) pour timeline validation

---
## 📝 Opportunité éditoriale (score: 6/10)

**Thème** : Soft AGI et explosion identités non-humaines
**Angle** : IAM/NHI pas prêt pour vague "AI employees" 2026-27

> 🪝 Hook : "En 2027, votre entreprise aura peut-être 10 000 'employés IA'. Qui gère leurs credentials ? Qui audit leurs accès ? Qui révoque quand un agent est compromis ?"

**Points clés** :
1. Soft AGI (émulation suffisante) ≠ Hard AGI (vraie généralisation) 
2. L'industrie vise Soft, et ça arrive 2026-27
3. "Onboard like human" = identité, credentials, accès APIs/systèmes
4. 160h/semaine, jamais malade, jamais démission = nouveau modèle threat
5. IAM legacy pas conçu pour scale 1:100 human-to-agent ratio

**Question ouverte** : "Votre IAM peut-il gérer 10x plus d'identités en 18 mois ? Vos politiques Zero Trust distinguent-elles humains et agents ? Vos logs d'audit sont-ils dimensionnés ?"

**Angle contrarian** : "On débat si AGI = sentience. Pendant ce temps, 10 000 bots vont s'authentifier sur vos APIs avec des service accounts mal gouvernés."

**Hashtags** : #NHI #NonHumanIdentity #AIAgents #SoftAGI #IAM #ZeroTrust #APISecurity

---
## 📝 Notes personnelles

**Lien livre NHI :**
- Perfect timing : justifie pourquoi NHI urgent (Soft AGI deployment imminent)
- Agent identity = sous-ensemble NHI, mais avec nouveau pattern : "employee-like" vs "service account-like"

**Implications archi :**
- OAuth for agents : scope "act as employee" ?
- Delegation chains : agent agit au nom de qui ? Lui-même ? Manager humain ?
- Audit : distinguer actions humain vs agent (new claim ?)
- Revocation : agent compromis = revoke all child sessions/tokens ?

**Tension avec axiomes :**
Neutre sur axiomes, mais renforce #4 ("identité = nouveau périmètre") : si agents = employees, l'identité devient encore + critique.

**Timeline à valider :**
Miessler prédit 2026-27 pour produits Soft AGI. Surveiller :
- OpenAI "Operator" évolution
- Anthropic Claude agents
- Startups "AI workforce" (ex: 11x, Lindy, etc.)

**Questions ouvertes :**
- Protocol OAuth/OIDC suffit pour agents, ou faut-il extensions (RFC draft "OAuth for Autonomous Agents") ?
- Agent credentials : short-lived tokens vs long-lived API keys ? Rotation auto ?
- MFA pour agents : comment ? Attestation TPM/secure enclave ?
