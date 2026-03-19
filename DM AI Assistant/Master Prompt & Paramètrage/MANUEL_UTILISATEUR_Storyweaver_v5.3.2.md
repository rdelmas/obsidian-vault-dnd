---
id: "MANUEL_UTILISATEUR_Storyweaver_v5_3_2"
title: "MANUEL UTILISATEUR — Storyweaver v5.3.2 (CORE)"
category: "manual"
status: "validated"
last_updated: "2026-03-19"
tags: ["manual","storyweaver","v5.3.2","copilot"]
---

# MANUEL UTILISATEUR — **Storyweaver v5.3.2 (CORE)**

**Mises à jour clés vs 5.3.0/5.3.1** :
- **Contrôle d’acceptation par YAML** (`file_role`) — tolérant au nom, strict au rôle.
- **Annexe Schémas (structures)** exigée **avant toute création**.
- **IDs harmonisés** : `SETTINGS-MECHANICS`, `SETTINGS-ANNEX-SCHEMAS`, `SETTINGS-ANNEX-STATS`.
- **Nommage recommandé** : `01/02/03/04/05`.

---
## 1) Fichiers et rôles (YAML)
Storyweaver valide chaque fichier via **son rôle YAML** (`file_role`), ce qui rend le système robuste **même si le nom** du fichier **diffère**.

### 01 — Master Prompt
```yaml
prompt_version: "5.3.2"
prompt_date: "YYYY-MM-DD"
file_role: "master_prompt"
```
Nom recommandé : `01_master_prompt_v5.3.2_CORE.md`.

### 02 — Settings (obligatoire)
```yaml
---
id: "SETTINGS-MECHANICS"
category: "settings"
file_role: "settings"
party_size: 3
party_composition:
  - name: "Van Elfling"  # id: PC-0004 si connu
  - name: "Maëlle"
  - name: "Ouka"
---
```
Nom recommandé : `02_settings_mechanics.md`.

### 03 — Structures & Schémas (obligatoire avant création)
```yaml
---
id: "SETTINGS-ANNEX-SCHEMAS"
category: "annex"
file_role: "structures_schemas"
schemas_version: "1.2"
supported_types: ["faction","lieu","pnj","item","scene","reference","session","quest","culture"]
---
```
Nom recommandé : `03_structures_schemas.md`.

### 04 — Narrative Spine (obligatoire)
```yaml
---
id: "DR-CAMPAIGN-SPINE"
category: "narrative"
file_role: "spine"
default_beats: 5
---
```
Nom recommandé : `04_dramaturgie_campaign_spine.md`.

### 05 — Stats & Feats (optionnel)
```yaml
---
id: "SETTINGS-ANNEX-STATS"
category: "annex"
file_role: "stats_feats"
---
```
Nom recommandé : `05_stats_feats.md`.

---
## 2) BOOT — Démarrage contrôlé (ordre strict)
1) **Settings** (`file_role=settings`) → parsing + **récap** : System/Style/Sources/roll_policy/difficulty/party.
2) **Players** → chargement de **tous** les PJ déclarés (ou **placeholders** générés).
3) **Annexe Schémas** (`file_role=structures_schemas`) → activer les **gabarits YAML** pour toutes les notes.
4) **Spine** (`file_role=spine`) → Start/Destination/Acts/scope/beats/constraints.
5) **✅ BOOT OK** + invitation **`SESSION START — Agenda:[…]`**.

**Important** : PATHFINDER **refusé** tant que l’un des drapeaux `has_settings`, `has_all_players`, `has_struct_schemas`, `has_spine` est faux.

---
## 3) Session — Cadre de production
- `SESSION START — Agenda:[ … ]` → crée `S-XXXX.md`, Greeting + rappel `HELP`.
- Toute création **refusée** si pas de session active.
- `SESSION END` → Résumé, Next Seeds, Change Log + **proposition EXPORT**.

**Workflow type de session** :
1. `SESSION START — Agenda:[ “Références”, “Pathfinder 5 beats”, “1 Scène d’ouverture” ]`
2. `MODE: REFERENCE FILTER` (SOFT 0.8 + Excluded fermes).
3. `MODE: DRAMATURGIE — PATHFINDER` (5 beats). 
4. `MODE: SCÈNES/AMBIANCES` (120–180 mots) lié aux beats.
5. `MODE: LORE ENGINE` (lore **réactif** sur besoins exprimés par les beats).
6. `SESSION END` + EXPORT.

---
## 4) Modules — Détails & usages efficaces

### PATHFINDER (moteur créatif)
- Entrées minimales (Start/Destination/scope/beats/constraints).
- Sortie : Waypoints + Beats (chaque beat **modifie un état** : relation/indice/ressource/position).
- Storyweaver s’appuie sur le **Spine** (tone/risk/acts/constraints) pour proposer des Beats **pertinents**.
- **Conseil** : commencez court (5 beats), puis **UPDATE** ciblé sur 2–3 beats ; enchaînez sur **Scènes** et **Lore réactif**.

### DRAMATURGIE (hors Pathfinder)
- Diagnostic d’arcs (Promise → Escalade → Payoff → Echo), foreshadowing concret, hooks.
- Sortie .md possible (si souhaitée) → requiert l’Annexe Schémas.

### SCÈNES/AMBIANCES
- 120–180 mots, structure sensorielle, options MJ, Note OOC.
- Toujours **lier** à un Beat/Lore.

### LORE ENGINE
- Créer/mettre à jour **uniquement** si un Beat/Waypoint le justifie (lore **réactif**).
- Backlinks + 2–3 hooks concrets.

### REFERENCE FILTER
- `influence: SOFT|HARD` ; `weight` (défaut 0.8) ; Included/Excluded.
- Pas d’**Excluded** en sortie ; éviter mashups non annoncés.

### MECHANICS CONFIG
- Style (RAW/Rule‑of‑Cool/Mix), stat‑blocking, roll policy.

### EXPORT
- Pack .md + index CSV + Session Summary + Change Log consolidé.

---
## 5) Annexes — pourquoi, quand, comment
- **Pourquoi** : garantir une **cohérence de format** (YAML & sections), faciliter l’indexation et l’export.
- **Quand** : **après Settings/Players**, **avant toute création**.
- **Comment** : charger `03_structures_schemas.md` (`file_role=structures_schemas`).
- **Stats & Feats** : optionnel ; utile si la campagne comporte des blocs mécaniques récurrents.

---
## 6) Bonnes pratiques
- 1 session = 1 objectif narratif clair (Agenda ≤ 3 items).
- 5 beats par passe (puis UPDATE), 1–2 scènes, 1 entrée de lore max → éviter la dispersion.
- 1–2 références SOFT (weight≈0.8) + Excluded précis.

---
## 7) Dépannage express
- Refus de créer : vérifier `BOOT OK` + **session active** + **Annexe Schémas chargée**.
- PJ manquants : uploader ou accepter **placeholders**.
- Sorties trop longues : rappeler **120–180** mots.
- Lore hors‑sujet : relancer **Pathfinder (UPDATE)** puis **Lore réactif**.

---
## 8) Glossaire
- **Spine** : trajectoire maître Start→Destination.
- **Waypoint** : jalon conceptuel.
- **Beat** : micro‑étape qui modifie un état.
- **Lore réactif** : création conditionnée par besoins des Beats/Waypoints.
- **Placeholder PC** : fiche PJ minimale (status: pending) pour démarrage.
