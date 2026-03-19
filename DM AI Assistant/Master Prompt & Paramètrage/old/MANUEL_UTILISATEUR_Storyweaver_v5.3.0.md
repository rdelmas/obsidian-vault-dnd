---
id: "MANUEL_UTILISATEUR_Storyweaver_v5_3_0"
title: "MANUEL UTILISATEUR — Storyweaver v5.3.0 (CORE)"
category: "manual"
status: "validated"
last_updated: "2026-03-18"
tags: ["manual","storyweaver","v5.3.0","copilot"]
---

# MANUEL UTILISATEUR — **Storyweaver v5.3.0 (CORE)**

Assistant de **worldbuilding DnD 2024**, optimisé pour **Copilot**. Cette version intègre :
- **BOOT strict** : `Settings → Players (réels/placeholder) → Spine → ✅ BOOT OK`.
- **PLAYER LOADING ENFORCER** : charge tous les PJ déclarés, propose des **placeholders** si nécessaire.
- **SESSION ENFORCER** : aucune création sans session active ; greeting, MENU/HELP, journalisation.
- **Guardrails Copilot** : sortie `.md` Obsidian‑ready par défaut, longueurs contrôlées, refus s’il manque une précondition.

---

## 1) **Vue d’ensemble**
Storyweaver structure la création narrative autour de trois piliers :
1. **Données stables** (Settings, PJ, Spine) → Base de vérité.
2. **Session de travail** (S‑XXXX) → Journalisation, cohérence et export.
3. **Modules** (Modes) → Production concrète : Lore, Dramaturgie, Pathfinder, Scènes, Références, Mécaniques, Export.

---

## 2) **Démarrage rapide (Quick Start)**
1. **Nouvelle conversation** Copilot → collez le **Master Prompt v5.3.0**.
2. À la demande, **uploadez** `02_settings_mechanics.md`.
3. Storyweaver détecte **Party Size / Composition** → **uploadez toutes les fiches PJ** correspondantes (ou acceptez la **création de placeholders**).
4. **Uploadez** `03_dramaturgie_campaign_spine.md`.
5. Attendez **« ✅ BOOT OK »** → envoyez `SESSION START — Agenda:[…]`.
6. Utilisez **MENU** (pour voir les modules) et **HELP** (pour les commandes). Lancez ensuite un **MODE**.

---

## 3) **Le fichier Settings** — contenu et utilité
Le fichier `02_settings_mechanics.md` sert d’**ancrage mécanique et opérationnel**. Vous pouvez y indiquer :

- **Système** (DnD 2024) & **Style** (RAW / Rule‑of‑Cool / Mix) → Influence la tonalité des sorties mécaniques.
- **Sources autorisées** (PHB 2024, DMG 2024, MM 2024, autres) → Cadre légal de référence.
- **Stat‑blocking** (précis / abstrait / suggestion) → Niveau de détail attendu pour les blocs techniques.
- **Jets** (simulate / never / on request) → Politique de lancés de dés.
- **Difficulté par défaut** (Low/Medium/Hard) → Calibration globale.
- **Party Size / Composition** (⚠️ **obligatoire** si vous voulez lier les PJ au cadre) → Permet à Storyweaver de **réclamer les fiches PJ** et/ou de **générer des placeholders** pour démarrer.

> **Remplir si non explicite** :
> - Ajoutez un bloc **“Party Composition”** listant les **Noms** des PJ attendus et, si possible, leurs **IDs** (PC‑XXXX) si vous les avez déjà :
>   ```md
>   ## Party Composition
>   - Joueur 1 : Van Elfling (PC-0004)
>   - Joueur 2 : Maëlle — à créer
>   - Joueur 3 : Ouka (PC-0002)
>   ```
> - Si l’ID n’est pas connu : **le Nom suffit**. Storyweaver proposera un **placeholder** (`PC_<Nom>_TEMP_<PC‑XXXX>.md`).

---

## 4) **BOOT** — Initialisation contrôlée
**Objectif** : ne **jamais** produire de contenu avant que toutes les **préconditions** soient réunies.

1) **Settings** → parsing + **récap** : Système, Style, Jets, etc.  
2) **Players** (*PLAYER LOADING ENFORCER*) → Si Party Size > 0 :
   - Réclame **toutes** les fiches PJ listées ;
   - **Propose des placeholders** pour les manquants (nom pris depuis Settings, `status: pending`, YAML strict) ;
   - Passe `has_all_players=true` uniquement quand tous sont présents (réels ou placeholders).
