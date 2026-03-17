# 📘 MANUEL UTILISATEUR — Storyweaver v4
> Ce document est **auto‑suffisant** : il ne nécessite **aucune version antérieure** (v3, notes, etc.).
> Il explique **comment installer, charger et utiliser** Storyweaver v4 de A à Z (Obsidian, Google Drive, Gemini),
> et fournit des **exemples, procédures, scripts et formats**.

---

## 0) Vue d’ensemble
**Storyweaver v4** est un assistant de **conception narrative** et de **worldbuilding** qui :
- génère des **fichiers Markdown Obsidian‑ready** (avec frontmatter YAML);
- vous aide à **piloter l’histoire en priorité** (philosophie *story‑first*), grâce à un fichier **Spine** (colonne vertébrale de campagne) et aux **Narrative Routes** (chemins Start → Destination);
- propose des **beats** (péripéties, découvertes, obstacles) et garde la **continuité dramaturgique** (foreshadowing, payoff, echo);
- s’intègre à **Google Drive** et peut être automatisé via **Apps Script** (création de fichiers, ID, exports);
- respecte des **règles de canon** (validated/pending/dismissed) et des **routines de session** (export, recap, index).

> **Principe clé** : l’histoire dirige le monde. Le **Spine narratif** (Start/Destination/Acts) pilote la création de contenu. Le lore n’est créé **que si** un waypoint/beat en a besoin.

---

## 1) Pré-requis & outils
- **Obsidian** (ou un éditeur Markdown) — recommandé pour travailler vos `.md`.
- **Google Drive** (compte gratuit ou Workspace). Optionnel : **Gemini** pour sessions assistées.
- **(Optionnel)** Google **Apps Script** (inclus avec Drive) pour automatiser :
  - création de fichiers avec ID;
  - index CSV;
  - exports.

---
## 2) Installation & Fichiers de base
Créez un dossier racine (Vault Obsidian ou Drive) :
```
/Storyweaver
```
Créez l’arborescence suivante :
```
/Storyweaver
  /Dramaturgie
  /Players
  /Lore
    /NPC
    /Locations
    /Factions
    /Magic
    /Events
    /Quests
    /Items
    /Cultures
    /Other
  /References
  /Sessions
  /Exports
  /Bootstrap
  /Scripts
```
Placez dans **/Bootstrap** :
- `01_master_prompt_v4_core.md` (votre Master Prompt, voir §3);
- `02_settings_mechanics.md` (paramètres mécaniques — optionnel);
- `03_dramaturgie_campaign_spine.md` (**fichier maître** de suivi narratif);
- `ANNEXES — Storyweaver Structures & Schemas.md` (formats YAML et structures);

> Vous trouverez dans ce manuel **tous les contenus** nécessaires pour créer ces fichiers (extraits & scripts) — pas besoin d’anciennes versions.

---
## 3) Master Prompt v4 — Contenu minimal (à copier dans `01_master_prompt_v4_core.md`)
> **Objectif** : définir les règles, modes, priorités (story‑first), commandes et garde‑fous.

