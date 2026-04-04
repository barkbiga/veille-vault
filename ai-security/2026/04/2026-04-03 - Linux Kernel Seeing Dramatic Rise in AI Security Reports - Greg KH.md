---
title: "Linux Kernel Seeing Dramatic Rise in AI Security Reports - Greg Kroah-Hartman"
date: 2026-04-03
source: "Simon Willison (via Greg Kroah-Hartman)"
link: "https://simonwillison.net/2026/Apr/3/greg-kroah-hartman/#atom-everything"
categorie: "ai-security"
action: "keep"
pertinence: 4.5
contrarian: false
vendor_bias: false
uid: "simonwillison-2026-04-03-greg-kh-kernel"
tags:
  - ai-agents
  - linux-kernel
  - vulnerability-reports
  - open-source-security
  - maintainer-perspective
---

# Linux Kernel Seeing Dramatic Rise in AI Security Reports - Greg Kroah-Hartman

| | |
|---|---|
| **Pertinence** | 4.5/5 🔥 |
| **Catégorie** | AI Security / Maintainer Perspective |
| **Source** | [Simon Willison](https://simonwillison.net/2026/Apr/3/greg-kroah-hartman/#atom-everything) |

## Résumé

**Greg Kroah-Hartman (mainteneur Linux kernel stable)** confirme la tendance : *"We too are seeing this, it's going to be interesting."*

**Contexte kernel Linux** :
- Plus grande codebase open-source critique (30M+ lignes)
- Surface d'attaque énorme : drivers, syscalls, networking, filesystems, KVM, etc.
- Chaque vuln kernel = impact sur des milliards de devices (serveurs, Android, IoT, cloud)

**Pourquoi "interesting" ?** :
1. **Volume** : si HAProxy (petit projet) voit × 20-30, le kernel pourrait voir × 100+
2. **Complexité du triage** : le kernel a déjà un process de CVE controversé (beaucoup de noise)
3. **Impact supply chain** : kernel vulns affectent TOUS les layers au-dessus (containers, VMs, orchestrators)
4. **Défense** : le kernel team va devoir outiller le triage (agents défensifs)

**Convergence finale** : 4e témoignage de maintainers majeurs (HAProxy, cURL, kernel, + implicit consensus). La thèse Ptacek est **validée empiriquement**.

## Actions recommandées

- [ ] **Infrastructure teams** : accélérer les cycles de patching kernel (live patching, kpatch, automation)
- [ ] Suivre les CVE kernel avec un filtre "high exploitability" (pas tous les CVE kernel ne méritent panic)
- [ ] Pour les architectures cloud/containers : évaluer les mitigations kernel-level (seccomp, LSM, eBPF)
- [ ] Réfléchir au modèle de responsabilité : qui est responsable du patching dans un modèle "serverless" ?
- [ ] Veille sur les outils émergents : quels agents défensifs pour le triage kernel ?

---
## 📝 Notes personnelles

**Greg KH** : L'un des top 5 contributeurs kernel au monde, responsable du stable tree. Son avis fait autorité.

**Ton "it's going to be interesting"** : Laconique, mais chargé de sens. GKH sait que le kernel team va devoir évoluer rapidement pour gérer le flood.

**Implication cloud/containers** :
- Les hyperviseurs (KVM) sont dans le kernel → vuln kernel = escape VM
- Les namespaces/cgroups (containers) sont dans le kernel → vuln kernel = escape container
- **Zero Trust assume breach** : si le kernel est breach, tous les contrôles user-space (auth, policy enforcement) peuvent être bypassés

**Lien avec API Security** :
- Les API gateways, Authorization Servers, etc. tournent sur des kernels
- Une vuln kernel exploitée = exfiltration tokens, clés, secrets
- **Defense-in-depth critique** : vault-based tokenization, HSM, TPM deviennent encore plus importants

**Question NHI** : Les agents qui scannent le kernel sont des NHI. Si un agent découvre une 0-day kernel et décide de l'exploiter au lieu de la reporter, qui est responsable ? Le propriétaire de l'agent ? Le fournisseur du LLM ? Nouvelle frontière juridique.

**Pour le livre** : Ajouter un encadré "The Kernel as Ultimate Trust Anchor" dans le chapitre Zero Trust — même avec ZT parfait, le kernel reste un SPOF. Les agents IA vont le cibler massivement.
