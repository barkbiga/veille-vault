---
title: "MiCA: Why Entity Identification Is Now a Compliance Cornerstone"
date: 2026-04-17
source: "Finextra"
link: "https://www.finextra.com/blogposting/31450/mica-why-entity-identification-is-now-a-compliance-cornerstone"
categorie: "Reglementation"
action: "keep"
pertinence: 3.5
contrarian: false
vendor_bias: false
uid: "78df673bce90"
tags:
  - MiCA
  - LEI
  - EU-regulation
  - crypto-assets
  - entity-identification
  - compliance
---

# MiCA: Why Entity Identification Is Now a Compliance Cornerstone

| | |
|---|---|
| **Pertinence** | 3.5/5 |
| **Catégorie** | Réglementation / EU |
| **Source** | [Finextra](https://www.finextra.com/blogposting/31450/mica-why-entity-identification-is-now-a-compliance-cornerstone) |

## Résumé

⚠️ **Contenu partiel** (extraction limitée) — MiCA (Markets in Crypto-Assets Regulation), le règlement européen de référence sur les crypto-actifs, passe de la théorie à l'application. Le **Legal Entity Identifier (LEI)** devient un pilier de conformité. Le LEI est un identifiant global unique pour les entités juridiques (ISO 17442), utilisé dans les rapports financiers. Son intégration à MiCA signifie que les CASPs (Crypto-Asset Service Providers) devront identifier formellement leurs contreparties institutionnelles. **Implication** : gouvernance renforcée, traçabilité des transactions inter-entités, alignement avec les standards de reporting financier traditionnel (EMIR, MiFID II).

Convergence réglementation crypto ← finance traditionnelle. LEI = équivalent organisationnel du KYC individuel.

## Actions recommandées

- [ ] **Gouvernance API** : Si APIs exposées à des CASPs (banques avec activité crypto), anticiper obligation LEI dans metadata des transactions
- [ ] Vérifier si les standards FAPI intègrent LEI comme claim optionnel/requis dans les access tokens (contexte open banking + crypto)
- [ ] **Livre** : Mentionner MiCA + LEI dans chapitre gouvernance — exemple de réglementation forçant entity identification au niveau API/protocol layer
- [ ] Surveiller guidance ESMA/EBA sur implémentation technique LEI dans APIs crypto (probable Q2-Q3 2026)

---
## 📝 Notes personnelles

**Extraction limitée** : article Finextra probablement derrière soft paywall ou protection. RSS donne seulement teaser.

**Contexte MiCA** :
- Entrée en vigueur progressive 2024-2026
- Régule exchanges, custodians, stablecoins, etc.
- Équivalent EU du BitLicense US mais harmonisé UE

**LEI (Legal Entity Identifier)** :
- ISO 17442, géré par Global LEI Foundation (GLEIF)
- Déjà obligatoire pour rapports EMIR (dérivés), MiFID II (marchés financiers)
- Format : 20 caractères alphanumériques (ex: 529900T8BM49AURSDO55)

**Implications techniques** :
1. **API Design** : ajouter champ `lei` dans request/response pour transactions institutionnelles
2. **Validation** : appel API GLEIF pour vérifier validité LEI (rate limits, caching)
3. **Access Control** : scoper les permissions par LEI (institution A ne voit que ses transactions)

**Lien avec OAuth/FAPI** :
- FAPI déjà utilisé pour open banking (DSP2)
- MiCA + open banking crypto → probable extension claims JWT :
  ```json
  {
    "sub": "user@example.com",
    "org_id": "529900T8BM49AURSDO55",  // LEI
    "lei_verified": true,
    "lei_verified_at": "2026-04-15T10:00:00Z"
  }
  ```

**Contrarian potentiel** :
Crypto = "décentralisation", mais MiCA force centralisation via LEI (identité organisationnelle centralisée). Tension philosophique.

**Score pertinence** : 3.5/5
- Réglementation EU pertinente : +3
- Contenu partiel : pas de bonus long-form
- Gouvernance API directement impactée : +0.5
