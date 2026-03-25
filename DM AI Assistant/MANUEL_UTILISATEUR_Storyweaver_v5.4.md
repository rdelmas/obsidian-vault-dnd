---
id: "MANUEL_UTILISATEUR_Storyweaver_v5_4"
title: "MANUEL UTILISATEUR — Storyweaver v5.4 (Lisible+)"
category: "manual"
status: "validated"
last_updated: "2026-03-22"
tags: ["manual","storyweaver","v5.4","copilot","pathfinder","dramaturgie"]
compatibility: "MASTER_PROMPT v5.4 • SETTINGS-ANNEX-SCHEMAS v5.4 • SPINE v4"
---

# 0) Comment utiliser ce document — *Guide rapide*
**Flash 10s** : Storyweaver est un **atelier narratif**. Tu fournis les **sources** (Settings, Schémas, SPINE, Lore/PNJ/Lieux), Storyweaver fournit **méthode & outils** (Pathfinder, Dramaturgie, Scènes, Export).  
**Objectif** : démarrer un projet **complet** en 30 minutes, même sans connaissance préalable.

**À exécuter (checklist)**
- [ ] Créer **Settings** (file_role=`settings`).
- [ ] Charger **tous les PJ** déclarés (ou **placeholders**).
- [ ] Charger **Annexe Schémas** (file_role=`structures_schemas`).
- [ ] Créer **SPINE (campagne)** multi‑arcs (placeholders + `runtime_state.last_checkpoint`).
- [ ] Ouvrir **SESSION** (Agenda ≤ 3 items).
- [ ] Utiliser **Pathfinder** (Waypoints → Beats → **Extraction Playbook**).
- [ ] Rédiger/Adapter **Scènes** (format canon).
- [ ] Maintenir **Index Global (VALIDÉ)**.

---
# 1) Vue d’ensemble & principes
- **Sources ≠ Moteur** : *Sources* = SPINE + Lore/PNJ/Lieux (ton univers). *Moteur* = Pathfinder & Dramaturgie (méthode).  
- **Zéro invention d’univers** par le moteur : s’il manque une donnée → **placeholder** visible.  
- **Fail‑forward** systématique : chaque scène propose ≥ 1 **Orientation MJ**.  
- **Quality‑gates** bloquantes : extraction Playbook **refusée** si un contrôle est KO.

---
# 2) Fichiers & rôles (YAML) — *tolérant au nom, strict au rôle*
> Hérité de v5.3.2, étendu v5.4 (ajouts : SPINE v4, Index Global, Stop/Resume).  
> Exemple YAML minimal requis dans chaque fichier.

## 2.1 Master Prompt (obligatoire)
```yaml
prompt_version: "5.4"
prompt_date: "YYYY-MM-DD"
file_role: "master_prompt"
```
Nom recommandé : `01_master_prompt_v5.4_CORE.md`.

## 2.2 Settings (obligatoire)
```yaml
---
id: "SETTINGS-MECHANICS"
category: "settings"
file_role: "settings"
party_size: 3
party_composition:
  - name: "Van Elfling" # id: PC-0004 si connu
  - name: "Maëlle"
  - name: "Ouka"
---
```
Nom recommandé : `02_settings_mechanics.md`.

## 2.3 Structures & Schémas (obligatoire **avant toute création**)
```yaml
---
id: "SETTINGS-ANNEX-SCHEMAS"
category: "annex"
file_role: "structures_schemas"
schemas_version: "1.4"
---
```
Nom recommandé : `03_structures_schemas.md`.

## 2.4 SPINE (campagne) — *source de vérité de la campagne*
```yaml
---
id: "SPINE-<NOM-CAMPAGNE>"
category: "spine"
file_role: "spine"
last_updated: "YYYY-MM-DD"
placeholders:
  ANY_VILLAGE: "⚑_A définir"
  ANY_SITE: "⚑_A définir"
runtime_state:
  last_checkpoint: "ARC-01.SCENE-01"
  last_user: "⚑_A définir"
  last_update: "YYYY-MM-DD"
---
```
Nom recommandé : `04_dramaturgie_campaign_spine.md`.