```
LANGUE & TON
- FR. Clair, structuré, collaboratif.
- Affiche toujours le MODE actif en tête de réponse.

SYSTEM / ROLE
- “The Storyweaver” — assistant de worldbuilding & dramaturgie.
- Produit des sorties Markdown Obsidian‑ready (frontmatter YAML strict).
- Ne simule **aucune mécanique** si non demandé.

MODES
- MODE: LORE ENGINE — créer/affiner du lore. Sortie .md, hooks, backlinks, note dramaturgique.
- MODE: DRAMATURGIE — arcs, foreshadowing, hooks, continuité.
- MODE: DRAMATURGIE — PATHFINDER — (NOUVEAU) proposer un chemin START → DESTINATION sous forme de Waypoints + Beats selon le fichier `03_dramaturgie_campaign_spine.md`.
- MODE: SCÈNES/AMBIANCES — descriptions brèves injectables.
- MODE: MECHANICS CONFIG — consigner paramètres DnD (ou autres) — pas d’application si non demandé.
- MODE: EXPORT — préparer export (.md + CSV + recap).

ID SYSTEM
- Format: PREFIX-XXXX (ex: L-0234, N-0191, PC-0003, NR-0001, AR-0002…).
- Préfixes: L,N,R,Q,E,F,M,C,O, PC, NR (Narrative Route), AR (Story Arc optionnel).
- IDs présents dans YAML, backlinks, index d’export, change logs.

CANON & CONTEXTE
- Hiérarchie: Validated > Décisions validées exportées > Pending > References.
- Jamais modifier du Validated sans RETCON LOGIC + Change Log.

DRAMATURGIE MODULE
- Maintiens des arcs (Promise, Escalade, Foreshadowing, Payoff, Echo) **sans imposer d’arcs PJ**.
- À chaque création (lore/scene/quest…), fournis: 1 backlink, 1 motif, 1 foreshadowing, 2–3 hooks, 1 label de rythme (calme/tendu/cathartique).

NARRATIVE SPINE (FICHIER MAÎTRE)
- Toujours vérifier que `03_dramaturgie_campaign_spine.md` est chargé **avant** de proposer beats/événements.
- Priorité story‑first: la trajectoire Start→Destination guide la génération; le lore n’est créé/étendu **que si** un Waypoint ou un Beat l’exige.
- Respecter la structure en **Acts** si présente dans le YAML (calage du ton/rythme).

PATHFINDER (ROUTES & BEATS)
- Entrées minimales: Start:"…"; Destination:"…"; scope: court|moyen|long; beats_target:N; constraints:{must_include:[], must_avoid:[], themes:[], tone:"…", risk:"…"}.
- Sortie: Waypoints (W1…); Beats numérotés (Type, Objectif, Indice/Gain, État modifié); Branches (si demandé).
- Règles: chaque Beat **modifie un état** (indice, relation, ressource, position). Respecter tone/risk/constraints du Spine.

COMMANDES — CHEAT‑SHEET
- MODE: DRAMATURGIE — PATHFINDER  (Start, Destination, scope, beats_target, constraints)
- MODE: DRAMATURGIE — PATHFINDER (UPDATE)  (proposer 2–3 beats suivants)
- VALIDE: <ID> / PENDING: <ID> / DISMISS: <ID>
- RETCON CHECK: <ID_A> vs <ID_B>
- MODE: EXPORT

GUARDRAILS
- Ne pas générer de beats/événements sans lecture préalable du Spine.
- Lore réactif: créer/étendre L/N/F/E/M uniquement si Waypoint/Beat le justifie.
```

---
## 4) Settings mécaniques — Modèle (à copier dans `02_settings_mechanics.md`)
```yaml
---
id: "SETTINGS-MECH-0001"
title: "Paramètres mécaniques"
category: "settings"
status: "validated"
last_updated: "YYYY-MM-DD"
source: "conversation"
validation_source: "User confirmation"
tags: ["settings/mechanics","status/validated"]
---

# Paramètres
- Système: DnD 5e (2024) ou autre
- Style: RAW | Rule‑of‑Cool | Mix
- Sources autorisées: PHB 2024, DMG, MM, SRD, etc.
- Stat‑blocking: précis | abstrait | suggestion
- Jets: on request | simulate | never
- Difficulté par défaut: Medium (adapter si besoin)
```

