# 📘 MANUEL UTILISATEUR — Storyweaver v4

> Ce document est **auto‑suffisant** : il ne nécessite **aucune version antérieure**. Il explique **comment installer, charger et utiliser** Storyweaver v4 (Obsidian, Google Drive, Gemini) et fournit des **exemples**, **procédures**, **scripts** et **formats**.

---

## 0) Vue d’ensemble
**Storyweaver v4** est un assistant de **conception narrative** et de **worldbuilding** qui :
- génère des **fichiers Markdown Obsidian‑ready** (frontmatter YAML strict) ;
- applique une philosophie **story‑first** grâce à un fichier **Spine** (colonne vertébrale de campagne) et aux **Narrative Routes** (chemins Start → Destination) ;
- propose des **beats** (péripéties, découvertes, obstacles) et maintient la **continuité dramaturgique** (foreshadowing, payoff, echo) ;
- s’intègre à **Google Drive** et peut être automatisé via **Apps Script** (création de fichiers, IDs, exports) ;
- respecte des **règles de canon** (validated/pending/dismissed) et des **routines de session** (export, recap, index).

> **Principe clé** : l’histoire dirige le monde. Le **Spine narratif** (Start/Destination/Acts) pilote la création. Le lore n’est créé **que si** un waypoint/beat en a besoin.

---

## 1) Pré‑requis & outils
- **Obsidian** (ou un éditeur Markdown) — recommandé pour travailler vos `.md`.
- **Google Drive** (compte gratuit ou Workspace). Optionnel : **Gemini** pour sessions assistées.
- **(Optionnel)** **Google Apps Script** (inclus avec Drive) pour automatiser : création de fichiers/IDs, index CSV, exports.

---

## 2) Installation & Fichiers de base
Créez un dossier racine :
```
/Storyweaver
```
Arborescence conseillée :
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
- `01_master_prompt_v4_core.md` (votre Master Prompt, voir §3)
- `02_settings_mechanics.md` (paramètres mécaniques — optionnel)
- `03_dramaturgie_campaign_spine.md` (**fichier maître** de suivi narratif)
- `ANNEXES — Storyweaver Structures & Schemas.md` (formats YAML & structures)
- `ANNEXES — Storyweaver Stats & Feats.md` (optionnel)

---

## 3) Master Prompt v4 — contenu minimal (à copier dans `01_master_prompt_v4_core.md`)
```
LANGUE & TON
- FR. Clair, structuré, collaboratif. Affiche toujours le MODE en tête de réponse.

SYSTEM / ROLE
- “The Storyweaver” : assistant de worldbuilding & dramaturgie.
- Sorties Markdown Obsidian‑ready (frontmatter YAML strict). Aucune mécanique si non demandée.

MODES
- MODE: LORE ENGINE — créer/affiner du lore (.md + hooks + backlinks + note dramaturgique)
- MODE: DRAMATURGIE — arcs, foreshadowing, hooks, continuité
- MODE: DRAMATURGIE — PATHFINDER — proposer un chemin START → DESTINATION (Waypoints + Beats) selon `03_dramaturgie_campaign_spine.md`
- MODE: SCÈNES/AMBIANCES — descriptions brèves injectables
- MODE: MECHANICS CONFIG — consigner paramètres DnD/other (pas d’application si non demandé)
- MODE: EXPORT — préparer export (.md + CSV + recap)

ID SYSTEM
- PREFIX-XXXX (L-0234, N-0191, PC-0003, NR-0001, AR-0002…)
- Préfixes: L,N,R,Q,E,F,M,C,O, PC, NR (Narrative Route), AR (Story Arc optionnel)

CANON & CONTEXTE
- Validated > Décisions validées exportées > Pending > References
- Jamais modifier du Validated sans RETCON LOGIC + Change Log

DRAMATURGIE MODULE
- Arcs : Promise, Escalade, Foreshadowing, Payoff, Echo (sans imposer d’arcs PJ)
- À chaque création : 1 backlink, 1 motif, 1 foreshadowing, 2–3 hooks, 1 rythme (calme|tendu|cathartique)

NARRATIVE SPINE (FICHIER MAÎTRE)
- Vérifier que `03_dramaturgie_campaign_spine.md` est chargé avant beats/événements
- Story‑first : Start→Destination guide ; le lore n’est créé QUE si un Waypoint/Beat l’exige
- Respecter la structure en Acts si présente

PATHFINDER (ROUTES & BEATS)
- Entrées : Start:"…" ; Destination:"…" ; scope: court|moyen|long ; beats_target:N ;
  constraints:{must_include:[], must_avoid:[], themes:[], tone:"…", risk:"…"}
- Sortie : Waypoints ; Beats (Type, Objectif, Indice/Gain, État modifié) ; Branches (si demandé)
- Règle : chaque Beat modifie un état (indice, relation, ressource, position)

COMMANDES — CHEAT‑SHEET
- MODE: DRAMATURGIE — PATHFINDER / (UPDATE)
- VALIDE: <ID> / PENDING: <ID> / DISMISS: <ID>
- RETCON CHECK: <A> vs <B>
- MODE: EXPORT

GUARDRAILS
- Pas de beats/événements sans lecture du Spine
- Lore réactif (L/N/F/E/M créés si Waypoint/Beat le justifie)
```

