# Storyweaver v3 — Manuel Utilisateur

> Assistant de **worldbuilding DnD 5e** pour générer du lore **Obsidian-ready**, filtrer les références, assurer la **continuité dramaturgique**, et produire des **EXPORT PACKS** vers Google Drive/Workspace.

---


## Sommaire

- 1. Démarrage rapide

- 2. Commandes d’invocation (modules)

- 3. Système d’ID & Conventions de nommage

- 4. Intégration Obsidian

- 5. Mémoire & Contexte

- 6. Dramaturgie & Continuité

- 7. Scènes / Ambiances

- 8. Paramètres DnD 5e

- 9. Session Protocol (Worldbuilding)

- 10. Références — Validation & Filtres

- 11. Export & Sauvegarde (Drive/Workspace)

- 12. Régénération de l’assistant

- 13. Bonnes pratiques & Checklist

  

---

  

## 1. Démarrage rapide

1) **Colle le Master Prompt v3** dans une nouvelle conversation. 

2) (Optionnel) Configure les **paramètres 5e** :
>    MODE: MECHANICS CONFIG Party: 4 joueurs niv. 5 Style: Mix (RAW majoritaire) Sources: PHB + SRD Stat-blocking: suggestion Dice: never

3) (Optionnel) Valide les **références** :
>    MODE: REFERENCE FILTER Référence: "Expedition 33" (Game) Included: dynamiques relationnelles complexes; deuil et perte; mondes coexistant Excluded: esthétique impressionniste; style pinceau Influence Mode: SOFT Action: Ajouter et renvoyer l'entrée .md

4) **Lance la session** :
>    SESSION START — Agenda: [1) Lieux: Temple des Brumes, 2) Histoire: deuil/Myra, 3) Hook principal]


--- 


## 2. Commandes d’invocation (modules) 

#### `LORE ENGINE (créer/modifier du Lore)`

> MODE: LORE ENGINE Tâche: Crée un lieu "Temple des Brumes" (mots-clés: deuil, brume, résonance). Format .md complet + 2–3 hooks + 1 backlink.


#### `DRAMATURGIE (arcs, hooks, foreshadowing)`

> MODE: DRAMATURGIE Tâche: Étend l’arc "Cicatrices du monde" avec 1 foreshadowing concret et 2 hooks liés à L-0234.


#### `SCÈNES/AMBIANCES (description brève injectables)`

> MODE: SCÈNES/AMBIANCES Demande: Ambiance d'entrée de crypte (ton: tendu), 150 mots max, OOC: rappeler 1 hook.


#### `REFERENCE FILTER (valider/mettre à jour)`

> MODE: REFERENCE FILTER Référence: "Expedition 33" (Game) Included: ... Excluded: ... Influence Mode: SOFT Action: Ajouter/Mettre à jour et renvoyer l'entrée .md

#### `MECHANICS CONFIG (paramétrage DnD 5e)`

> MODE: MECHANICS CONFIG Party: ... Style: ... Sources: ... Stat-blocking: ... Dice: ...

#### `VALIDATION / STATUT`

> VALIDE: L-0234
> **ou**
> PENDING: N-0191
> **ou**
> DISMISS: L-0107


#### `RETCON / CONFLITS`

> RETCON CHECK: Conflit entre L-0234 et N-0191 Objectif: proposer (a) retcon ciblé, (b) coexistence in-universe, (c) dismiss + Change Log


#### `EXPORT PACK`

> MODE: EXPORT Action: Préparer EXPORT PACK (bulk .md + index CSV + session summary) Chemin cible: Worldbuilding/Exports/2026-03-16/



---

## 3. Système d’ID & Conventions de nommage

### 3.1. ID (explication)
- Format: `[Préfixe]-[Numéro 4 chiffres]` (ex: `L-0234`, `R-0033`, `N-0191`).
- Numéro **incrémental par préfixe**; **jamais réutilisé** (même si dismissed).
- Utilisé partout: frontmatter, backlinks, export indexes, change logs.

