---
id: "R-0003"
title: "Référence — Frieren (Temps, Mémoire, Héritage)"
category: "reference"
file_role: "reference"
influence_mode: "SOFT"
weight: 0.70
last_updated: "2026-03-23"
tags: ["reference","culture","frieren","memory","time","motifs"]
---

# PROFIL
Référence culturelle inspirée de *Frieren*, recentrée sur les dynamiques de **temps long**, de **mémoire**, d’**héritage émotionnel**, de **liens discrets mais profonds**, et de **révélations différées**. Influence **uniforme** sur le monde, sans import graphique animé. 

# DIALS — dosage par thème (1–5)

## A) Tonalité & Esthétique (EXCLU)
A1:0 A2:0 A3:0 A4:0

## B) Motifs & dynamiques
B1 Voyage continu: 2
B2 Rencontres éphémères marquantes: 3
B3 Apprenticeship inversé: 0
B4 Retour sur les traces: 2

## C) Structures & rythmes
C1 Rythme contemplatif (scènes de voyage): 2
C2 Micro-changements: 0
C3 Dualité passé/présent (Passé=origine, Présent=trame): 3
C4 Explosions émotionnelles rares (niveau Expedition 33): 3

## D) Archétypes
D1 Long-vécu / Immortelle (type Renoir - ClairObscur): 5
D2 Disciple dépasse le maître: 0
D3 Ami compris après coup: 0
D4 Gardien du souvenir (PNJ multiples): 3

## E) Philosophie
E1 Comprendre après coup: 3
E2 Gestes importants invisibles: 0
E3 Valeur du lien augmente: 0
E4 Chaque rencontre change profondément: 3

## F) Interdits
F1 Magie simple/élégante (anti-flashy): 3
F2 Anti-caricature / anti-slapstick: 3
F3:0
F4 Destinée héroïque interdite (EXCLU): EXCLU

## G) Symbolique
G1 Objets-souvenirs: 2
G2 Vestiges/ruines (ancien empire fondateur): 5
G3 Gestes répétés: 0
G4 Ciel/météo: 0

---

# INCLUDED — utilisations autorisées
- Liens discrets (B1,B4) → profondeur émotionnelle par petites scènes.
- Rencontres éphémères (B2=3) → PNJ marquants, impact durable.
- C3 (3) → structure miroir Origine/Trame.
- C4 (3) → rares scènes émotionnelles puissantes (révélations, morts PNJ majeurs).
- D1 (5) → archétype "Renoir" appliqué en version long-vécu.
- D4 (3) → PNJ gardiens du souvenir.
- E1/E4 → compréhension différée et transformation lente.
- F1/F2 → magie élégante, ton doux, jamais caricatural.
- G2 (5) → ruines/vestiges comme pivots narratifs (activer Beats/Scènes).

---

# EXCLUDED — interdits fermes
- Toute esthétique anime "flashy".
- Toute structure héroïque destinée ou prophétique.
- Mélodrame excessif.
- Humour slapstick.

---

# UTILISATIONS (Pathfinder / Dramaturgie)
- Beats/Scènes: utiliser les vestiges (G2) comme points d'ancrage.
- C3: faire contraster Origine vs Trame.
- C4: réserver émotions fortes pour les pivots.
- D1: veiller à la présence du long-vécu dans les enjeux.
- D4: PNJ-clés = vecteurs de mémoire.

---

# PARAMÉTRAGE — MODE: REFERENCE FILTER
```
MODE: REFERENCE FILTER
Included: [R-0003]
influence: SOFT
weight: 0.70
# Dials
B1:2 B2:3 B3:0 B4:2
C1:2 C2:0 C3:3 C4:3
D1:5 D2:0 D3:0 D4:3
E1:3 E2:0 E3:0 E4:3
F1:3 F2:3 F3:0 F4:EXCLU
G1:2 G2:5 G3:0 G4:0
Constraints:[no_graphics,no_flashy_magic,no_prophesy,no_slapstick]
```