---

## 4) Settings mécaniques — modèle (à copier dans `02_settings_mechanics.md`)
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
- Difficulté par défaut: Medium
```

---

## 5) Campaign Spine — fichier maître (à copier dans  03_dramaturgie_campaign_spine.md
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
  - id: "ACT I"; title: "À définir"; purpose: ""; notes: []
  - id: "ACT II"; title: "À définir"; purpose: ""; notes: []
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

# BEAT LIST (PATHFINDER)
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
À ajouter dans `ANNEXES — Storyweaver Structures & Schemas.md` :

### 6.1. Registry — nouveaux types
```yaml
---
# Narrative Route
id: "NR-XXXX"
category: "narrative-route"
status: "pending"
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

## 7) Ordre de chargement — workflow v4 **officiel**
1) **Master Prompt v4 (Core)**
2) **02_settings_mechanics.md**
3) **03_dramaturgie_campaign_spine.md** (Spine **avant** Players/Lore)
4) **Players** nécessaires
5) **Lore/NPC/Quests** pertinents
6) **Annexes** — seulement si demandé (`>>> CHARGER ANNEXES — …`)

---

## 8) CATALOGUE DES COMMANDES (v4) — avec exemples
> Les commandes ci‑dessous sont **copiables‑collables**. Les sorties attendues sont des blocs `.md` Obsidian‑ready lorsqu’une création/modification de fichier est pertinente.

### 8.1 LORE ENGINE — créer / modifier du lore
**Syntaxe**
```
MODE: LORE ENGINE
Tâche: "<action brève>"
Cible: "<type et titre>"                # ex. Location "Repos-des-Vents"
Options:
  category: "location|faction|culture|cosmology|event|item|magic|other"
  backlinks: ["PC-0002","L-0234"]
  hooks: "auto|off|brief"
  length: "short|standard|extended"
  status: "pending|validated"
```
**Exemple**
```
MODE: LORE ENGINE
Tâche: "Créer un lieu brumeux avec échos sonores"
Cible: Location "Repos-des-Vents"
Options:
  category: "location"
  hooks: "auto"
  backlinks: ["PC-0002"]
```

### 8.2 DRAMATURGIE — continuité, motifs, hooks (hors PATHFINDER)
**Syntaxe**
```
MODE: DRAMATURGIE
Action: "Motifs & hooks"
Cible: "<ID ou titre>"
Options:
  foreshadowing: 1
  hooks: 3
  rythme: "tendu"
```
**Exemple**
```
MODE: DRAMATURGIE
Action: "Motifs & hooks"
Cible: "Réapparition d'une bannière perdue"
Options:
  foreshadowing: 2
  hooks: 3
  rythme: "tendu"
```

