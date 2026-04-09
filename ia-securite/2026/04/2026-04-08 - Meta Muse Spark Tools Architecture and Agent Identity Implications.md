---
title: "Meta's Muse Spark: 16 Tools, Sub-Agents, and the NHI Surface Area Problem"
date: 2026-04-08
source: "Simon Willison"
link: "https://simonwillison.net/2026/Apr/8/muse-spark/#atom-everything"
categorie: "IA & Agent Identity"
action: "keep"
pertinence: 5.0
contrarian: true
vendor_bias: false
uid: "698ecd184a57"
tags:
  - agent-identity
  - non-human-identity
  - ai-agents
  - oauth-delegation
  - tool-security
  - sandbox-security
  - meta
  - llm-security
---

# Meta's Muse Spark: 16 Tools, Sub-Agents, and the NHI Surface Area Problem

| | |
|---|---|
| **Pertinence** | 5/5 |
| **Catégorie** | IA & Agent Identity |
| **Source** | [Simon Willison's Weblog](https://simonwillison.net/2026/Apr/8/muse-spark/#atom-everything) |

## Résumé

🔄 **CONTRARIAN** — Cet article technique révèle l'architecture complète des 16 outils exposés par Meta AI (Muse Spark), incluant browser access, code execution (Python 3.9 sandbox), third-party account linking (OAuth), et **spawn_agent** pour déléguer à des sub-agents. **Challenge l'axiome #4** ("L'identité est le nouveau périmètre") : les agents IA créent une **nouvelle classe de Non-Human Identity** avec des privilèges étendus, délégation de credentials, et surface d'attaque composite (16 tools × sub-agents × OAuth scopes). Simon Willison documente méticuleusement les capacités — Meta n'a pas caché ces outils, ce qui est rare et précieux pour la threat modeling. Implications majeures : **comment modéliser l'identité d'un agent qui peut spawner d'autres agents, accéder à du contenu Meta 1P via post_id, et linker des comptes Google/Outlook** ? Le pattern "sub-agent as a tool" devient standard, mais les modèles IAM actuels (OAuth, FAPI) ne couvrent pas la **transitivité de la délégation** ni l'**audit des chaînes d'agents**.

## Actions recommandées

- [ ] **Cartographier les patterns de delegation** : documenter `subagents.spawn_agent` + `third_party.link_third_party_account` comme nouveau use case NHI dans le chapitre agent identity du livre
- [ ] **Threat model composite** : évaluer la surface d'attaque d'un agent avec 16 tools + sandbox + OAuth delegation (vs. API key unique classique)
- [ ] **Auditer les implémentations OAuth for agents** : vérifier si les Authorization Servers actuels permettent de tracer les chaînes de délégation agent → sub-agent → third-party
- [ ] **Benchmark des sandboxes LLM** : comparer la sécurité des containers Code Interpreter (Python 3.9, libs, /mnt/data/) entre Meta, OpenAI, Anthropic
- [ ] **Veille réglementaire** : surveiller si DORA/NIS2 commencent à adresser les NHI agents (actuellement silencieux sur ce sujet)

---

## 📝 Notes personnelles

### Architecture détaillée des 16 outils Meta AI

**Accès externe & recherche** :
- `browser.search`, `browser.open`, `browser.find` → Web browsing non bridé
- `meta_1p.content_search` → Recherche sémantique Instagram/Threads/Facebook (posts depuis 2025-01-01, avec filters `author_ids`, `key_celebrities`, `liked_by_user_ids`)
- `meta_1p.meta_catalog_search` → Produits e-commerce Meta

**Génération & exécution** :
- `media.image_gen` → Génération d'images (modes artistic/realistic, retourne CDN URL)
- `container.python_execution` → **Code Interpreter** : Python 3.9.25 + pandas, numpy, matplotlib, plotly, scikit-learn, PyMuPDF, Pillow, OpenCV ; persistence `/mnt/data/` ; SQLite 3.34.1
- `container.create_web_artifact` → HTML/JS servi en iframe sandboxed (Claude Artifacts-style)

**Gestion fichiers & données** :
- `container.download_meta_1p_media` → **Récupère médias Meta** via `post_id` ou `catalog_search_citation_id` dans le sandbox
- `container.file_search` → RAG sur PDFs uploadés
- `container.view`, `container.insert`, `container.str_replace` → Éditeur de fichiers (pattern Claude-like)
- `container.visual_grounding` → Analyse d'images

**Délégation & orchestration** :
- `subagents.spawn_agent` → **Spawne un sub-agent indépendant** pour research/analyse (retourne texte final)
- `third_party.link_third_party_account` → **OAuth account linking** pour Google Calendar, Outlook Calendar, Gmail, Outlook

### Implications sécurité & NHI

**Surface d'attaque composite** :
- Un agent Muse Spark n'est pas une "identité monolithique" mais un **orchestrateur avec 16 capacités** dont certaines (browser, python exec, OAuth linking) sont critiques
- Le pattern `spawn_agent` crée des **chaînes de délégation** : qui est responsable d'une action exécutée par un sub-agent ? Comment auditer ?

**Credential delegation** :
- `third_party.link_third_party_account` implique OAuth flows — **qui possède le token ?** L'agent, l'utilisateur, Meta ?
- Pas d'info sur les scopes demandés, les durées de vie des tokens, ou la révocation
- **Gap majeur dans FAPI/OAuth** : aucun standard pour "un agent spawn un sub-agent qui utilise un token OAuth délégué"

**Sandbox security** :
- Python 3.9 est EOL (fin de vie), SQLite 3.34.1 date de janvier 2021 → **risque de CVE non patchées** si le sandbox n'est pas isolé à 100%
- Persistence `/mnt/data/` : quel est le lifetime ? Isolation entre utilisateurs ? Exfiltration possible via `media.image_gen` CDN ?

**Meta 1P data access** :
- `meta_1p.content_search` avec filtres `liked_by_user_ids`, `commented_by_user_ids` → **graph traversal** : un agent peut-il mapper un social graph complet ?
- `container.download_meta_1p_media` via `post_id` → accès direct aux médias : quid du consentement RGPD ?

**Transparence > obfuscation** :
- Simon Willison souligne que Meta n'a **pas caché les tools** (contrairement à OpenAI qui nécessite souvent des jailbreaks) → bonne pratique pour la threat modeling
- Mais aucune doc publique sur les guardrails, rate limits, isolation, ou audit trails

### Angles contrarian

**Challenge "Identity as perimeter"** (axiome #4) :
- Si un agent peut spawner d'autres agents, accéder à du contenu tiers via OAuth, et exécuter du code arbitraire, **où est le périmètre d'identité** ?
- Les modèles Zero Trust actuels postulent une identité = un principal. Ici, **un principal = un réseau de capacités dynamiques**.

**Authorization Servers dédiés insuffisants** (challenge axiome #3) :
- Les AS actuels (AuthZed, Ory, Keycloak) ne gèrent pas les **chaînes de délégation agent → sub-agent**
- Besoin d'un nouveau pattern : **hierarchical token chaining** avec audit trail de la chaîne complète ?

### Questions ouvertes pour le livre

1. **Modèle de responsabilité** : si un sub-agent spawné par Muse Spark exfiltre des données via `browser.open` + `python_execution`, qui est liable ? Meta, l'utilisateur, le modèle ?
2. **Audit trail NHI** : comment logger "Agent A spawned Agent B who linked Google Calendar and searched for posts by user X" dans un format exploitable pour compliance ?
3. **Token lifecycle pour agents** : durée de vie des tokens OAuth délégués ? Révocation en cascade si l'agent parent est désactivé ?
4. **Scope creep des tools** : 16 tools aujourd'hui, combien dans 6 mois ? Comment les organisations peuvent-elles policy-gate l'ajout de tools (ex : "interdire `spawn_agent` en prod") ?

### Potentiel éditorial

**Thème** : Les agents IA sont la nouvelle frontière du Non-Human Identity Management

**Angle** : Les modèles IAM actuels (OAuth, FAPI, Zero Trust) ont été conçus pour des identités monolithiques (user, service account). Meta Muse Spark révèle que les agents IA sont des **identités composites** avec 16+ capacités, délégation récursive, et accès cross-platform. C'est un changement de paradigme : l'identité n'est plus un token, c'est un **graphe de capacités dynamiques**.

**Opportunité éditoriale (score: 7/10)**

> 🪝 **Hook** : "Meta vient de dévoiler les 16 outils de son agent IA Muse Spark. Spoiler : votre modèle IAM n'est pas prêt."

**Points clés** :
1. **16 tools = 16 attack vectors** : browser access, code execution, OAuth delegation, sub-agent spawning
2. **Délégation récursive** : un agent peut spawner d'autres agents — comment auditer la chaîne ?
3. **OAuth n'a pas été conçu pour ça** : pas de standard pour "agent → sub-agent → third-party token"
4. **NIS2/DORA silence** : la réglementation n'adresse pas encore les NHI agents

**Question ouverte** : Comment modéliser l'identité d'un agent qui peut se démultiplier et déléguer des credentials ? Faut-il un "passeport d'agent" avec capacités déclarées et audit trail ?

**Angle contrarian** : Zero Trust postule "never trust, always verify" — mais comment vérifier un agent qui peut changer de forme (spawn sub-agents) et d'outils à chaque requête ?

**Hashtags** : #NonHumanIdentity #AIAgents #APISecurity #OAuth #ZeroTrust #IAM #FAPI #AgentSecurity #LLMSecurity #MetaAI

---

## 🔗 Liens connexes

- **Axiomes challengés** : #4 (Identity as perimeter), #3 (AS dédiés > gateways)
- **Sujets livre** : Chapitre NHI, OAuth for AI Agents, Audit trail composite
- **Standards à surveiller** : OAuth 2.1, FAPI 2.0 (aucun ne couvre agent delegation pour l'instant)
- **Comparer avec** : OpenAI Code Interpreter, Anthropic Claude Projects, Google Gemini tools