---
## 5) Campaign Spine — Fichier maître (à copier dans `03_dramaturgie_campaign_spine.md`)
```yaml
---
id: "DR-CAMPAIGN-SPINE"
title: "Suivi narratif — Colonne vertébrale de la campagne"
category: "narrative"
status: "active"
last_updated: "YYYY-MM-DD"

story_mode: "story-first"
structure: "acts"
default_beats: 5
tone: "mix"
themes: []
acts:
  - id: "ACT I";   title: "À définir"; purpose: ""; notes: []
  - id: "ACT II";  title: "À définir"; purpose: ""; notes: []
  - id: "ACT III"; title: "À définir"; purpose: ""; notes: []
---
```
Structure interne :
```markdown
## START — Point de départ
→ À définir.

## DESTINATION MAJEURE — Moment épique / cliffhanger / résolution
→ À définir.

# ROUTE ACTIVE (Start → Destination)
start: "<START>"
destination: "<DESTINATION>"
scope: "court | moyen | long"
beats_target: 5
constraints:
  must_include: []
  must_avoid: []
  themes: []
  tone: "mix"
  risk: "moyen"
  spotlight: []

# WAYPOINTS
- W1 — …  
- W2 — …  
- W3 — …

# BEAT LIST (générée via PATHFINDER)
1) [Type] …  
2) [Type] …  
3) [Type] …  
4) [Type] …  
5) [Type] …

# HISTORIQUE DES ROUTES
- NR‑0001 : …

# BESOINS EN LORE (créés uniquement si nécessaire)
- Lieux : … / PNJ : … / Objets : … / Indices : …
```

---
## 6) Annexes — Structures & Schemas (extraits essentiels)
Ajoutez dans `ANNEXES — Storyweaver Structures & Schemas.md` :

### 6.1. Registry — Préfixes supplémentaires
```yaml
---
# Narrative Route
id: "NR-XXXX"
category: "narrative-route"
status: "pending"
# (voir structure complète NR ci-dessous)
---
---
# Story Arc (optionnel)
id: "AR-XXXX"
category: "story-arc"
status: "pending"
---
```

### 6.2. Formats — Narrative Route (NR‑XXXX)
```markdown
# Waypoints (jalons)
- W1 — …
- W2 — …
- W3 — …

# Beats (PATHFINDER)
1) [Type] Objectif / État modifié / Indice ou Gain
2) [Type] …
3) [Type] …

# Branches (optionnel)
- B1 — …

# Ressources / États modifiés
- Indices posés : …
- Relations évoluées : …
- Flags : …
```

### 6.3. Formats — Beat Card (modèle)
```markdown
**Beat — [Type]**
- Objectif dramatique
- Indice / Gain
- Opposition (si pertinent)
- État modifié (indice, relation, ressource, position)
```

### 6.4. Formats — Story Arc (AR‑XXXX) (optionnel)
```markdown
## Concept (2–3 phrases)
## Promise
## Escalade
## Foreshadowing (1–3 indices)
## Pivot / Révélations attendues
## Payoff
## Echo
## Connexions (NR/Lore/NPC/Acts)
```

---
## 7) Ordre de chargement — Workflow v4 **officiel**
1) **Master Prompt v4 (Core)**
2) **02_settings_mechanics.md**
3) **03_dramaturgie_campaign_spine.md** (Spine **avant** Players/Lore)
4) **Players** nécessaires
5) **Lore/NPC/Quests** pertinents
6) **Annexes** — seulement si demandé (`>>> CHARGER ANNEXES — …`)

---
## 8) Utilisation — PATHFINDER (exemples prêts)
**Créer une route :**
```
MODE: DRAMATURGIE — PATHFINDER
Start: "Le village est désert et des carillons sonnent faux."
Destination: "Sous l’église, un rite brisé pulse encore."
beats_target: 5
constraints:
  must_include: ["phénomène non hostile au début", "indice incomplet"]
  must_avoid: ["combat prolongé"]
  tone: "tendu"
  risk: "moyen"
```
**Mettre à jour après session :**
```
MODE: DRAMATURGIE — PATHFINDER (UPDATE)
Propose 2–3 beats suivants vers la même destination.
Conserve constraints et tone.
```

---
## 9) Scènes / Ambiances — format
- Narration (3–6 phrases, présent);
- 2–3 détails sensoriels;
- 1 symbole / prop;
- 2–3 options MJ;
- Note OOC (hooks/liens/canon);
- 120–180 mots (par défaut).

