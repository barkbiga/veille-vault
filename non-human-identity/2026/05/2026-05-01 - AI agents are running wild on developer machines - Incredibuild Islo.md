---
title: "AI agents are running wild on developer machines. Incredibuild has a fix."
date: 2026-05-01
source: "The New Stack"
link: "https://thenewstack.io/incredibuild-ai-agents-sandbox-coding/"
categorie: "Non-Human Identity"
action: "keep"
pertinence: 5.0
contrarian: false
vendor_bias: true
uid: "dd2e88a7f895"
tags:
  - nhi
  - agent-identity
  - sandbox
  - credentials
  - governance
  - ai-agents
  - policy-enforcement
---

# AI agents are running wild on developer machines. Incredibuild has a fix.

| | |
|---|---|
| **Pertinence** | 5/5 |
| **Catégorie** | Non-Human Identity |
| **Source** | [The New Stack](https://thenewstack.io/incredibuild-ai-agents-sandbox-coding/) |

## Résumé

⚠️ **Contenu vendor** — Incredibuild lance Islo, une sandbox spécialisée pour agents IA avec isolation, credentials scoped, et governance explicite. Le constat de départ est brillant : les agents cassent le modèle "1 dev = 1 machine" → lifecycles non-humains, blast radius hérité (toutes les credentials du dev), besoin de persistence (pas d'éphémère). Architecture notable : **credential-blind** (credentials injectées à la frontière réseau, jamais dans le sandbox), choke points de policy (réseau/filesystem/audit externes au VM), persistence vs ephemeral containers. L'approche "every agent needs its own computer" est architecturalement cohérente avec le problème d'identité non-humaine : l'agent devient le principal, pas l'humain.

**Points clés pour le livre** : frameworks pour scoped credentials, séparation identity/infrastructure, policy-as-choke-point (vs policy languages), audit trail natif. Challenge implicite : si les agents sont principals, les Authorization Servers doivent-ils évoluer pour les traiter comme tels (vs service accounts dérivés) ?

## Actions recommandées

- [ ] Intégrer le pattern "credential-blind sandbox" comme référence dans le chapitre NHI du livre
- [ ] Documenter les 3 raisons pour lesquelles les agents cassent le modèle 1-dev-1-machine (lifecycle, blast radius, persistence)
- [ ] Challenger : est-ce que les AS OAuth actuels ont un modèle d'identity adapté aux agents autonomes longue durée ?
- [ ] Explorer le trade-off ephemeral vs persistent pour les workloads agent (conteneurs vs VMs)

---

## 📝 Opportunité éditoriale (score: 7/10)

**Thème** : Non-Human Identity pour AI agents
**Angle** : Les agents IA ne sont pas des "service accounts améliorés" — ils nécessitent un modèle d'identité à part entière

> 🪝 Hook : "Pourquoi laissez-vous votre laptop ouvert toute la nuit ? Parce que votre agent IA va mourir sinon. Bienvenue en 2026."

**Points clés** :
1. Le modèle "1 dev = 1 machine" est rompu (lifecycle, blast radius, persistence)
2. Les credentials scoped > credentials héritées
3. Policy-as-choke-point > policy languages complexes
4. Les agents comme principals, pas comme proxies humains

**Question ouverte** : Si un agent tourne 24/7, autonome, avec des credentials scopées — est-ce encore un "service account" ou avons-nous besoin d'un nouveau primitive d'identité ?

**Angle contrarian** : OAuth/OIDC ont été pensés pour des humains supervisés. Les agents longue durée non supervisés remettent en question les assumptions fondamentales (refresh token lifetime, consent, delegation).

**Hashtags** : #NonHumanIdentity #AIAgents #ZeroTrust #OAuth #APISecurity #DevSecOps

---

## 📝 Notes personnelles

Excellente articulation du problème. Trois insights architecturaux :

1. **Credential-blind by design** : les credentials ne vivent jamais dans le sandbox, injectées côté host à la frontière réseau. C'est du BeyondCorp pour agents — l'identité est découplée de l'environnement d'exécution.

2. **Choke points > policy languages** : au lieu de Cedar/OPA, enforcement à des points fixes (gateway réseau, filesystem boundary, audit log). Plus simple à raisonner, plus difficile à contourner.

3. **Agent-as-principal** : "every agent needs its own computer" = chaque agent est un principal avec son propre contexte d'identité. Pas un service account emprunté.

**Lien avec FAPI/OAuth** : FAPI assume des clients supervisés (user present). Un agent qui tourne en continu sans humain dans la boucle casse le modèle de consent/delegation. Les refresh tokens ont des lifetimes pensées pour des sessions humaines.

**Question pour le livre** : Faut-il un "FAPI for Agents" ? Ou les agents doivent-ils utiliser client credentials + token exchange (RFC 8693) avec des scopes ultra-granulaires ?

**Trade-off notable** : VM persistente vs container éphémère. Islo choisit la VM (services qui tournent, caches chauds). Mais coût/complexité vs stateless. Dépend du use case (agent build vs agent monitoring).

**Bias check** : c'est un article vendor (Incredibuild), mais le problème articulé est réel et l'architecture proposée est cohérente. Pas de bullshit marketing, focus technique.