3) **Spine** → parsing + **récap** : Start, Destination, Acts, scope, beats_target, constraints.  
4) **✅ BOOT OK** → invite à `SESSION START — Agenda:[…]`.

---

## 5) **Session** — Le cœur du flux
- Commande : `SESSION START — Agenda:[ item1, item2, item3 ]` → crée `S-XXXX.md`.
- Greeting : liste des modules + rappel `HELP`.
- **Gating** : toute action (Lore, Scènes, Pathfinder, Export) **refusée** si pas de session active.
- `SESSION END` → Résumé, Next Seeds, Change Log + proposition **Export Pack**.

**Workflow type de session** :
1. `SESSION START — Agenda:[ “Créer 1 référence”, “Proposer 5 beats d’ouverture”, “Écrire 1 scène d’attaque” ]`
2. `MODE: REFERENCE FILTER` → cadrage esthétique & thèmes.
3. `MODE: DRAMATURGIE — PATHFINDER` → 5 beats d’ouverture.
4. `MODE: SCÈNES/AMBIANCES` → 1 scène **120–180 mots**.
5. `MODE: LORE ENGINE` → formaliser un lieu ou une faction apparus dans les beats.
6. `SESSION END` → résumé + export proposé.

---

## 6) **MODES** — Détails, bonnes pratiques et **workflows types**

### 6.1 **MODE: DRAMATURGIE — PATHFINDER** (moteur créatif principal)
**À quoi ça sert ?**
- Proposer un **chemin narratif** de **Start** à **Destination**, sous forme de **Waypoints** (jalons) et de **Beats** (micro‑étapes effectives).
- Chaque **Beat** doit **modifier un état** (indice, relation, ressource, position), empêchant les scènes “plateau”.
- Storyweaver exploite le **Spine** (Start/Destination/Acts/tone/risk/constraints) pour générer des **propositions pertinentes** et **actionnables**.

**Commande type** :
```text
MODE: DRAMATURGIE — PATHFINDER
Start: "Arrivée à Port‑Murmure"
Destination: "Briser le monopole de la Guilde"
scope: moyen
beats_target: 5
constraints:
  must_include: ["intrigue politique locale","premier contact avec la Guilde"]
  must_avoid: ["combat frontal prolongé"]
  themes: ["dette", "confidence"]
  tone: "tendu"
  risk: "moyen"
```

**Ce que Storyweaver fait pour vous** :
- Identifie **W1…Wn** (jalons structurants).
- Produit **5 beats numérotés** cohérents avec tone/risk/constraints.
- Assure que chaque beat **fait avancer** : ex. “obtenir un indice clé”, “gagner un allié ambivalent”, “perdre une ressource”.
- Optionnel : propose des **branches** si demandé (B1/B2), pour du “what‑if” cadré.

**Workflow type Pathfinder** :
1) Lancer PATHFINDER avec **beats_target=5** (format court) pour capter l’orientation.
2) Affiner **constraints** (ajout/suppression de must_include/avoid) selon vos priorités.
3) Demander un **PATHFINDER (UPDATE)** focalisé sur **les 2–3 prochains beats**.
4) Produire **1–2 Scènes** sur les beats validés.
5) Créer/mettre à jour **Lore** (lieu/faction/PNJ) uniquement si **un Beat le requiert** (Lore réactif).

**Astuce** : dans vos constraints, ciblez les **leviers d’histoire** (alliés, dettes, menaces, dilemmes) plutôt que des “résultats figés”.

---

### 6.2 **MODE: DRAMATURGIE** (hors Pathfinder)
**À quoi ça sert ?**
- Évaluer / organiser les **arcs** (Promise → Escalade → Payoff → Echo), la **tension** et le **rythme**.
- Proposer du **foreshadowing concret** (indices discrets), des **hooks** et des **échos** thématiques.

**Commande type** :
```text
MODE: DRAMATURGIE
Cible: "Acte I complet"
Objectif: "Clarifier la promesse initiale et deux niveaux d’escalade"
Contraintes: { tone: "mix", risk: "moyen" }
```

**Workflow type Dramaturgie** :
1) Demander un **diagnostic** des arcs en cours (promesse / escalade / payoff / echo).
2) Demander **3 propositions** de **foreshadowing concrets** (indices à disséminer).
3) Figer **2–3 hooks** pour la prochaine session.

---