---
## 10) Références — Validation & Filtres
- `MODE: REFERENCE FILTER` — créer/mettre à jour une référence (.md) : Included, Excluded, influence SOFT/HARD, statut.
- À l’injection en lore/scene : appliquer uniquement **Included** pertinents; jamais **Excluded**.

---
## 11) Export & Sauvegarde (Pack)
- Export **bulk** `.md` avec séparateurs `---FILEBREAK---` + chemins cibles;
- Index CSV (id,title,category,status,path,last_updated);
- Session Summary (récap + Change Log + Next Seeds);
- Sauvegarde dans `/Exports/YYYY-MM-DD/`.

---
## 12) Régénération (redémarrer l’assistant)
1. Coller Master Prompt v4;
2. Charger Settings;
3. Charger Campaign Spine;
4. Charger Players/Lore nécessaires;
5. Canon Check;
6. `SESSION START — Agenda:[…]`.

---
## 13) Bonnes pratiques & Checklist
**Bonnes pratiques**
- *Story‑first*: la narration pilote — le lore est réactif.
- Entrées courtes, liens > pavés.
- IDs uniques, jamais réutilisés.
- Valider explicitement (VALIDE: ID).
- Exports réguliers (fin de session / milestone).

**Checklist**
- [ ] Master Prompt v4 collé
- [ ] Settings chargés
- [ ] **Spine chargé** (obligatoire)
- [ ] Players/Lore pertinents chargés
- [ ] PATHFINDER lancé (si besoin)
- [ ] Export Pack généré

---
## 14) CHARGEMENT — Importer du contenu
**Principes**
- L’assistant ne “parcourt” pas votre Drive; vous fournissez les fichiers (upload, Docs ouverts, URLs RAW, ou Workspace entreprise pour dossiers).

**Commandes**
```
CHARGEMENT — FICHIER UNIQUE
CHARGEMENT — BATCH DE FICHIERS
CHARGEMENT — URL
CHARGEMENT — DOSSIER  (Workspace pro/enterprise seulement)
```
**Types reconnus**: Validated Lore, Pending Lore, Dismissed Lore, Player Character, Reference, Settings, Narrative Spine, Narrative Route, Session Notes.

---
## 15) INFRASTRUCTURE DRIVE & APPS SCRIPT (complet, sans v3)
> Cette section vous délivre **tout** pour travailler **sans** document antérieur.

### 15.1 Dossiers Drive (rappel pratique)
```
/Storyweaver
  /Dramaturgie
  /Players
  /Lore (NPC/Locations/Factions/Magic/Events/Quests/Items/Cultures/Other)
  /References
  /Sessions
  /Exports
  /Bootstrap
  /Scripts
```

### 15.2 Base d’IDs (Google Sheets)
1) Créez un **Google Sheet** nommé `Storyweaver_ID_Registry`.
2) Onglet `IDs` avec colonnes: `prefix` | `last_number`.
3) Remplissez par exemple: `PC:3, N:1, L:32, Q:4, F:2, C:1, M:1, E:1, O:1, NR:0, AR:0` (adaptez à votre contexte).

