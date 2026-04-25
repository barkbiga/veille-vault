---
title: "The People Do Not Yearn for Automation"
date: 2026-04-24
source: "The Verge (via Simon Willison)"
link: "https://simonwillison.net/2026/Apr/24/the-people-do-not-yearn-for-automation/"
categorie: "Culture"
action: "borderline"
pertinence: 2.5
contrarian: true
vendor_bias: false
uid: "90c05539f3d2"
tags:
  - ai-ethics
  - automation
  - software-brain
  - human-factors
  - adoption
  - contrarian
---

# The People Do Not Yearn for Automation

| | |
|---|---|
| **Pertinence** | 2.5/5 |
| **Catégorie** | Culture |
| **Source** | [The Verge via Simon Willison](https://simonwillison.net/2026/Apr/24/the-people-do-not-yearn-for-automation/) |

## Résumé

🔄 **CONTRARIAN** — Nilay Patel (The Verge) explore pourquoi l'IA reste impopulaire auprès du grand public malgré l'explosion des usages de ChatGPT. Sa thèse : le "software brain" (voir le monde comme une série de flux à automatiser) crée un fossé avec le reste de la population. **L'erreur fondamentale** : croire que tout peut être modélisé en base de données, que toute tâche humaine aspire à l'automatisation. Citation clé : "Not everything is a loop. The entire human experience cannot be captured in a database. That's the limit of software brain. That's why people hate AI. It *flattens* them." Même l'exemple du smart home échoue : Apple/Google/Amazon ont échoué à convaincre le grand public après une décennie d'efforts.

## Actions recommandées

- [ ] **Challenger la roadmap "AI agents everywhere"** : avant d'automatiser un processus métier avec des agents IA, vérifier que les utilisateurs *veulent* cette automatisation (ne pas projeter son software brain)
- [ ] **Sécurité des agents IA** : si les agents IA sont déployés malgré une adoption faible, le risque est un usage "shadow" (contournement, credential sharing) → anticiper les patterns de résistance
- [ ] **NHI governance** : les agents doivent avoir des identités claires et révocables, mais **visibles/compréhensibles pour les humains** (pas juste des UUIDs techniques) → UX de la confiance

---

## 📝 Notes personnelles

### Anti-biais mental pour les architectes

Cette pièce est un **rappel salutaire** pour quiconque conçoit des systèmes : **le fait que quelque chose *puisse* être automatisé ne signifie pas qu'il *doit* l'être, ni que les utilisateurs le *veulent*.**

Les architectes sécurité (moi inclus) ont tendance à raisonner en "flows", "states", "authentication/authorization chains". C'est utile. Mais ça crée un angle mort : **on oublie que les humains ne veulent pas toujours d'efficience maximale**. Parfois, ils veulent :
- De la friction (pour réfléchir, pour contrôler)
- De l'opacité partielle (pour garder de l'autonomie)
- De l'inefficacité (parce que le processus *lui-même* a de la valeur sociale/symbolique)

### Lien avec Zero Trust et API Security

**Implication directe** : si on déploie des agents IA avec OAuth delegation (l'agent agit pour le compte de l'utilisateur), et que l'utilisateur ne *fait pas confiance* à l'agent, il va :
1. **Refuser le consentement** → l'agent ne fonctionne pas
2. **Partager ses credentials directement** (pire) → contournement du flow OAuth, explosion du risque
3. **Créer des workarounds** → shadow IT, shadow AI

**Donc** : la gouvernance NHI ne peut pas être purement technique. Elle doit intégrer une **couche de légitimité perçue** : l'utilisateur doit comprendre *pourquoi* l'agent existe, *ce qu'il peut faire*, *comment le révoquer*.

### Pattern : "Automation fatigue"

Patel décrit un phénomène que j'ai observé dans la banque/assurance : **l'automation fatigue**. Après des années de "digital transformation", les clients *et* les employés sont saturés de chatbots qui ne comprennent rien, de portails qui plantent, de "self-service" qui prend 3x plus de temps qu'un appel téléphonique.

Résultat : **résistance passive** aux nouvelles automatisations, même quand elles sont bien conçues.

**Implications pour les APIs** :
- Les APIs internes (pour agents IA, RPA, intégrations) doivent être **opt-in** et **révocables**
- Les APIs externes (open banking, DSP3) doivent avoir des **consent flows ultra-clairs** (pas de dark patterns)
- Les Authorization Servers doivent logguer et exposer *qui* (humain ou agent) a consenti à *quoi* → audit trail humainement lisible

### Contrarian angle : Et si le Zero Trust était... trop automatisé ?

Le Zero Trust repose sur l'idée de **vérification continue, automatique, invisible**. Mais si Patel a raison, une partie des utilisateurs *veulent* voir et contrôler ces vérifications. Ils ne veulent pas d'une "boîte noire" qui décide silencieusement s'ils ont accès ou non.

**Question ouverte** : doit-on créer des "friction points intentionnels" dans les flows Zero Trust pour donner aux utilisateurs un sentiment de contrôle ? Exemple : afficher un dashboard "Votre score de confiance actuel est X/100 basé sur : device, location, behavior" → transparence, pas seulement efficience.

### Ce que ça ne remet PAS en question

Cet article ne dit pas que l'automatisation est mauvaise. Il dit qu'elle est **surestimée comme objectif universel**. Pour les systèmes critiques (finance, santé, infra), l'automatisation reste essentielle pour :
- Réduire l'erreur humaine
- Scaler la défense (threat detection)
- Répondre en temps réel (fraud prevention)

Mais il faut arrêter de la vendre comme un *bénéfice utilisateur intrinsèque*. C'est un bénéfice *organisationnel* (coûts, scale). L'utilisateur, lui, veut souvent autre chose : **fiabilité, compréhension, contrôle**.

---

## 📝 Opportunité éditoriale (score: 7/10)

**Thème** : Le Zero Trust doit rester humainement gouvernable, pas seulement automatisé

**Angle** : L'automatisation sans légitimité perçue crée de la résistance, du contournement, du shadow IT. Le Zero Trust ne peut pas être une boîte noire — il doit être **auditable, compréhensible, révocable** par les humains qu'il protège.

> 🪝 Hook : "On automatise tout : la détection, la réponse, l'authentification. Mais si les utilisateurs ne font pas confiance à l'automation, ils la contournent. Et là, c'est la catastrophe."

**Points clés** :
1. Le "software brain" crée un angle mort : on oublie que les humains ne veulent pas *toujours* d'efficience maximale
2. Les agents IA avec OAuth delegation = risque de credential sharing si l'utilisateur ne fait pas confiance
3. Zero Trust doit être **transparent** : qui a accès, pourquoi, comment révoquer — pas juste invisible et "efficient"
4. Exemple : un dashboard "trust score" visible par l'utilisateur vs. une décision silencieuse en backend

**Question ouverte** : Vos utilisateurs comprennent-ils *pourquoi* ils sont bloqués ou autorisés ? Ou est-ce qu'ils voient juste "Access Denied" et appellent le support ?

**Angle contrarian** : "Le Zero Trust sans gouvernance humaine n'est pas du Zero Trust. C'est du Security Theater automatisé."

**Hashtags** : #ZeroTrust #AIethics #HumanFactors #NHI #Governance #SecurityUX #TrustButVerify