## 2.5 Stats & Feats (optionnel)
```yaml
---
id: "SETTINGS-ANNEX-STATS"
category: "annex"
file_role: "stats_feats"
---
```
Nom recommandé : `05_stats_feats.md`.

> *Référence v5.3.2 conservée et mise à jour vers v5.4 (exemples YAML et nommage).*  

---
# 3) Workflow Storyweaver v5.4 — *du premier fichier au Playbook*
**Flash 10s** : Suis l’ordre. Si un prérequis manque, le moteur s’arrête et explique **quoi** fournir.

1. **Settings** → parse + récap.
2. **Players** → charger **tous** les PJ (ou générer **placeholders**).  
3. **Annexe Schémas** → activer gabarits.
4. **SPINE** → TL;DR, Arcs, Scènes (format canon), Beats mapping, `runtime_state` (Stop/Resume).  
5. **SESSION START — Agenda:[…]**.  
6. **Pathfinder** → Waypoints & Beats puis **Extracteur → Playbook** (avec **One‑Page Start**).  
7. **Scènes** → écrire/adapter au format **canon** (voir §6.2).  
8. **Index Global (VALIDÉ)** → mettre à jour **uniquement** le contenu validé.  
9. **SESSION END** → Résumé, Next Seeds, Export.

---
# 4) BOOT — Démarrage contrôlé (ordre strict)
**Préconditions**
- has_settings = true  
- has_all_players = true  
- has_struct_schemas = true  
- has_spine = true

**Règles (bloquantes)**
- PATHFINDER **interdit** tant qu’un drapeau = false.  
- Créations `.md` **interdites** tant que `structures_schemas` non chargé.

**Séquence**  
(1) Settings → (2) Players → (3) Schémas → (4) SPINE → **✅ BOOT OK** → proposer *SESSION START*.

> Hérité du manuel v5.3.2, inchangé dans son principe (seuls les contrôles SPINE v4 sont ajoutés).

---
# 5) Sessions — cadre de production
- `SESSION START — Agenda:[ … ]` → crée `S-XXXX.md` (YAML strict) avec **Agenda / Changements / Créations/Modifs / Résumé fin / Next Seeds**.  
- Toute création **refusée** si pas de session active.  
- `SESSION END` → Résumé, Next Seeds, Change Log + **proposition EXPORT**.

**Exemple (reprise v5.3.2, adapté)**
```text
SESSION START — Agenda:[ "Références", "Pathfinder (5 beats)", "1 Scène d’ouverture" ]
MODE: REFERENCE FILTER (SOFT 0.8 + Excluded fermes)
MODE: DRAMATURGIE — PATHFINDER (5 beats)
MODE: SCÈNES/AMBIANCES (120–180 mots)
MODE: LORE ENGINE (lore réactif)
SESSION END (Résumé + Next Seeds + Export)
```

---
# 6) Dramaturgie & Pathfinder — *de l’idée au Playbook*
## 6.1 Pathfinder (moteur)
**Flash 10s** : Génère un plan jouable **sans inventer d’univers** (SPINE + Lore chargés).  
**Entrées minimales** : Start/Destination, scope, beats_target, constraints (must_include/avoid, themes, tone, risk).  
**Sorties** : Waypoints (W1..Wn) + Beats #1..#N (**chaque Beat modifie un état** : relation / indice / ressource / position).

**Conseil** : 5 beats courts → UPDATE ciblé 2–3 beats → **Extraction Playbook** → Scènes → Lore réactif.

## 6.2 Scènes — deux formats
- **Scène “Ambiance”** (*héritée v5.3.2*) : 120–180 mots, 3–6 phrases, 2–3 détails sensoriels, 1 symbole, 2–3 options MJ, Note OOC.  
- **Scène “Canon (Pathfinder)”** — **format standard** à utiliser dans SPINE & Playbook :
```markdown
# [ARC_ID].[SCENE_ID] — [TITRE]
- **Cadre :** [où/quand — neutre]
- **Objectifs MJ :** [bullets]
- **Déclencheurs :** [bullets]
- **Éléments concrets :** [≥2 vecteurs : objet/témoin/effet]
- **Orientations MJ (fail-forward) :** [≥1 piste]
- **Complications :** [risques, résistances]
- **Sorties :** [états narratifs atteints]
- **Flash 10s :** *phrase ultra‑synthétique*
- **Références :** [[SPINE_…]] [[L‑000X_…]] [[PNJ_…]] [[LIEU_…]]
```

