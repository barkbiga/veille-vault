---
title: "MCP Is Making API Sprawl Worse"
date: 2026-05-05
source: "Nordic APIs"
link: "https://nordicapis.com/mcp-is-making-api-sprawl-worse/"
categorie: "API Security"
action: "keep"
pertinence: 5
contrarian: true
vendor_bias: true
uid: "b519e056db1b"
tags:
  - API-Governance
  - MCP
  - API-Sprawl
  - AI-Agents
  - Zero-Trust
  - DevSecOps
---

# MCP Is Making API Sprawl Worse

| | |
|---|---|
| **Pertinence** | 5/5 |
| **Catégorie** | API Security / Gouvernance |
| **Source** | [Nordic APIs](https://nordicapis.com/mcp-is-making-api-sprawl-worse/) |

## Résumé

🔄 **CONTRARIAN** — ⚠️ **Contenu vendor (Axway)** — Le Model Context Protocol (MCP) amplifie le problème d'API sprawl au lieu de le résoudre. Rogier van Boxtel (Axway) présente des données alarmantes : 80% des décideurs ne savent pas combien d'APIs ils ont (VansonBourne), 55% gèrent >500 APIs, 57% ont subi une brèche API dans les 2 dernières années (Traceable 2025). L'abstraction MCP crée une nouvelle couche d'aveuglement où la gouvernance devient encore plus difficile. Le débat REST vs MCP vs JSON-RPC (Kelsey Hightower) masque le problème de fond : **sans gouvernance stricte, chaque nouvelle couche d'abstraction multiplie la surface d'attaque**. L'anecdote Shell montre que la simple visibilité forcée (rapports + réunions) incite les développeurs à rollback des APIs avant examen.

**Challenge l'axiome** : "Zero Trust est le bon modèle" → Zero Trust suppose la visibilité complète du périmètre. Si 80% des organisations ne connaissent pas leur inventaire API, le socle même de Zero Trust s'effondre. MCP aggrave ce problème.

## Actions recommandées

- [ ] **Audit immédiat** : inventaire exhaustif de toutes les APIs (internes, externes, MCP-wrapped) avant tout déploiement d'agents IA
- [ ] **Gouvernance préventive** : obligation de déclaration pré-déploiement pour toute API exposée à MCP/agents (modèle Shell)
- [ ] **Threat model MCP** : analyser comment MCP modifie la surface d'attaque des APIs existantes (bypass traditionnel API gateway?)
- [ ] **Chapitre livre NHI** : section "MCP et credential sprawl" — les agents MCP créent-ils de nouvelles identités machine non gouvernées?
- [ ] **Veille JSON-RPC** : suivre le débat Hightower — alternative crédible ou fausse piste?

---

## 📝 Opportunité éditoriale (score: 8/10)

**Thème** : La couche d'abstraction qui a tué la visibilité

**Angle** : Pendant que tout le monde débat REST vs MCP, personne ne parle du vrai problème : on ne peut pas sécuriser ce qu'on ne voit pas.

> 🪝 **Hook** : "80% des entreprises ne savent pas combien d'APIs elles ont. Et maintenant, elles ajoutent MCP par-dessus. C'est comme installer un système d'alarme dans une maison dont on ignore le nombre de portes."

**Points clés** :
1. API sprawl n'est pas un problème de "trop d'APIs" mais de **perte de visibilité**
2. MCP ajoute une couche d'indirection qui rend la gouvernance encore plus difficile
3. Zero Trust repose sur la connaissance exhaustive du périmètre — impossible avec 80% d'inventaires incomplets
4. La solution Shell : **visibilité forcée = accountability = réduction volontaire**

**Question ouverte** : Si nous ne pouvons pas gouverner nos APIs aujourd'hui, comment gouvernerons-nous des milliers d'agents IA qui les appellent demain?

**Angle contrarian** : "MCP n'est pas la prochaine révolution API — c'est le prochain cauchemar de gouvernance."

**Hashtags** : #APISecurity #ZeroTrust #MCP #APIGovernance #AIAgents #DevSecOps

---

## 📊 Données clés

- **80%** des décideurs ne savent pas combien d'APIs ils ont (VansonBourne)
- **55%** gèrent plus de 500 APIs (Traceable 2025)
- **54%** citent la prévention du sprawl comme défi #1
- **57%** ont subi au moins une brèche API dans les 2 dernières années
- **67%** adoptent activement l'IA générative (= nouvelle surface d'attaque)

## Architecture et trade-offs

**Le problème structurel** :
```
Couche 1 : APIs (déjà non inventoriées)
Couche 2 : API Gateways (coverage partielle)
Couche 3 : MCP (nouvelle abstraction)
Couche 4 : AI Agents (consommateurs autonomes)
```

Chaque couche multiplie l'aveuglement. L'approche traditionnelle (catalog centralisé) échoue dès qu'on dépasse quelques dizaines d'APIs.

**Trade-off central** : Agilité DevOps vs Gouvernance centralisée
- MCP promet de faciliter l'intégration AI ↔ API (agilité++)
- Mais chaque nouveau "tool" MCP = nouvelle API non gouvernée (gouvernance--)

**Piste optimiste** : Les agents IA eux-mêmes pourraient monitorer et enforcer la gouvernance à l'échelle. Mais cela suppose... qu'on sache déjà ce qu'on gouverne (chicken & egg).

## Liens avec NIS2 / DORA

- **DORA ICT Risk Management** : l'inventaire exhaustif des assets critiques est obligatoire. Une banque qui ne connaît pas ses APIs viole DORA.
- **NIS2 Supply Chain** : chaque API = point d'interconnexion. MCP = nouvelle supply chain à cartographier.

## Questions ouvertes

1. Les API Gateways actuels peuvent-ils découvrir automatiquement les APIs MCP-wrapped?
2. OAuth/OIDC pour agents MCP : qui est le resource owner? Le user ou l'agent?
3. Le débat JSON-RPC vs REST vs MCP détourne-t-il l'attention du vrai sujet (gouvernance)?

---

## 📝 Notes personnelles

**Insight fort** : Le cas Shell est brillant. La simple menace de "devoir expliquer ton API en réunion" = mécanisme de gouvernance sociale plus efficace que les policies techniques. Applicable aux NHI?

**Lien livre** : Chapitre "Agent Identity Crisis" — MCP crée de facto des identités machine (chaque tool = credential). C'est du NHI non gouverné.

**Contrarian view** : Et si le vrai problème n'était pas MCP mais l'incapacité chronique à faire de la gouvernance API? MCP révèle un problème préexistant, il ne le crée pas.

