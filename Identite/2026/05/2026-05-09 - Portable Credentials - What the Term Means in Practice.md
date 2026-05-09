---
title: "Portable Credentials: What the Term Means in Practice"
date: 2026-05-09
source: "Spruce ID"
link: "https://blog.spruceid.com/interoperability-portable-credentials-what-the-term-means-in-practice/"
categorie: "Identité"
action: "keep"
pertinence: 4.5
contrarian: false
vendor_bias: true
uid: "138e3ac68fe5"
tags:
  - verifiable-credentials
  - portable-identity
  - interoperability
  - W3C-VC
  - ISO-18013-5
  - mobile-driver-license
  - federation
  - trust-framework
  - cross-jurisdiction
---

# Portable Credentials: What the Term Means in Practice

| | |
|---|---|
| **Pertinence** | 4.5/5 |
| **Catégorie** | Identité |
| **Source** | [Spruce ID](https://blog.spruceid.com/interoperability-portable-credentials-what-the-term-means-in-practice/) |

## Résumé

⚠️ Contenu vendor — Spruce ID est un acteur du marché des verifiable credentials.

**Définition critique de la portabilité** : capacité à utiliser un credential numérique vérifiable **across systems, jurisdictions, wallets, and contexts** sans compromettre sa validité ni nécessiter d'intégrations custom pour chaque nouveau cas d'usage.

**Insight clé** : la portabilité n'est PAS l'interopérabilité technique SEULE. Elle nécessite **3 couches simultanées** :
1. **Interopérabilité technique** (standards ouverts : ISO 18013-5, W3C VC)
2. **Mutual recognition** (accord juridique/politique entre juridictions)
3. **Trust framework** (gouvernance de l'acceptation cross-juridiction)

**Gap fondamental identifié** : un État peut adopter des standards ouverts (interopérabilité technique) MAIS sans politique de mutual recognition, les vérificateurs d'autres juridictions n'ont aucune base pour accepter ces credentials. Inversement, deux juridictions peuvent signer un accord de reconnaissance mutuelle, mais sans formats compatibles, l'accord n'a aucun mécanisme pour fonctionner en pratique.

**3 scénarios concrets analysés** :
- **Mobilité résidentielle** : resident déménage vers nouvel État → doit re-établir identité même avec credentials valides de l'État précédent. Solution : ISO 18013-5 ou W3C VC permettent lecture/vérification par tout système built to same standard + framework de mutual recognition.
- **Licences professionnelles cross-state** : infirmière, ingénieur relocalisé → période de re-examen et re-licensing. Verifiable credentials ne résolvent PAS seules, mais créent l'infrastructure pour rendre les compact agreements et mutual recognition **fonctionnels**.
- **Navigation multi-programmes gouvernementaux** : bénéficiaire d'assistance logement + Medicaid + nutrition benefits → ne devrait pas re-établir identité/éligibilité pour chaque agence. Portable credential = issued once, verifiable across programs, avec contrôle resident sur ce qui est partagé.

**Architecture technique mentionnée** : ISO 18013-5 pour mobile driver's licenses, W3C Verifiable Credentials comme formats largement adoptés. Emphasis sur le fait que la portabilité ne peut pas être "added after the fact" — c'est un outcome que standards techniques ET policy frameworks doivent supporter ensemble.

## Actions recommandées

- [ ] **Reviewer les specs ISO 18013-5** et leur adoption pour mobile driver's licenses dans contexte Open Banking/SCA — parallèle avec FAPI pour federation bancaire
- [ ] **Analyser le gap portabilité dans l'écosystème CIAM bancaire européen** — est-ce que les verifiable credentials W3C sont sur la roadmap DSP3/eIDAS 2.0 ?
- [ ] **Intégrer dans le livre section NHI** : la portabilité des credentials machines (service accounts, API keys) suit-elle les mêmes patterns ? Ou bien mutual recognition n'existe pas pour NHI ?
- [ ] **Use case banque/assurance** : credentials portables pour professionnels (courtiers, agents généraux) qui naviguent entre plusieurs plateformes/assureurs — quel framework de trust aujourd'hui ?

---

## 📝 Opportunité éditoriale (score: 7/10)

**Thème** : La portabilité des credentials numériques — pourquoi l'interopérabilité technique ne suffit pas

**Angle** : L'article met en lumière un malentendu fondamental dans l'industrie : beaucoup pensent que l'adoption de standards ouverts (W3C VC, ISO 18013-5) = portabilité automatique. **FAUX**. Sans layer de mutual recognition (politique/juridique), on a juste de l'interopérabilité technique sans acceptance.

> 🪝 Hook : "Votre mobile driver's license fonctionne dans 5 États différents. Pourquoi vos credentials API bancaires ne fonctionnent-ils pas entre 2 business units de la même banque ?"

**Points clés** :
1. Portabilité = interopérabilité technique + mutual recognition + trust framework (3 layers, pas 1)
2. ISO 18013-5 et W3C VC sont nécessaires mais non suffisants
3. Les scénarios B2C (citizen mobility) et B2B (occupational licensing) exposent les mêmes gaps architecturaux que les APIs bancaires

**Question ouverte** : Dans le monde API/IAM, qui joue le rôle d'orchestrateur du "mutual recognition framework" ? Les API Gateways ? Les Authorization Servers ? Les federations comme GAIN ?

**Angle contrarian** : "Zero Trust suppose que l'identité est le nouveau périmètre. Mais si vos credentials ne sont pas **portables** cross-systems, vous avez juste créé des silos d'identité. Zero Trust devient Zero Portability."

**Hashtags** : #VerifiableCredentials #DigitalIdentity #ZeroTrust #APIGateway #IAM #TrustFramework #eIDAS #OpenBanking

---

## 📝 Notes personnelles

**Lien FAPI/Open Banking** : ISO 18013-5 pour mobile DL = équivalent de FAPI pour banking APIs. Les deux nécessitent interop technique + mutual recognition. Différence : FAPI a une governance (OIDF, regional profiles UK/Australia/Brazil). ISO 18013-5 pour DL a-t-elle un équivalent ? Article ne mentionne pas.

**Gap NHI** : L'article parle de credentials **humains** (nurse, resident, benefits recipient). Quid des credentials **machines** ? Service accounts, API keys, agent credentials n'ont PAS de framework de mutual recognition. Chaque org invente sa propre solution. C'est un chaos architectural.

**Potential challenge axiome #1** : "Zero Trust est le bon modèle pour les APIs bancaires" — cet article suggère qu'un modèle Zero Trust sans portable credentials = prolifération de silos d'identité. Si chaque API Gateway/Authorization Server devient une île, on n'a pas fait Zero Trust, on a fait Zero Federation.

**Vendor bias** : Spruce ID vend des solutions de verifiable credentials. L'article est bien écrit et informatif, mais pousse naturellement vers l'adoption de W3C VC et nécessité de trust frameworks (ce qui est leur business). Néanmoins, l'analyse du gap interopérabilité/mutual recognition est solide et non-marketing.

**Question livre** : Comment les **AI agents** vont-ils gérer des credentials portables ? Un agent OAuth2 qui opère pour le compte d'un user A doit-il pouvoir "porter" les credentials de A vers un service B sans re-authentication ? Ou bien chaque service B doit-il re-valider ? Cela rejoint le débat delegation vs. impersonation dans OAuth.