### 3.2. Préfixes
- **L** — Lore générique (ou “Other” si non classé)
- **N** — NPC (PNJ)
- **R** — Reference (œuvres)
- **Q** — Quest
- **E** — Event
- **F** — Faction
- **M** — Magic/Item
- **C** — Culture/Cosmology
- (**O** — Other, optionnel)

### 3.3. Conventions de nommage fichiers

> LORE_[Category]_[slug]_[ID].md REFERENCE_[Slug]_[ID].md

```
Exemples :
- `LORE_Location_temple-des-brumes_L-0234.md`
- `LORE_NPC_myra_L-0191.md`
- `REFERENCE_Expedition-33_R-0033.md`
```
---

## 4. Intégration Obsidian

### 4.1. Arborescence recommandée
```

/Lore/ /NPC/ /Locations/ /Factions/ /Magic/ /Events/ /Quests/ /Items/ /Cosmology/ /Culture/ /Other/ References/ Sessions/ Exports/

````

### 4.2. Frontmatter standard (YAML — Lore)
```yaml
---
id: L-XXXX
title: "TITRE"
category: npc | location | faction | magic | event | quest | item | culture | cosmology | other
status: pending
last_updated: YYYY-MM-DD
source: conversation
source_file: ""
validation_source: ""
refs_included: []
refs_excluded: []
obsidian_links: []
tags: ["lore/<category>","status/pending"]
---
````

### 4.3. Structure interne (sections)

- Résumé (1–3 phrases)
- Détail (Contexte, Particularités, Intrigues liées, Liens)
- Canon & Retcon (Contradictions, Propositions, Change Log)
- Hooks & Utilisations (personnel, monde, mystère)

---

## 5. Mémoire & Contexte

### 5.1. Hierarchie du Canon

1. Lore Validé (.md + `status: validated`)
2. Décisions validées en conversation exportées en `.md`
3. Pending Lore (non canon)
4. Références validées (inspiration, jamais canon)

### 5.2. Règles de conservation (Context Preservation)

- Priorités : Validated > References > Pending (lié à l’agenda) > autres.
- En cas de limite :
    1. Éjecte Dismissed,
    2. Résume Pending non pertinent,
    3. Conserve des mémo‑résumés (ID + 1–2 lignes) pour les éléments validés majeurs.
- Jamais modifier du Validated sans RETCON LOGIC.

### 5.3. Mémoire de session

- **Session Recap** : entrées créées/modifiées, statuts, diffs de canon.
- **NPC Ledger** : PNJ, relations, statut.
- **Quest Log** : actives/completed/failed/dormant.
- **World State** : changements politiques/magiques/environnementaux.
- **Next Seeds** : 3–5 pistes.

### 5.4. Lore Ledger Snapshot (fin de session)

- Validated Lore (IDs + résumés)
- Pending Lore (IDs + enjeux)
- Dismissed Lore (IDs + raisons)
- Canon Warnings (contradictions potentielles)

---

## 6. Dramaturgie & Continuité

- **Arcs** avec: Promise, Escalade, Foreshadowing (objet/indice concret), Payoff, Echo.
- Chaque élément de lore doit :
    - créer 1 backlink,
    - renforcer 1 motif récurrent,
    - offrir 1 opportunité de foreshadowing,
    - proposer 2–3 hooks.
- **Pacing** : étiquette “calme/tendu/cathartique”.
- **Objectif** : des enchaînements naturels des hooks/plots au fil des sessions.

---

## 7. Scènes / Ambiances

**Format standard :**

- Narration (3–6 phrases, présent)
- Détails sensoriels (2–3 éléments)
- Focus (1 symbole/prop)
- Options MJ (2–3 utilisations)
- (OOC) Note (hooks/liens/canon)

**Longueur cible** : ~120–180 mots (sauf demande “développe”).

---

## 8. Paramètres DnD 5e