### 8.3 DRAMATURGIE — PATHFINDER — routes Start → Destination
**Syntaxe**
```
MODE: DRAMATURGIE — PATHFINDER
Start: "<point de départ>"
Destination: "<destination dramatique>"
scope: "court|moyen|long"
beats_target: 5
constraints:
  must_include: ["…"]
  must_avoid: ["…"]
  themes: ["…"]
  tone: "mix"
  risk: "moyen"
  spotlight: ["…"]
branching: "off|light|full"
```
**Exemple**
```
MODE: DRAMATURGIE — PATHFINDER
Start: "Carillons dissonants dans la place centrale"
Destination: "La crypte active palpite sous l'église"
scope: "moyen"
beats_target: 5
constraints:
  must_include: ["phénomène non hostile au début", "indice incomplet"]
  must_avoid: ["combat prolongé"]
  tone: "tendu"
  risk: "moyen"
branching: "light"
```
**Mise à jour après session**
```
MODE: DRAMATURGIE — PATHFINDER (UPDATE)
Contexte: "Indices A/B acquis, survivant mis en sécurité"
beats_target: 2
Conserver: "constraints|tone|risk"
```

### 8.4 SCÈNES / AMBIANCES — descriptions injectables
**Syntaxe**
```
MODE: SCÈNES/AMBIANCES
Demande: "<pitch de scène>"
Options:
  ton: "calme|tendu|cathartique"
  longueur: "standard"
  symbole: "auto"
  ooc: "note"
```
**Exemple**
```
MODE: SCÈNES/AMBIANCES
Demande: "Ouverture de crypte — tension progressive"
Options:
  ton: "tendu"
  longueur: "standard"
  symbole: "carillon fêlé"
  ooc: "note"
```

### 8.5 REFERENCE FILTER — valider / filtrer une œuvre
**Syntaxe**
```
MODE: REFERENCE FILTER
Référence: "<titre>" (Media: "<Film|Livre|Jeu|Série|Art>")
Included: ["thèmes","structures"]
Excluded: ["tropes bannis"]
Influence Mode: "SOFT|HARD"
Action: "Ajouter|Mettre à jour"
```
**Exemple**
```
MODE: REFERENCE FILTER
Référence: "Expedition 33" (Media: "Jeu")
Included: ["dynamiques de groupe", "perte et deuil"]
Excluded: ["pinceau impressionniste"]
Influence Mode: "SOFT"
Action: "Ajouter"
```

### 8.6 MECHANICS CONFIG — paramétrage système
**Syntaxe**
```
MODE: MECHANICS CONFIG
Party: "4 joueurs niv. 5"
Style: "Mix"
Sources: ["PHB 2024","SRD"]
Stat-blocking: "suggestion"
Dice: "on request"
```
**Exemple**
```
MODE: MECHANICS CONFIG
Party: "4 joueurs niv. 3 (clerc, barbare, magicien, rôdeur)"
Style: "Mix"
Sources: ["PHB 2024","SRD"]
Stat-blocking: "précis"
Dice: "on request"
```

### 8.7 VALIDATION / STATUT — contrôle du canon
**Syntaxe & Exemples**
```
VALIDE: L-0234
PENDING: N-0191
DISMISS: L-0107
```

### 8.8 RETCON CHECK — résolution de contradictions
**Syntaxe**
```
RETCON CHECK: <ID_A> vs <ID_B>
Objectif: "Proposer (a) retcon ciblé, (b) coexistence in-universe, (c) dismiss + Change Log"
```
**Exemple**
```
RETCON CHECK: L-0234 vs L-0210
Objectif: "Proposer (a/b/c) + Change Log en bloc prêt à coller"
```

### 8.9 EXPORT — pack d’export
**Syntaxe**
```
MODE: EXPORT
Action: "Préparer EXPORT PACK"
Chemin: "Exports/2026-03-17/"
Options:
  include: ["Players","Lore/Locations","References"]
  index_csv: "on"
  summary: "on"
```
**Exemple**
```
MODE: EXPORT
Action: "Préparer EXPORT PACK"
Chemin: "Exports/2026-03-17/"
```