### 6.3 **MODE: SCÈNES/AMBIANCES**
**À quoi ça sert ?**
- Générer des **scènes brèves** (120–180 mots) : atmosphère, sensoriel, symbole, options MJ.

**Commande type** :
```text
MODE: SCÈNES/AMBIANCES
Brief: "Arrivée nocturne dans l’atelier d’horlogerie"
Tone: "calme"
Link: Beat #2 (Pathfinder)
```

**Workflow type Scènes** :
1) Générer **1 scène** par **beat** validé ;
2) Demander **2 variations** si besoin (tonalité différente) ;
3) Coller en Obsidian et **lier** au Beat/Lore concernés.

---

### 6.4 **MODE: LORE ENGINE**
**À quoi ça sert ?**
- Créer/mettre à jour une **entrée de lore** (faction, lieu, PNJ, item…).
- **Toujours réactif** aux besoins des Beats/Pathfinder.

**Commande type** :
```text
MODE: LORE ENGINE
Type: "Faction"
Nom: "La Guilde du Balancier"
Contexte: "Contrôle officieux des docks de Port‑Murmure"
Liens: [Beat #3, SCÈNE #1]
```

**Workflow type Lore** :
1) Créer/mettre à jour **uniquement** si un Beat/Waypoint le requiert.
2) Ajouter **backlinks** vers Beats/Scènes/PNJ.
3) Fournir **2–3 hooks** concrets utilisables en partie.

---

### 6.5 **MODE: REFERENCE FILTER**
**À quoi ça sert ?**
- Installer des **inspirations** (SOFT/HARD) sans plagier : **Included** (autorisé), **Excluded** (interdit), `weight` (intensité). 

**Commande type** :
```text
MODE: REFERENCE FILTER
Titre: "Clair Obscur — Expedition 33"
Included: ["mélancolie lumineuse","contrastes clair‑obscur","rituel fatal (concept)"]
Excluded: ["noms propres","événements exacts"]
Influence: "SOFT"
weight: 0.8
Action: "Ajouter"
```

**Workflow type Références** :
1) Ajouter 1–2 références **SOFT** (weight 0.8).
2) Poser **EXCLUDED** fermes (noms propres, intrigues exactes) pour rester légal et modulable.
3) Réévaluer le **weight** selon le ressenti en lecture des Beats/Scènes.

---

### 6.6 **MODE: MECHANICS CONFIG**
**À quoi ça sert ?**
- Clarifier le niveau de simulation, le style de résolution, les sources légales.

**Workflow type Mécaniques** :
1) Définir **Style** (RAW / Rule‑of‑Cool / Mix) ;
2) Fixer **Stat‑blocking** (précis vs abstrait) ;
3) Choisir **Jets** (simulate / never / on request).

---

### 6.7 **MODE: EXPORT**
**À quoi ça sert ?**
- Générer un **Export Pack** : fichiers `.md` créés, index CSV, Session Summary, Change Log consolidé.

**Workflow type Export** :
1) `SESSION END` → accepter la **proposition d’Export** ;
2) Récupérer le **bundle** ;
3) Ranger dans `/Exports/` et partager au groupe.

---

## 7) **Bonnes pratiques**
- **Commencer petit** : 5 beats, 1 scène, 1 lore par session.
- **Rendre les beats causaux** : chaque Beat doit “laisser une trace” (indice, relation, ressource, position).
- **Limiter les références** : 1–2 SOFT suffisent, `weight` ≈ 0.8.
- **Toujours journaliser** via la Session (S-XXXX).

---

## 8) **Dépannage express**
- Storyweaver refuse d’écrire → Vérifier **BOOT OK** + **Session active**.
- Manque des PJ → Uploader les fiches ou accepter **placeholders**.
- Sortie trop longue → Rappeler *120–180 mots*. 
- Lore déconnecté → Réaligner via **Pathfinder** (UPDATE) puis Lore **réactif**.

---

## 9) **Glossaire**
- **Spine** : trajectoire maître Start→Destination (+acts, scope, constraints).
- **Waypoint** : jalon conceptuel sur la route.
- **Beat** : micro‑étape qui modifie un état.
- **Lore réactif** : on ne crée du lore que si un Beat/Waypoint le nécessite.
- **Placeholder PC** : fiche PJ minimale (status: pending) générée pour démarrer.

---

## 10) **Changelog (5.3.0)**
- Enforcement **Players** intégré au BOOT.
- Placeholders PJ auto (nom depuis Settings).
- Préconditions étendues (has_all_players).
- Manuel enrichi : workflows détaillés par module.
