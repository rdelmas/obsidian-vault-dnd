---
id: "SPINE-TEMPLATES"
title: "Modèles dramaturgiques universels — Spines"
category: "annex"
status: "validated"
last_updated: "2026-03-19"
file_role: "spine_templates"
version: "1.0"
---

> Ce fichier propose **plusieurs gabarits de Spine** (sans univers) que tu peux **copier/coller** dans ton `04_dramaturgie_campaign_spine.md` selon le format souhaité.  
> Tous sont compatibles avec **Pathfinder** (beats = changements d'état) et la philosophie **story‑first**.

---
## 🇦 Modèle “3 actes” (classique)
```markdown
---
structure: "3-acts"
default_beats: 5
---

# ACTE I — Mise en place & promesse
- Présenter le problème central (Promesse)
- Déclencheur

# ACTE II — Escalade & complications
- Épreuves / Alliés / Adversaires
- Point médian (révélation / renversement)

# ACTE III — Confrontation & résolution
- Climax
- Conséquences & nouvel équilibre
```

---
## 🇧 Modèle “4 actes” (TV / streaming)
```markdown
---
structure: "4-acts"
default_beats: 6
---

# ACTE I — Set‑up & Hook
# ACTE II — Complication 1
# ACTE III — Complication 2
# ACTE IV — Climax & Aftermath
```

---
## 🇨 Modèle “5 actes” (épique / campagne longue)
```markdown
---
structure: "5-acts"
default_beats: 8
---

# ACTE I — Appel / Promesse
# ACTE II — Montée des tensions
# ACTE III — Point médian / bascule
# ACTE IV — Crises / choix irréversible
# ACTE V — Résolution / échos
```

---
## 🇩 Modèle “7 étapes” (monomythe simplifié)
```markdown
---
structure: "7-steps"
default_beats: 7
---

1) Monde ordinaire → 2) Appel → 3) Refus/Conseiller → 4) Franchir le seuil → 5) Épreuves/Alliés/Ennemis → 6) Ordalie / Récompense → 7) Retour transformé
```

---
## 🇪 Modèle “Saison” (arcs multi‑épisodes)
```markdown
---
structure: "season"
default_beats: 10
---

# PILOTE — Promesse & hook de saison
# MID‑SEASON — Révélation pivot
# FINALE — Climax de saison & setup saison N+1
```

---
## 🇫 Modèle “One‑shot” (2–4 heures)
```markdown
---
structure: "one-shot"
default_beats: 4
---

# Phase 1 — Mise en place rapide (promesse claire)
# Phase 2 — Complication unique (timing serré)
# Phase 3 — Choix / Twist
# Phase 4 — Confrontation & retombée
```

---
## Comment utiliser ces modèles
1) Choisis un modèle.
2) Copie son bloc **markdown** (entre ```markdown … ```).
3) Colle‑le dans ton `04_dramaturgie_campaign_spine.md` **sous** le YAML de tête.
4) Renseigne **Start / Destination / constraints / acts** selon ton projet.
5) Lance **Pathfinder** avec `beats_target` adapté.
