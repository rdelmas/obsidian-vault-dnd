---
id: "REFERENCE-ENGINE-ADVANCED"
title: "Module Avancé — Référence Engine v5.3.2"
category: "tool"
status: "validated"
last_updated: "2026-03-19"
file_role: "reference_engine"
version: "1.0"
---

# Module Avancé — REFERENCE ENGINE (v5.3.2)

Ce module enrichit le système de références classique en ajoutant :
- gestion avancée des **scopes** (global/acte/séquence/scène/élément)
- **pondération dynamique** des influences
- **profils d'influence** (tonal/thématique/structurelle/stylistique)
- **résolution de conflits** entre références
- **sécurité anti‑plagiat renforcée**
- commandes de pilotage DM (MODE: REFERENCE ENGINE)

---
# 1) Concept général
Le moteur avancé permet d'orchestrer plusieurs inspirations à la fois, avec un contrôle fin :
- quelles inspirations s'appliquent où ?
- avec quelle intensité ?
- avec quelle priorité ?
- avec quel type d'influence ?
- que faire en cas de conflit ?

Il NE REMPLACE PAS le mode "REFERENCE FILTER" classique. Il le COMPLÈTE.

---
# 2) Scopes (portées)
Tu peux définir où une référence agit :

- **global** — influence toute la campagne / chapitre
- **acte** — influence un acte dramatique
- **séquence** — influence 1–3 scènes
- **scène** — influence locale
- **élément** — influence ciblée (PNJ / lieu / item / beat)

```markdown
Scope: "acte"
Cible: "Acte I"
Références: ["Matrix", "Arcane"]
```

---
# 3) Profils d'influence
Chaque référence peut être utilisée selon un ou plusieurs profils :

| Profil | Usage |
|--------|--------|
| **Tonal** | ambiance, couleur émotionnelle, cadence |
| **Thématique** | motifs, dualités, idées centrales |
| **Structurelle** | dynamique d'éveil, arcs, rythme narratif |
| **Stylistique** | vocabulaire, texture sensorielle |

Exemple :
```markdown
Référence: "Matrix"
Profils: ["tonal", "structurelle"]
```

---
# 4) Pondération dynamique
Le moteur peut adapter automatiquement le `weight` :
- si la sortie manque de couleur → `weight += 0.1`
- si la sortie tire trop fort sur l'œuvre → `weight -= 0.2`
- si plusieurs refs se télescopent → équilibrage automatique

Tu peux aussi verrouiller :
```markdown
Dynamic_weighting: false
```

---
# 5) Résolution de conflits (Conflict Resolver)
Quand deux références entrent en conflit :

- **HARD > SOFT**
- **HARD vs HARD** → demande d'arbitrage DM
- **SOFT vs SOFT** → mélange pondéré
- possibilité de définir une priorité manuelle

```markdown
Conflict_strategy: "auto-resolve"
Priority: ["Arcane", "Matrix"]
```

---
# 6) Sécurité anti‑plagiat intelligente
Tu peux citer des personnages/œuvres réels : Neo, Geralt, Trinity, Daenerys.

Le moteur applique :
- **inspiration archétypale autorisée**
- **interdiction stricte** de copier histoire, noms, scènes, intrigues exactes
- respect des champs `excluded`

```yaml
included:
  - "archétype de l'élu hésitant"
  - "ambiance réalité/illusion"
excluded:
  - "noms propres du film"
  - "événements exacts"
```

---
# 7) Commandes du module avancé (MODE: REFERENCE ENGINE)

## 7.1 Ajouter un profil avancé
t```text
MODE: REFERENCE ENGINE
Action: "Ajouter"
Titre: "Matrix (avancé)"
Scope: "acte"
Cible: "Acte I"
Profils: ["tonal", "structurelle"]
Influence: "SOFT"
weight: 0.8
dynamic_weighting: true
included: ["éveil", "doute identitaire", "distorsion du réel"]
excluded: ["noms propres", "intrigue exacte"]
```

## 7.2 Mise à jour
```text
MODE: REFERENCE ENGINE
Action: "Mettre à jour"
Titre: "Matrix (avancé)"
weight: 0.7
Scope: "séquence"
```

## 7.3 Désactivation
```text
MODE: REFERENCE ENGINE
Action: "Désactiver"
Titre: "Matrix (avancé)"
```

## 7.4 Priorisation
```text
MODE: REFERENCE ENGINE
Action: "Priorité"
Order: ["Arcane", "Witcher", "Matrix"]
```

---
# 8) Usage de l'engine avec PATHFINDER et SCÈNES

## 8.1 PATHFINDER
affecte :
- rythme
- tonalité
- motifs

affecte PAS :
- intrigue
- noms
- évènements prêts

## 8.2 LORE ENGINE
influence :
- couleur stylistique
n'influence jamais :
- contenu canon
- structures internes

---
# 9) Exemples avancés

## 9.1 Mélange Matrix + Arcane
```markdown
Références:
  - Matrix: profils [tonal, structurelle], weight 0.7
  - Arcane: profils [stylistique], weight 0.6
Conflict_strategy: auto-resolve
```

## 9.2 Influence ciblée (PNJ)
```markdown
Scope: "élément"
Cible: "N-1203"
Profils: ["tonal"]
Référence: "Geralt (archétype)"
```

---
# 10) Modop (Mode Opératoire)

1. **Créer/charger** les fiches de référence classiques (R-XXXX)
2. **Activer le module avancé** si tu veux mixer plusieurs refs
3. Définir le **scope** (global, acte, séquence…)
4. Définir les **profils d'influence**
5. Définir la **priorité** si plusieurs refs
6. Activer **dynamic_weighting** si besoin
7. Lancer **PATHFINDER**
8. Lancer **LORE ENGINE** (réactif seulement)
9. Ajuster les refs si saturation ou manque d'effet

---
# 11) Conclusion
Le module avancé est l'outil "expert DM" pour :
- mélanger des influences complexes
- gérer les conflits
- appliquer des styles différents selon les actes/scènes
- éviter tout risque de plagiat
- garder une narration cohérente & stylée

Il fonctionne **exclusivement sur les fiches R-XXXX existantes**, sans rien changer au format.