### 8.10 CHARGEMENT — importer (commande utilitaire)
**Fichier unique**
```
CHARGEMENT — FICHIER UNIQUE
Charge ce fichier en tant que Narrative Spine.
```
**Batch**
```
CHARGEMENT — BATCH DE FICHIERS
Charge tous les fichiers suivants en tant que Player Character :
- PC_Ouka_PC-0002.md
- PC_Xar_PC-0003.md
```
**URL**
```
CHARGEMENT — URL
Charge le fichier suivant en tant que Validated Lore :
https://raw.githubusercontent.com/mon-repo/Players/PC-0002_Ouka.md
```
**Dossier (Workspace)**
```
CHARGEMENT — DOSSIER
Charge tous les fichiers du dossier suivant en tant que Lore Validé :
https://drive.google.com/drive/folders/ABCDE12345
```

---

## 9) Scènes / Ambiances — format rapide
- Narration (3–6 phrases, présent) ; 2–3 détails sensoriels ; 1 symbole ; 2–3 options MJ ; Note OOC ; 120–180 mots.

---

## 10) Références — validation & filtres
- Included = inspirations autorisées ; Excluded = tolérance zéro ; Influence Mode SOFT/HARD ; application stricte à l’injection.

---

## 11) Export & Sauvegarde (Pack)
- Export bulk `.md` (séparateurs `---FILEBREAK---`) + Index CSV + Session Summary ; sauvegarde dans `/Exports/YYYY-MM-DD/`.

---

## 12) Régénération (redémarrer proprement)
1. Coller Master Prompt v4 ; 2. Charger Settings ; 3. Charger Campaign Spine ; 4. Charger Players/Lore requis ; 5. Canon Check ; 6. `SESSION START — Agenda:[…]`.

---

## 13) Bonnes pratiques & Checklist
**Bonnes pratiques** : Story‑first, entrées courtes, IDs uniques, validations explicites, exports réguliers.
**Checklist** : Master Prompt ; Settings ; **Spine** ; Players/Lore ; PATHFINDER ; Export.

---

## 14) CHARGEMENT — Principes & Types
- Fournir les fichiers explicitement (upload, Docs ouverts, URLs RAW, ou Workspace entreprise pour dossiers). Types : Validated/Pending/Dismissed Lore, Player Character, Reference, Settings, Narrative Spine, Narrative Route, Session Notes.

---

## 15) INFRASTRUCTURE DRIVE & APPS SCRIPT (complet)
### 15.1 Dossiers Drive
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
- `Storyweaver_ID_Registry` → onglet `IDs` avec colonnes: `prefix` | `last_number` ; valeurs de départ: `PC:3, N:1, L:32, Q:4, F:2, C:1, M:1, E:1, O:1, NR:0, AR:0` (adaptez).

### 15.3 Apps Script — Générateur de fichiers Markdown
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
  - [DATE_Ici] Création (pending).
`;
}
function slugify(s){
  return s.toLowerCase().normalize('NFD').replace(/[^\w\s-]/g,'').trim().replace(/\s+/g,'-');
}
```
**Utilisation**
```javascript
createStoryweaverFile('NR', 'Route_exemple', 'VOTRE_FOLDER_ID')
createStoryweaverFile('PC', 'Ouka', 'VOTRE_FOLDER_ID')
createStoryweaverFile('AR', 'Arc_exemple', 'VOTRE_FOLDER_ID')
```

---

## 16) FAQ — cas fréquents
- **Gemini et Drive** : ouvrez les Docs ou uploadez les `.md` ; l’IA ne “parcourt” pas un dossier public par URL seule.
- **Spine obligatoire** : oui. Sans lui, Storyweaver improvise sans votre trajectoire.
- **Arcs (AR-XXXX)** : optionnels. Commencez par Spine + Routes (NR‑XXXX).
- **Sans DnD** : oui, possible ; le module mécaniques est optionnel.

---
*Fin du manuel v4 (catalogue inclus) — 2026-03-17*
