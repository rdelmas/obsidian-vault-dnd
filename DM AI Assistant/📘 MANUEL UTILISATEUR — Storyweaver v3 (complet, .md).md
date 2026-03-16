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

- 14. Chargement des données Drive au format .md



  

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
- `05_Players/`
- `06_Lore_Pending/`
- `07_Session_Summaries/`
- `08_Index.csv`

**Procédure** :

1. Nouvelle conversation.
2. Colle `01_Master_Prompt.md`.
3. Colle `02_Settings_Mechanics.md` si utilisé.
4. Demande le chargement logique : références validées + lore validé + personnages + lore pending.
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

---

## 14.📥 CHARGEMENT — Importer du contenu dans Storyweaver

_(Module d’import pour fichiers `.md` depuis Drive, GitHub ou upload direct)_

> Cette section explique **comment importer des fichiers dans Gemini**, puis comment **Storyweaver** (_via ton Master Prompt_) les intègre dans sa mémoire canonique.
> 
> Important : **CHARGEMENT** n’est pas un MODE.  
> C’est une **commande utilisateur**, destinée à Gemini, afin qu’il lise les fichiers pour Storyweaver.

---

### 🧭 1. Principes du système de CHARGEMENT

- Gemini **ne peut pas explorer ton Drive tout seul**.
    
- Tu dois **fournir les fichiers** explicitement par :
    
    - Upload direct
    - Sélecteur Google Drive
    - URL Drive
    - URL GitHub RAW
    - Dossier Drive (Workspace Pro/Enterprise)
- Une fois le fichier transmis, Storyweaver :
    
    - lit le contenu `.md`
    - parse le frontmatter
    - classe l’entrée dans le **Lore Ledger** selon ton instruction
    - met à jour sa **mémoire contextuelle**

---

### 📂 2. Les commandes officielles de CHARGEMENT

#### 🟦 A) Chargement d’un fichier unique

Utilise cette commande **juste après avoir uploadé ou fourni l’URL du fichier** :

```
CHARGEMENT — FICHIER UNIQUE
Charge ce fichier en tant que [Validated Lore | Pending Lore | Player Character | Reference].
```

Exemples :

```
Charge ce fichier en tant que Validated Lore.
```

```
Charge ce fichier en tant que Player Character.
```

---

#### 🟩 B) Chargement en lot (batch de fichiers)

À utiliser lorsque tu fournis plusieurs fichiers (uploadés ou listés) :

```
CHARGEMENT — BATCH DE FICHIERS
Charge tous les fichiers suivants en tant que [TYPE] :
- PC-0001_Fenryx.md
- PC-0002_Ouka.md
- PC-0003_Tyron.md
```

Où **TYPE** =

- Validated Lore
- Pending Lore
- Player Character
- Reference

---

#### 🟨 C) Chargement d’un dossier Drive complet

_(Disponible si Gemini a accès au dossier Drive — généralement Workspace Pro/Enterprise)_

```
CHARGEMENT — DOSSIER
Charge tous les fichiers du dossier suivant en tant que [TYPE] :
https://drive.google.com/drive/folders/ABCDE12345
```

Gemini va alors :

- lister les fichiers du dossier
- les ouvrir un par un
- transmettre le contenu à Storyweaver
- Storyweaver les indexe (ID + category + status)

---

#### 🟥 D) Chargement via URL (Drive ou GitHub RAW)

Pour un fichier public ou partageable :

```
CHARGEMENT — URL
Charge le fichier suivant en tant que [TYPE] :
https://drive.google.com/file/d/ABC123/view?usp=sharing
```

Pour GitHub RAW :

```
CHARGEMENT — URL
Charge le fichier suivant en tant que Validated Lore :
https://raw.githubusercontent.com/monrepo/Players/PC-0001_Fenryx.md
```

---

### 📌 3. Types reconnus lors du CHARGEMENT

Les types suivants sont **officiellement reconnus** :

|Type|Usage|
|---|---|
|**Validated Lore**|Canon permanent|
|**Pending Lore**|Idées non confirmées|
|**Dismissed Lore**|Lore invalidé (rare)|
|**Player Character**|Fiches PJ|
|**Reference**|Œuvres de référence|
|**Settings**|Paramètres mécaniques ou système|
|**Session Notes**|Récaps, exports, etc.|

Storyweaver ajuste automatiquement :

- les **tags**
- le **Lore Ledger**
- le **Canon Hierarchy**

---

### 🧠 4. Ce que fait Storyweaver après CHARGEMENT

Pour chaque fichier `.md` importé, Storyweaver :

1. Parse le **frontmatter YAML**
2. Identifie l’**ID**
3. Identifie la **catégorie** (npc, location, player, reference…)
4. Vérifie le **status** (validated / pending / dismissed)
5. Ajoute l’entrée au :
    - Lore Ledger
    - Reference Ledger
    - Player Ledger
    - Memory Context
6. Met à jour le **Canon Check** interne
7. Confirme le chargement

---

### 🧱 5. Exemple complet (PJ)

Après upload de `PC-0001_Fenryx.md` :

```
CHARGEMENT — FICHIER UNIQUE
Charge ce fichier en tant que Player Character (Validated Lore).
```

Réponse attendue de Storyweaver :

- confirmation du statut
- ajout au Player Ledger
- intégration dans le Lore Ledger
- génération de backlinks (si présents dans le .md)

---

### 🧩 6. Commande universelle (version simple)

Si tu veux éviter les variations :

```
Charge ce fichier en tant que [TYPE].
```

ou

```
Charge ces fichiers en tant que [TYPE].
```

---

### 🏁 7. Quand utiliser CHARGEMENT dans le workflow ?

L’ordre recommandé :

1. Master Prompt v3
2. **CHARGEMENT : 02_Settings_Mechanics.md**
3. **CHARGEMENT : 03_Reference_Ledger.md**
4. **CHARGEMENT : Lore Validé (.md)**
5. **CHARGEMENT : Players (.md)**
6. Canon Check
7. SESSION START