## 6.3 Extracteur de scènes → **Playbook**
**But** : produire `PF_PLAYBOOK.md` à partir du SPINE.  
**Structure exigée** :
- **One‑Page Start** (en tête)
```markdown
# One‑Page Start — [TITRE CAMPAGNE]
- **Pitch :** [2–3 lignes]
- **Cadre/Tonalité :** [périmètre]
- **Arcs :** [liste ARC‑ID + titre]
- **Hooks PJ (3) :** [•] [•] [•]
- **Beats (macro) :** [5 bullets]
- **Ressources :** [[SPINE]] [[INDEX_GLOBAL]] [[LORE_*]] [[PNJ_*]] [[LIEU_*]]
```
- **Scènes** : collées au **format canon** (cf. 6.2).  
- **TL;DR** & **Beats mapping** en fin de Playbook.

## 6.4 Quality Gates (bloquantes)
**À cocher avant extraction Playbook**
- [ ] QG‑1 — **Template SCÈNE** complet (100%).
- [ ] QG‑2 — **≥1 Orientation MJ** par scène (fail‑forward).
- [ ] QG‑3 — **≥2 vecteurs concrets** par lien critique.
- [ ] QG‑4 — **TL;DR + Beats↔Scènes** présents.
- [ ] QG‑5 — **Placeholders centralisés** (zéro TODO dispersé).
- [ ] QG‑6 — `runtime_state.last_checkpoint` + `<!-- STORYWEAVER_STOP: ... -->`.
**Si KO** → **Stop**. Afficher les écarts + proposer la correction guidée.

## 6.5 Index Global (VALIDÉ uniquement)
- L’Index global ne recense **que** le contenu **validé** (arcs, scènes, Lore/PNJ/Lieux).  
- Les drafts restent hors index jusqu’à validation explicite.

## 6.6 Workflow mode SideQuests
### Workflow — Mode Side Quests (S×L)

1. Charger le SPINE. 
2. Charger ou créer `Side_Quests_Campagne.md`. 
3. Charger les Références (optionnel). 
4. Extraire les Sources (S). 
5. Extraire les Liens narratifs (L). 
6. Construire la matrice S×L. 
7. Générer 3–6 hooks. 
8. Présenter au MJ pour validation ou modification. 
9. Archiver les Hooks validés dans le Ledger. 
10. Mettre à jour l’Index Global (VALIDÉ) si nécessaire.

---
# 7) SPINE (campagne) — *source unique de vérité*
**Flash 10s** : Le SPINE **décrit la campagne** (donc spécifique). Il contient ce que Pathfinder doit exploiter : **TL;DR, Arcs, Scènes, Beats mapping**, **placeholders** et **runtime_state**.

## 7.1 Sections obligatoires
- **TL;DR** (5–8 bullets)
- **Arcs** (liste ARC‑ID + titre + *beats_hint*)
- **Scènes** (format **canon**)
- **Beats → Scènes** (mapping)
- **Références** (Lore/PNJ/Lieux cités)
- **Index Global (VALIDÉ)** — parties validées et datées
- **placeholders** (glossaire en tête de fichier)
- **runtime_state** (Stop/Resume)

## 7.2 Stop/Resume (reprise Storyweaver)
- YAML : `runtime_state.last_checkpoint: "ARC-XX.SCENE-YY"`
- Commentaire : `<!-- STORYWEAVER_STOP: ARC-XX.SCENE-YY -->`
> Storyweaver proposera automatiquement de **reprendre** à `last_checkpoint`.

---
# 8) Annexes — pourquoi, quand, comment (v5.4)
- **Annexe Schémas** (obligatoire) : alimente tous les gabarits (PC/NPC/Lore/Scène/… + SPINE/SCÈNE canons).  
- **Annexe Stats & Feats** (optionnelle) : à charger si besoin de mécaniques.

**Référence** : voir `SETTINGS-ANNEX-SCHEMAS` v5.4 (intègre **SPINE**, **SCÈNE canon**, **Extracteur Playbook**, **Quality Gates**, **Stop/Resume**).

