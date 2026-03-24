---
id: "R-0002"
title: "Référence — Clair‑Obscur (Expédition 33)"
category: "reference"
file_role: "reference"
influence_mode: "SOFT"
weight: 0.70
last_updated: "2026-03-23"
tags: ["reference","culture","clair-obscur","expedition33","tonality","philosophy","motifs"]
---

# PROFIL
Référence culturelle centrée sur les dynamiques **Révélation / Voile**, la **Vérité fragmentaire**, les **Seuils**, et un ensemble d’**archétypes ambigus** qui structurent la notion de Clair‑Obscur. Aucun import graphique, esthétique, ou « charte visuelle ». Influence **symbolique**, **dramaturgique**, **philosophique**, et **structurelle** (Actes II & III). 

# DIALS — dosage par thème (1–5)

## A) Tonalité & Esthétique (EXCLU)
A1:0 A2:0 A3:0 A4:0

## B) Thèmes
B1 Révélation vs Voile: 5
B2 Seuils & Passages (Actes 2–3 uniquement): 4
B3 Vérité fragmentaire: 4
B4 Corruption / Redressement: 2

## C) Motifs narratifs
C1 Lanterne / porteur de lumière: 2
C2 Guide ambigu: 3
C3 Double agenda nocturne: 0
C4 Rituel de passage: 2

## D) Structures
D1 Enquête en spirale: 0
D2 Descente/Remontée: 3
D3 Ellipses nocturnes: 0
D4 Scènes de silence: 0

## E) Archétypes
E1 Veilleur/Lanternier: 5   # PNJ type « Renoir » — gardien du statu quo et du secret du monde
E2 Pénitent: 0
E3 Témoin myope: 3
E4 Masque / Dévoilement: 0
E5 Peintresse / Architecte du Clair‑Obscur: 4   # Perçue comme dangereuse car ignorante de sa vraie nature

## F) Symboles & Objets (EXCLU)
F1:0 F2:0 F3:0 F4:0

## G) Philosophie
G1 « Voir a un coût »: 3
G2 « L’ombre protège »: 2
G3 Vérité locale: 0
G4 « L’homme fabrique l’obscurité »: 4

## H) Interdits (coupe‑circuits)
H1 Gore / horreur viscérale: EXCLU
H2 Surnaturel horrifique « pur »: EXCLU
H3 Esthétique moderne (néon/LED/digital): EXCLU
H4 Moralisme binaire lumière=Bien/ombre=Mal: EXCLU

---

# INCLUDED — utilisations autorisées (et dosées)
- Révélation vs Voile (B1=5) → scènes où **ce qui est montré cache plus qu’il ne révèle**. Indices incomplets, angles morts.
- Seuils & Passages (B2=4) **Actes 2–3** → tirs narratifs basés sur franchissement : portes, arches, cryptes, paliers de compréhension.
- Vérité fragmentaire (B3=4) → indices contradictoires mais cohérents avec la trame globale.
- Rituel de passage (C4=2) → petit coût symbolique (temps, objet, relation) pour « passer ».
- Archétype du **Veilleur/Lanternier** (E1=5) → PNJ type « Renoir », gardien du statu quo.
- Archétype **Témoin myope** (E3=3) → l’équipe Actes 1 et 2 : voit, constate, ne comprend pas encore.
- **Peintresse/Architecte** (E5=4) → figure pivot, perçue comme antagoniste, en réalité protectrice du Clair‑Obscur.
- Philosophie (G1=3, G2=2, G4=4) → toute progression vers la vérité **a un coût** ; l’ombre **n’est pas hostile** ; les zones d’ombre **sont produites par l’homme**.

---

# EXCLUDED — interdits fermes
- **Aucune esthétique graphique importée** (bloc A et F exclus entièrement).
- **Aucun gore / horreur viscérale** (H1).
- **Aucun surnaturel horrifique pur** (H2).
- **Aucune esthétique moderne digitalisée** (H3).
- **Aucun moralisme binaire** (H4).

---

# UTILISATIONS (Pathfinder / Dramaturgie)
- **Pathfinder — Beats/Scènes**
  - Acte II–III : privilégier les **passages** (B2) et les **paliers de compréhension** (D2).
  - (B1=5, B3=4) → fournir **révélations fragmentaires** sans jamais donner la clé complète.
  - (C2=3) → présence d’un **guide ambigu** (pas fiable, pas malveillant).
  - (E1, E5) → Veilleur & Peintresse comme **axes d’ombre** (équilibre, secret, structure).

- **Dramaturgie — garde‑fous**
  - Jamais de bascule horreur ou gore (H1–H2).
  - Pas d’esthétique ou langage moderne visuel (H3).
  - Toujours éviter les dichotomies simplistes (H4).

- **Scène canon — Quality Gates**
  - Pour chaque lien critique → **≥2 vecteurs narratifs** (pas visuels) : objet neutre, témoin, coût symbolique.
  - Toujours ≥1 Orientation MJ (issue en avant).

---

# PARAMÉTRAGE — MODE: REFERENCE FILTER (snippet)
```
MODE: REFERENCE FILTER
Included: [R-0002]
influence: SOFT
weight: 0.70
# Dials
B1:5 B2:4(scope:[Act2,Act3]) B3:4 B4:2
C1:2 C2:3 C3:0 C4:2
D1:0 D2:3 D3:0 D4:0
E1:5 E2:0 E3:3 E4:0 E5:4
G1:3 G2:2 G3:0 G4:4
Constraints: [no_graphics,no_gore,no_horror,no_modern_noir,no_binary_moral]
```
