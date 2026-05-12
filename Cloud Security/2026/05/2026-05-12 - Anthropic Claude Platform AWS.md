---
title: "Anthropic's Claude Platform Comes to AWS"
date: 2026-05-12
source: "The New Stack"
link: "https://thenewstack.io/anthropics-claude-platform-comes-to-aws/"
categorie: "Cloud Security"
action: "keep"
pertinence: 3.5
contrarian: false
vendor_bias: false
uid: "f3b91a2c4d78"
tags:
  - anthropic
  - aws
  - compliance
  - data-residency
  - agent-platform
  - nhi
  - supply-chain
---

# Anthropic's Claude Platform Comes to AWS

| | |
|---|---|
| **Pertinence** | 3.5/5 |
| **Catégorie** | Cloud Security |
| **Source** | [The New Stack](https://thenewstack.io/anthropics-claude-platform-comes-to-aws/) |

## Résumé

Anthropic annonce l'**intégration de sa plateforme Claude directement dans AWS** (au-delà de Bedrock), permettant aux clients de **déployer des agents IA dans leurs propres VPCs AWS sans que les données quittent leur boundary**. Argument commercial principal : **compliance-first architecture** (data residency, HIPAA, FedRAMP, RGPD). Les entreprises peuvent utiliser **Claude API + tool calling + agent runtime** tout en gardant les données sensibles confinées dans leur cloud. Annonce également **Agent SDK for AWS** avec intégrations natives S3, Lambda, DynamoDB. **Implication NHI** : chaque agent devient un service account AWS avec IAM role et policies dédiées → gouvernance des identités machine. **Signal faible** : la course au compliance entre fournisseurs d'IA générative (OpenAI Azure, Google Cloud AI, maintenant Anthropic AWS) indique que les régulateurs pèsent lourd dans l'adoption enterprise.

## Actions recommandées

- [ ] **Cartographier les use cases agents IA** où la data residency est bloquante (santé, banque, secteur public)
- [ ] **Évaluer l'architecture VPC-bound** : quels gains de compliance vs. complexité opérationnelle (réseau, monitoring, costs) ?
- [ ] **Auditer les IAM roles pour agents** : définir des policies minimales (principe de moindre privilège) pour agents accédant S3, DynamoDB, APIs internes
- [ ] **Challenger le vendor lock-in** : déployer Claude dans AWS VPC = dépendance AWS + Anthropic. Plan de sortie ?
- [ ] **Documenter les exigences réglementaires** : DORA, DSP3, HDS (santé), SecNumCloud (ANSSI) → vérifier si VPC-bound suffit ou si des contrôles supplémentaires sont requis
- [ ] **Prototyper un agent AWS-native** : Lambda function → appelle Claude API (VPC) → accède DynamoDB → retourne résultat. Mesurer latence, coût, observabilité.

---

## 📝 Notes personnelles

**Architecture proposée** :
```
[User] → [API Gateway] → [Lambda (agent runtime)] 
         → [Claude API in VPC] → [S3/DynamoDB/RDS]
         ↓
    [IAM Role Agent_XYZ]
    Policies: S3:Read bucket_clients, DynamoDB:Query table_transactions
```

**Compliance wins** :
- **Data residency** : données ne quittent jamais la région AWS
- **Audit trail** : CloudTrail logs toutes les API calls (agent → Claude, agent → S3)
- **Encryption** : at-rest (KMS) + in-transit (TLS)
- **RBAC** : IAM policies définissent exactement ce que chaque agent peut faire

**Challenges** :
- **Coût** : VPC endpoints, data transfer, Lambda invocations, Claude API calls (facturation au token)
- **Observabilité** : comment monitorer les agents ? Logs structurés, traces distribuées (X-Ray) ?
- **Gouvernance NHI** : explosion du nombre de service accounts (1 agent = 1 IAM role). Comment auditer ?
- **Vendor lock-in** : architecture AWS-native → migration vers autre cloud = réécriture

**Lien avec le livre** :
- Chapter potentiel : "Agent Identity in Cloud Environments"
- Pattern : agent = non-human identity avec credentials éphémères (IAM role assumed via STS)
- Contraste avec API keys : IAM roles = short-lived tokens, auto-rotation, least privilege by design

**Questions ouvertes** :
- **Interop multi-cloud** : peut-on déployer le même agent sur AWS, Azure, GCP ? Standards manquants.
- **Agent-to-agent trust** : si agent A (AWS) appelle agent B (Azure), comment gérer la chaîne de confiance ?
- **Revocation** : comment révoquer instantanément les permissions d'un agent compromis ? IAM policies propagation = secondes à minutes.

**Comparaison OpenAI Azure** :
- OpenAI sur Azure = similaire (data residency, private endpoints)
- Différence : Anthropic met l'accent sur tool calling + agent SDK natif AWS (OpenAI = plus généraliste)

**Signal faible** :
- La bataille se joue sur la compliance, pas sur la performance du modèle
- Indica que les RSSI/DPO ont un droit de veto sur l'adoption de l'IA générative
- Les fournisseurs s'alignent sur les exigences réglementaires européennes (RGPD, DORA, NIS2)

