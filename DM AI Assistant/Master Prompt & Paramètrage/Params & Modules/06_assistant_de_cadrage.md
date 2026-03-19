---
id: "ASSISTANT-CADRAGE"
title: "Assistant de Cadrage — Start / Destination / Constraints"
category: "tool"
status: "validated"
last_updated: "2026-03-19"
file_role: "cadrage_tool"
version: "1.1"
---

# Assistant de Cadrage (Storyweaver)

Cet assistant t'aide à **formuler rapidement** :
- **START** (point de départ)
- **DESTINATION** (objectif majeur)
- **CONSTRAINTS** (must_include, must_avoid, themes, tone, risk)
- et un **beats_target** pertinent pour PATHFINDER.

> ⚠️ **Quand l'utiliser ?** Après **✅ BOOT OK** et **dans une session active** (après `SESSION START`).  
> 🎯 **À quoi il sert ?** Préparer le bloc attendu par **`MODE: DRAMATURGIE — PATHFINDER`**.  
> 🧭 **Où l'utiliser ?** Tu réponds au questionnaire **dans la conversation**, pas dans Obsidian.

---
## A. Questionnaire express (90 secondes)
1) **Promesse initiale** (1 phrase) :
2) **Héro·ïne·s au centre** (noms ou rôles génériques) :
3) **Enjeu immédiat** (ce qui presse) :
4) **Obstacle principal** (naturel / social / surnaturel / moral ?) :
5) **Récompense / Changement d'état attendu** :
6) **Tonalité** (calme / tendu / cathartique / mix) :
7) **Risque** (faible / moyen / élevé) :
8) **Thèmes** (3 mots‑clés) :
9) **À inclure** (2 éléments concrets) :
10) **À éviter** (2 éléments) :

> Astuces :
> - Une phrase courte vaut mieux qu'un paragraphe.
> - Les *must_include* et *must_avoid* guident finement PATHFINDER sans le brider.

---
## B. Gabarit de remplissage (prêt à coller)
> Colle ce bloc **tel quel** dans la conversation juste après tes réponses au questionnaire.

```markdown
## START — Point de départ
<1 phrase>

## DESTINATION — Objectif majeur
<1 phrase>

## ROUTE ACTIVE (Start → Destination)
start: "<START résumé>"
destination: "<DESTINATION résumé>"
scope: "court|moyen|long"
beats_target: 5
constraints:
  must_include: ["<élément_1>","<élément_2>"]
  must_avoid: ["<éviter_1>","<éviter_2>"]
  themes: ["<thème_1>","<thème_2>","<thème_3>"]
  tone: "<calme|tendu|cathartique|mix>"
  risk: "<faible|moyen|élevé>"
```

---
## C. Prompts rapides (à envoyer à Storyweaver)

### 1) Générer PATHFINDER (passe #1)
```text
MODE: DRAMATURGIE — PATHFINDER
Start: "<...>"
Destination: "<...>"
scope: moyen
beats_target: 5
constraints:
  must_include: ["<...>"]
  must_avoid: ["<...>"]
  themes: ["<...>"]
  tone: "<...>"
  risk: "<...>"
```

### 2) Affiner (UPDATE) les 2–3 beats suivants
```text
MODE: DRAMATURGIE — PATHFINDER (UPDATE)
Focus: Beats #2–#3
Ajustements: ["augmenter tension sociale","réduire exposition"]
```

### 3) Produire 1 scène (120–180 mots)
```text
MODE: SCÈNES/AMBIANCES
Brief: "<micro‑situation>"
Tone: "<...>"
Link: Beat #<n>
```

### 4) Créer du lore **réactif** (si un Beat l'exige)
```text
MODE: LORE ENGINE
Type: "<faction|lieu|pnj|item>"
Nom: "<...>"
Contexte: "<besoin exprimé par Beat #n>"
Liens: ["Beat #<n>", "Scene_<id>"]
```

---
## D. Rappels utiles
- **Toujours** en session active (`SESSION START`) ; ferme par `SESSION END`.
- **PATHFINDER** a besoin d'un **Start**, d'une **Destination**, d'un **scope**, d'un **beats_target**, et de **constraints**.
- **Chaque Beat** doit **modifier un état** (relation / ressource / indice / position / risque).
- **Lore** : ne créer que si un Beat / Waypoint le **nécessite** (lore **réactif**).

---
## E. Mini-exemple (neutre)
> Copie d'abord le questionnaire, réponds en une ligne par point, puis colle ce bloc :

```markdown
## START — "Les PJ découvrent un problème urgent dans un lieu isolé."
## DESTINATION — "Le problème est neutralisé et la situation stabilisée."

## ROUTE ACTIVE (Start → Destination)
start: "Découverte du problème"
destination: "Problème neutralisé"
scope: "moyen"
beats_target: 5
constraints:
  must_include: ["indice majeur","tension progressive"]
  must_avoid: ["combat frontal immédiat","exposition longue"]
  themes: ["entraide","mystère","danger"]
  tone: "tendu"
  risk: "moyen"
```

> Ensuite, envoie :
```text
MODE: DRAMATURGIE — PATHFINDER
<bloc ci-dessus>
```
