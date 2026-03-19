---
id: "DELIVERY-NOTE-Storyweaver_v5_3_2"
title: "Bon de livraison — Storyweaver v5.3.2"
category: "delivery"
status: "validated"
last_updated: "2026-03-19"
---

# 📦 Bon de livraison — Storyweaver v5.3.2
**Client :** DELMAS, Romain  **Date :** 2026-03-19  **Périmètre :** Mise en conformité v5.3.2 (BOOT YAML‑first, Schémas unifiés, Assistant de cadrage, Module de référence avancé)

---
## 1) Inventaire des livrables

> Chaque entrée liste : **Nom**, **Version**, **Rôle**, **Résumé**, **Lien de téléchargement**.

### Core & Démarrage
- **01_master_prompt_v5.3.2_CORE.md** — **v5.3.2**    **Rôle :** Master Prompt (règles & modes).    **Résumé :** Définit le BOOT strict (Settings → Players → Annexes Schémas → Spine), le *lore réactif*, les modules (Dramaturgie, PATHFINDER, Scènes, Lore Engine, Reference, Export) et les garde‑fous (SOFT/HARD, Excluded).    **Lien :** [Télécharger](https://ca-prod.asyncgw.teams.microsoft.com/v1/objects/0-cca-d2-96781b13521940b1fb7cfdaf8750c475/views/original/01_master_prompt_v5.3.2_CORE.md)

- **02_settings_mechanics.md** — **file_version 1.1**    **Rôle :** Settings mécaniques (file_role=`settings`).    **Résumé :** Paramètres DnD 2024 (style RAW/Rule‑of‑Cool mix, sources autorisées, roll policy *on_request*, party_size=5 + tableau joueurs). Utilisé par le BOOT et le Player Loading Enforcer.    **Lien :** [Télécharger](https://ca-prod.asyncgw.teams.microsoft.com/v1/objects/0-eca-d3-13c9fa39b7f0a7935174ddd63c4af45e/views/original/02_settings_mechanics.md)

### Annexes & Schémas
- **03_structures_schemas.md** — **schemas_version 1.3**    **Rôle :** Annexes — Schémas (file_role=`structures_schemas`).    **Résumé :** Sommaire + tableau récap + sections **par type** (YAML + Structure + Exemple DATA neutre) : PC, NPC, Lore, Faction, Culture, Item, Event, Organization, Region, Ritual, Reference, Session, Quest, Other, Narrative Route. **Obligatoire** avant toute création `.md`.    **Lien :** [Télécharger](https://ca-prod.asyncgw.teams.microsoft.com/v1/objects/0-eca-d1-000a77f16ecf605d8523bf88059dfd7a/views/original/03_structures_schemas.md)

### Dramaturgie (Spine)
- **04_dramaturgie_campaign_spine.md** — **neutre**    **Rôle :** Spine narratif (file_role=`spine`).    **Résumé :** Gabarit vierge — Start/Destination, Route Active, Waypoints, Beats (via PATHFINDER), Historique, Besoins en lore. Sert d’ossature narrative, **sans univers imposé**.    **Lien :** [Télécharger](https://ca-prod.asyncgw.teams.microsoft.com/v1/objects/0-eca-d1-cc571d210d607e982c92599828943c99/views/original/04_dramaturgie_campaign_spine.md)

- **04B_spine_modeles_universels.md** — **gabarits**    **Rôle :** Modèles dramaturgiques (3, 4, 5 actes ; 7 étapes ; Saison ; One‑shot).    **Résumé :** Blocs prêts à copier‑coller sous le YAML du Spine pour choisir une forme (avec `default_beats`). **Aucun univers**.    **Lien :** [Télécharger](https://ca-prod.asyncgw.teams.microsoft.com/v1/objects/0-cca-d1-35faedbd985dc20c4c9a5b58d78a2054/views/original/04B_spine_modeles_universels.md)

### Mécaniques (optionnel)
- **05_stats_feats.md** — **optionnel**    **Rôle :** Annexe mécanique complémentaire.    **Résumé :** Espace pour blocs mécaniques (stats/feats) si besoin ; **non requis** par le BOOT.    **Lien :** [Télécharger](https://ca-prod.asyncgw.teams.microsoft.com/v1/objects/0-cca-d4-5ae962383bf71c41a22d24c3d0e5d9fb/views/original/05_stats_feats.md)

### Outils d’amorçage & de pilotage
- **06_assistant_de_cadrage.md** — **v1.1**    **Rôle :** Assistant de cadrage (file_role=`cadrage_tool`).    **Résumé :** **Quand/Où/Comment** l’utiliser (après **✅ BOOT OK**, en **session active**) + **Questionnaire 90s**, **Gabarit prêt à coller** (Start/Destination/Constraints), **Prompts rapides** (PATHFINDER, UPDATE, Scènes, Lore réactif).    **Lien :** [Télécharger](https://ca-prod.asyncgw.teams.microsoft.com/v1/objects/0-cca-d1-49edd6083aaf0b39a3eec6d943e12c98/views/original/06_assistant_de_cadrage.md)

- **07_reference_engine.md** — **v1.0**    **Rôle :** Module **avancé** de références (file_role=`reference_engine`).    **Résumé :** Enrichit le mode REFERENCE : **scopes** (global/acte/séquence/scène/élément), **profils d’influence** (tonal/thématique/structurelle/stylistique), **pondération dynamique**, **résolution de conflits** (HARD>SOFT, auto‑resolve/priorités), **sécurité anti‑plagiat**. **N’altère pas** le format des fiches R‑XXXX.    **Lien :** [Télécharger](https://ca-prod.asyncgw.teams.microsoft.com/v1/objects/0-eca-d2-099e0e00df29abf5d83e28223663b50f/views/original/07_reference_engine.md)

---
## 2) Résumé exécutif
- **BOOT strict & sûr** (01) : Settings → Players → Annexes Schémas → Spine ; empêche la création hors schémas.  - **Schémas unifiés** (03) : notes **Obsidian‑ready** homogènes avec exemples neutres.  - **Dramaturgie claire** (04 + 04B) : ossature narrative + formes prêtes.  - **Cadrage express** (06) : 10 réponses → bloc direct PATHFINDER.  - **Références sous contrôle** (07) : influences multi‑niveaux sans plagiat, avec résolveur de conflits.

---
## 3) Mode opératoire recommandé
1. **Coller** `01_master_prompt_v5.3.2_CORE.md` (nouvelle conversation).  2. **Charger** `02_settings_mechanics.md` → Player Loading Enforcer.  3. **Charger** `03_structures_schemas.md` (obligatoire pour créer des `.md`).  4. **Charger** `04_dramaturgie_campaign_spine.md` (+ option copier un modèle de `04B`).  5. **✅ BOOT OK** → `SESSION START`.  6. Utiliser `06_assistant_de_cadrage.md` → lancer **PATHFINDER** (passe #1).  7. Générer **SCÈNES** (120–180 mots) ; créer du **LORE** seulement si un **Beat** l’exige.  8. Piloter les **Références** via le mode classique ou le **07 avancé** (scopes, priorités, weighting).

---
## 4) Conformité & garde‑fous
- **Lore réactif** : pas de création de lore sans Beat/Waypoint.  - **References** : SOFT/HARD + `excluded` stricts ; jamais de copie (noms/scènes).  - **Préconditions** : PATHFINDER refusé si Settings/Players/Annexe/Spine manquent ; création `.md` refusée sans **03**.

---
## 5) Contact & prochaine étape
- Option : **ZIP “ReadyPack”** consolidé 01→07 pour diffusion.  - Option : **Starter References** (3 fiches neutres prêtes).  - Option : **Smoketest guidé** (3 min) BOOT → PATHFINDER → SCÈNES → LORE.