**Commande type** :
> MODE: MECHANICS CONFIG Party: 4 joueurs niv. 5 Style: Mix (RAW majoritaire) Sources: PHB + SRD Stat-blocking: suggestion Dice: never

**Defaults** : SRD + suggestions, pas de jets simulés, aucun ajout mécanique si non demandé.

---

## 9. Session Protocol (Worldbuilding)

**START**

1. `SESSION START — Agenda: [...]`
2. Storyweaver → Session Recap (si suite) + prise en compte agenda

**DURING**

- Chaque ajout → fichier `.md` prêt Obsidian (+ hooks, liens, dramaturgie)
- Contradiction → `RETCON CHECK` + Change Log
- Optionnel → Player Intent Detector (≤5 lignes)

**END**

- `MODE: EXPORT` → EXPORT PACK (bulk .md + index CSV + session summary)

---

## 10. Références — Validation & Filtres

**Commande type :**

```
MODE: REFERENCE FILTER
Référence: "Expedition 33" (Game)
Included: ...
Excluded: ...
Influence Mode: SOFT
Action: Ajouter/Mettre à jour et renvoyer l'entrée .md
```

**Règles :**

- **Included** = utilisations actives (thèmes, dynamiques, structures).
- **Excluded** = tolérance zéro (jamais, même indirectement).
- **Influence Mode** : HARD > SOFT. Conflit HARD↔HARD → arbitrage demandé.
- À l’injection (lore/scene), appliquer seulement **Included pertinents**.

---

## 11. Export & Sauvegarde (Drive/Workspace)

**Export Pack (fin de session)** :

- Bulk Markdown avec séparateurs :

```
---FILEBREAK---
path: Lore/Locations/LORE_Location_temple-des-brumes_L-0234.md
<contenu .md>
---FILEBREAK---
path: References/REFERENCE_Expedition-33_R-0033.md
<contenu .md>
```

- **Index CSV** (id,title,category,status,path,last_updated)
- **Session Summary** (récap + Change Log + Next Seeds)

**Dans Gemini/Workspace** (si autorisations Drive actives) :

> Demander explicitement de **créer les fichiers** dans le dossier cible et de **générer un Google Doc** “Session Recap — YYYY‑MM‑DD”.

**Astuce** : Maintiens un **Google Sheet “Lore Index”** (ID, titre, statut, chemin).  
Le Storyweaver peut produire un bloc **CSV** pour append.

---

## 12. Régénération de l’assistant

**Dossier Bootstrap (Drive)** :

- `01_Master_Prompt.md`
- `02_Settings_Mechanics.md`
- `03_Reference_Ledger.md`
- `04_Lore_Validated/`
- `05_Lore_Pending/`
- `06_Session_Summaries/`
- `07_Index.csv`

**Procédure** :

1. Nouvelle conversation.
2. Colle `01_Master_Prompt.md`.
3. Demande le chargement logique : références validées + lore validé + pending (comme pending).
4. Colle `02_Settings_Mechanics.md` si utilisé.
5. **Canon Check** (10–15 puces).
6. `SESSION START — Agenda: [...]`.

---

## 13. Bonnes pratiques & Checklist

**Bonnes pratiques**

- Entrées **courtes**, **liens** > longs pavés.
- Un **ID unique** par entrée (jamais réutilisé).
- Toujours demander des sorties **.md prêtes**.
- **Valider explicitement** (commande `VALIDE: ID`).
- **Exports réguliers** (fin de session ou milestones).
- Utiliser **Player Intent Detector** quand l’orientation est ambiguë.

**Checklist démarrage**

- [ ]  Master Prompt v3 collé
- [ ]  (Optionnel) Mechanics configurés
- [ ]  (Optionnel) Références validées
- [ ]  SESSION START + Agenda
- [ ]  Créations en MODE: LORE ENGINE / DRAMATURGIE / SCÈNES
- [ ]  Validations (VALIDE/PENDING/DISMISS)
- [ ]  EXPORT PACK généré + sauvegardé dans Drive