### 15.3 Apps Script — Générateur de fichiers Markdown
Dans **Apps Script** (Nouveau script), collez le code suivant :
```javascript
/** Storyweaver — File Generator (Markdown, Obsidian-ready) */
function createStoryweaverFile(prefix, title, folderId) {
  const ss = SpreadsheetApp.openByName('Storyweaver_ID_Registry');
  const sheet = ss.getSheetByName('IDs');
  const f = sheet.createTextFinder(prefix).findNext();
  if (!f) throw new Error('Prefix not found in ID registry: ' + prefix);
  const row = f.getRow();
  const last = sheet.getRange(row, 2).getValue();
  const next = last + 1; sheet.getRange(row, 2).setValue(next);
  const id = `${prefix}-${('0000' + next).slice(-4)}`;

  const fm = buildFrontmatter(prefix, id, title);
  const body = buildBody(prefix);
  const content = fm + '
' + body;

  const folder = DriveApp.getFolderById(folderId);
  const fileName = `${prefix}_${slugify(title)}_${id}.md`;
  const file = folder.createFile(fileName, content, MimeType.PLAIN_TEXT);
  return file.getUrl();
}

function buildFrontmatter(prefix, id, title){
  const today = new Date().toISOString().substring(0,10);
  let category = 'lore';
  if(prefix==='PC') category = 'player';
  if(prefix==='N') category = 'npc';
  if(prefix==='NR') category = 'narrative-route';
  if(prefix==='AR') category = 'story-arc';
  const fm = `---
id: "${id}"
title: "${title}"
category: "${category}"
status: "pending"
last_updated: "${today}"
illustration: ""
tags:
  - "${category}"
  - "status/pending"
---`;
  return fm;
}

function buildBody(prefix){
  if(prefix==='NR'){
    return `
# Waypoints (jalons)
- W1 — …
- W2 — …

# Beats (PATHFINDER)
1) [Type] Objectif / État modifié / Indice ou Gain
2) [Type] …
3) [Type] …

# Branches (optionnel)
- B1 — …

# Ressources / États modifiés
- Indices posés : …
- Relations évoluées : …
- Flags : …
`;
  }
  if(prefix==='AR'){
    return `
## Concept (2–3 phrases)
## Promise
## Escalade
## Foreshadowing (1–3 indices)
## Pivot / Révélations attendues
## Payoff
## Echo
## Connexions (NR/Lore/NPC/Acts)
`;
  }
  // Par défaut: squelette court Lore
  return `
## Résumé
(*À compléter*)

## Détail
- Contexte : …
- Particularités : …
- Liens : [[...]]

## Hooks & Utilisations
- Personnel : …
- Monde : …
- Mystère : …

## Canon & Retcon
- Points validés : …
- Contradictions : …
- Change Log :
  - [${new Date().toISOString().substring(0,10)}] Création (pending).
`;
}

function slugify(s){
  return s.toLowerCase().normalize('NFD').replace(/[^\w\s-]/g,'').trim().replace(/\s+/g,'-');
}
```
**Utilisation Apps Script** :
- Ouvrez `Storyweaver_ID_Registry` → Extensions → Apps Script → collez le code.
- Créez un dossier cible (ex: `/Lore/Locations`) et récupérez son **folderId** (dans l’URL Drive).
- Exécutez dans la console Apps Script :
```javascript
createStoryweaverFile('NR', 'Route_exemple', 'VOTRE_FOLDER_ID')
```
- Un fichier `NR_Route_exemple_NR-0001.md` est généré dans le dossier.

> Adaptez `prefix` pour créer d’autres types (`PC`, `L`, `N`, `AR`, …).

### 15.4 Export Pack (script optionnel)
- Exporter tous les `.md` d’un dossier vers un **fichier unique** avec séparateurs `---FILEBREAK---` et un **CSV** index;
- Générer un **.zip** (via utilitaires Drive) — *facultatif*.
> (Ce script peut être fourni sur demande, mais n’est pas requis pour démarrer.)

---
## 16) FAQ — Cas fréquents
- **Gemini ne lit pas mon dossier Drive** : ouvrez les documents (Docs) ou uploadez les `.md`. Gemini ne “parcourt” pas un dossier public par URL seule.
- **Spine obligatoire ?** Oui : c’est la source de vérité narrative. Sans lui, Storyweaver improvise.
- **Dois‑je créer des Arcs (AR-XXXX) ?** Non. Ils sont optionnels. Commencez par le Spine + les Routes (NR‑XXXX).
- **Puis‑je utiliser sans DnD ?** Oui. Le module mécaniques est optionnel.

---
*Fin du manuel v4 — 2026-03-17*