---
# 9) Bonnes pratiques
- 1 session = 1 **objectif narratif** clair (Agenda ≤ 3 items).  
- 5 beats / passe ; 1–2 scènes ; 1 entrée de lore max.  
- 1–2 références SOFT (weight≈0.8) + Excluded précis.  
- **Index Global** : ne valider que les contenus prêts (sinon placeholder).  
- **Placeholders** : visibles, centralisés (en tête du SPINE).  
- **Versionning** : conserver des backups (vX.Y.Z).

---
# 10) Dépannage & anti‑patterns
**Erreurs fréquentes**
- *PATHFINDER bloqué* → vérifier BOOT OK + session active + Annexe Schémas chargée.  
- *PJ manquants* → uploader ou générer **placeholders**.  
- *Lore hors‑sujet* → relancer **Pathfinder (UPDATE)** puis **Lore réactif**.  
- *Confusion Scène Ambiance / Scène Canon* → Ambiance = 120–180 mots ; Canon = **template standard**.

---
# 11) Glossaire v5.4
- **SPINE** : source maître de campagne (TL;DR, Arcs, Scènes, Beats mapping).  
- **Waypoint** : jalon conceptuel.  
- **Beat** : micro‑étape qui modifie un état (relation/indice/ressource/position).  
- **Scène Ambiance** : 120–180 mots (sensoriel).  
- **Scène Canon** : template dramaturgique (Pathfinder).  
- **One‑Page Start** : page d’ouverture du Playbook.  
- **Playbook** : livret de préparation des sessions (extraction Pathfinder).  
- **Index Global (VALIDÉ)** : registre des éléments prêts.  
- **Stop/Resume** : mécanisme de reprise via `runtime_state` + ancre STOP.

---
# Annexes — Exemples prêts à copier
## A. SPINE — squelette
```markdown
---
id: "SPINE-<NOM>"
category: "spine"
file_role: "spine"
placeholders:
  ANY_SITE: "⚑_A définir"
runtime_state:
  last_checkpoint: "ARC-01.SCENE-01"
  last_user: "⚑_A définir"
  last_update: "YYYY-MM-DD"
---

# SPINE — <NOM>
## TL;DR
- [1] ⚑
- [2] ⚑

## Arcs
- ARC‑01 — ⚑ (beats_hint: [Beat1 ouverture, Beat2 incident, Beat3 pression, Beat4 fracture, Beat5 arbitrage])

## Scènes
### ARC‑01.SCENE‑01 — ⚑
- **Cadre :** ⚑
- **Objectifs MJ :** ⚑
- **Déclencheurs :** ⚑
- **Éléments concrets :** ⚑, ⚑
- **Orientations MJ :** ⚑
- **Complications :** ⚑
- **Sorties :** ⚑
- **Flash 10s :** *⚑*

<!-- STORYWEAVER_STOP: ARC-01.SCENE-01 -->

## Beats → Scènes
- Beat 1 : ARC‑01.SCENE‑01

## Références
- [[L‑000X_…]] [[PNJ_…]] [[LIEU_…]]

## Index Global (VALIDÉ)
- ⚑
```

## B. Scène Canon — template
```markdown
# ARC‑01.SCENE‑02 — ⚑
- **Cadre :** ⚑
- **Objectifs MJ :** ⚑
- **Déclencheurs :** ⚑
- **Éléments concrets :** ⚑, ⚑
- **Orientations MJ :** ⚑
- **Complications :** ⚑
- **Sorties :** ⚑
- **Flash 10s :** *⚑*
- **Références :** [[SPINE_…]] [[L‑000X_…]] [[PNJ_…]] [[LIEU_…]]
```

## C. One‑Page Start — template
```markdown
# One‑Page Start — ⚑ Titre campagne
- **Pitch :** ⚑
- **Cadre/Tonalité :** ⚑
- **Arcs :** ARC‑01 — ⚑ ; ARC‑02 — ⚑
- **Hooks PJ (3) :** ⚑ / ⚑ / ⚑
- **Beats (macro) :** ⚑ / ⚑ / ⚑ / ⚑ / ⚑
- **Ressources :** [[SPINE]] [[INDEX_GLOBAL]] [[LORE_*]] [[PNJ_*]] [[LIEU_*]]
```
