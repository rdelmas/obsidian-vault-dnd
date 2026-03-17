# ANNEXES — Storyweaver Structures & Schemas (Obsidian-ready)

  

> Charge ce fichier quand Storyweaver te le demande (commande “CHARGER ANNEXES — STRUCTURES & SCHEMAS”)

> ou lorsque tu souhaites générer/valider des .md structurés (Lore, NPC, PC, References, Sessions, Settings).

  

---

  

## 1) YAML — Registry (Frontmatters officiels)

  

### 1.1 Player Character — PC-XXXX

```yaml

---

id: "PC-XXXX"

title: "Nom du personnage"

category: "player"

status: "pending"

last_updated: "YYYY-MM-DD"

race: ""

class: ""

domain: ""

divine_order: ""

alignment: ""

background: ""

origin: ""

family_role: ""

speed: ""

size: ""

passive_perception: ""

hit_die: ""

hp_max: ""

ac: ""

illustration: ""

tags:

  - "player"

  - "party"

  - "levelX"

  - "pending"

---
```
### 1.2 NPC — N-XXXX

```yaml
---

id: "N-XXXX"

title: "Nom du PNJ"

category: "npc"

status: "pending"

last_updated: "YYYY-MM-DD"

role: ""

species: ""

affiliation: ""

location: ""

importance: ""

alignment: ""

illustration: ""

tags:

  - "npc"

  - "status/pending"

---
```

### 1.3 Lore Entry — L-XXXX

```yaml
---

id: "L-XXXX"

title: "Titre"

category: "location"   # location|faction|culture|cosmology|event|item|magic|other

status: "pending"

last_updated: "YYYY-MM-DD"

source: "conversation" # conversation|obsidian|import

source_file: ""

validation_source: ""

refs_included: []

refs_excluded: []

illustration: ""

tags:

  - "lore/<category>"

  - "status/pending"

---
```

### 1.4 Reference — R-XXXX

```yaml
---

id: "R-XXXX"

title: "Titre de l’œuvre"

medium: "Film|Livre|Jeu|Art|Série"

status: "pending"         # validated|dismissed|pending

last_updated: "YYYY-MM-DD"

influence_mode: "SOFT"    # SOFT|HARD

included: []

excluded: []

notes: ""

tags:

  - "reference"

  - "status/pending"

---
```

### 1.5 Settings Mechanics — SETTINGS-MECH-0001

```yaml
---

id: "SETTINGS-MECH-0001"

title: "Paramètres mécaniques DnD 5e"

category: "settings"

status: "validated"

last_updated: "YYYY-MM-DD"

source: "conversation"

source_file: ""

validation_source: "User confirmation"

illustration: ""

tags:

  - "settings/mechanics"

  - "status/validated"

---
```

### 1.6 Session Notes — S-XXXX

```yaml
---

id: "S-XXXX"

title: "Session YYYY-MM-DD"

category: "session"

status: "validated"

last_updated: "YYYY-MM-DD"

summary_for: ["players","storyweaver"]

tags:

  - "session"

---
```

### 1.7 Quest Log Entry — Q-XXXX

```yaml
---
id: Q-XXXX  

title: "Nom de la quête"  

category: quest  

status: pending  

last_updated: 2026-03-16  

giver: ""        # NPC-XXXX

location: ""     # L-XXXX

reward: ""

danger: ""

illustration: ""

quest_type: main | side | faction  

state: active | completed | failed | dormant  

related: ["[[L-0234]]","[[N-0191]]"]  

tags: ["lore/quest","status/pending"]  
---
```

### 1.8 Autre — O-XXXX
```yaml
---

id: "O-XXXX"

title: "Élément divers / système / règle"

category: "other"

status: "pending"

last_updated: "YYYY-MM-DD"

type: ""     # phénomène, règle, entité non classée…

illustration: ""

tags:

  - "lore/other"

  - "status/pending"

---
```


## 2) Formats — Structures des notes .md

### 2.1 LORE ENTRY — Structure standard
```markdown
## Résumé (1–3 phrases)

Résumé clair, court, autoporteur. Contexte + angle principal.

  

## Détail

- Contexte :

- Particularités :

- Lieux / acteurs impliqués :

- Intrigues liées :

- Liens : [[...]] (backlinks vers PJ/PNJ/autres entrées)

  

## Hooks & Utilisations

- Hook personnel :

- Hook du monde :

- Hook mystère :

  

## Canon & Retcon

- Points validés :

- Contradictions potentielles :

- Propositions (retcon/coexistence/dismiss) :

- Change Log :

  - [YYYY-MM-DD] Création (pending).

```

### 2.2 NPC — Structure courte
```markdown
## Profil

- Rôle :

- Personnalité (3 mots) :

- Objectif :

- Secret :

  

## Liens

- Alliés :

- Rivalités :

- Lieu/Faction liée : [[...]]

  

## Hooks

- Personnel :

- Monde :

- Mystère :
```

### 2.3 Player Character — Structure narrative + mécaniques de jeu (en plus du frontmatter)
```markdown
## Résumé

2–4 phrases — identité, rôle, origine, intention du personnage.

  

---

  

## Profil & Personnalité

### Traits

- Traits :

- Idéaux :

- Liens :

- Défauts :

  

### Historique

Texte court (5–10 lignes). 

Backlinks vers lieux / PNJ importants.

  

### Informations en attente (Pending)

- Élément à clarifier 1 

- Élément à clarifier 2 

  

---

  

## Mécaniques (Générique & Complètes)

  

### Caractéristiques

- **FOR** [ ] ([ ]) 

- **DEX** [ ] ([ ]) 

- **CON** [ ] ([ ]) 

- **INT** [ ] ([ ]) 

- **SAG** [ ] ([ ]) 

- **CHA** [ ] ([ ]) 

  

### Défenses & PV

- **CA :** [ ] 

- **PV max :** [ ] 

- **DV :** [dX] 

- **Vitesse :** [ ] 

- **Initiative :** mod. DEX 

- **Résistances / Immunités / Vulnérabilités :** (si applicable)

  

### Maîtrises

- **Jets de sauvegarde :** [ ] 

- **Compétences maîtrisées :** [ ] 

- **Armes :** [ ] 

- **Armures :** [ ] 

- **Outils :** [ ] 

- **Langues :** [ ]

  

### Équipement

- Liste simple du matériel équipé + inventaire essentiel.

  

---

  

## Aptitudes (universelles)

### Aptitudes de classe (si applicable)

Format court et synthétique :

- Niveau 1 : [….] 

- Niveau 2 : [….] 

- Niveau 3 : [….] 

- Etc.

  

### Sous-classe / Archétype (si applicable)

- Trait 1 

- Trait 2 

- Trait 3 

  

### Capacités raciales

- [ ] 

- [ ]

  

### Dons (si applicable)

- [Don 1] 

- [Don 2] 

  

### Capacités spéciales (martiales / utilitaires)

- Second souffle, Déplacement félin, Rage, Canalisation divine, Expertise, etc. 

*(selon classe ; liste concise)*

  

---

  

## Magie (section optionnelle — NON obligatoire)

*(Inclure seulement si le PJ possède une classe magique OU un don magique)*

  

### Paramètres généraux

- **DD :** 8 + PB + mod Carac 

- **Jet d’attaque de sort :** PB + mod Carac 

- **Liste de sorts basée sur :** [Classe] / [Don]

  

### Cantrips (si applicable)

- [ ] 

- [ ] 

  

### Sorts (si applicable)

- Niveau 1 : [ ] 

- Niveau 2 : [ ] 

- Etc.

  

### Dons magiques (si applicable)

Exemple : *Initiation magique (Wizard)* ou *Initiation magique (Druid)*

  

---

  

## Actions (Génériques)

*(A utiliser quelle que soit la classe : martiale, magique, hybride)*

  

### Actions

- **[Arme]** : +[ ] toucher ; dégâts [ ] ([type]) 

- **[Technique de combat / Manœuvre]** : [effet] 

- **[Sort offensif / capacité]** : DD [ ] / Jet att. sort [ ] — effet

  

### Actions Bonus

- [ ] (maniement d’arme, sorts bonus, techniques, dons…)

  

### Réactions

- [ ] (parade, opportunité, défense magique, interposition, etc.)

  

---

  

## Hooks & Dramaturgie

- Hook personnel : 

- Hook du monde : 

- Hook mystère : 

- Backlinks utiles : [[lore1]], [[npc1]]

  

---

  

## Canon & Retcon

- Points validés : 

- Contradictions potentielles : 

- Propositions : retcon / coexistence / dismiss 

- **Change Log :** 

  - [YYYY-MM-DD] Création (pending).
```

### 2.4 NPC Boss / Elite / Important
Utilise ce format pour : boss, antagonistes majeurs, créatures uniques.
```markdown

## Résumé

2–4 phrases — identité, rôle, origine, intention du personnage.


## Statblock (Boss Générique)

**Nom / Titre :** [ ] 

**Type & Taille :** [ ] 

**CA :** [ ] — **PV :** [ ] — **Vitesse :** [ ] — **PB :** [ ] 

  

### Caractéristiques

FOR [ ] ([ ]) • DEX [ ] ([ ]) • CON [ ] ([ ]) 

INT [ ] ([ ]) • SAG [ ] ([ ]) • CHA [ ] ([ ]) 

  

### Défenses

- Jets de sauvegarde : [ ] 

- Compétences : [ ] 

- Résistances / Immunités / Vulnérabilités : [ ] 

- Sens : [ ] 

- Langues : [ ] 

- FP : [ ] 

  

---

  

## Traits (passifs)

- *Trait thématique majeur* : [ ] 

- *Résistance légendaire (3/jour)* 

- *Trait racial / classe / unique* : [ ]

  

---

  

## Actions

- **Multiattaque** : [2–3 attaques] 

- **Attaque signature** : +[ ] toucher, dégâts [ ] + effet (DD [ ]) 

- **Attaque secondaire / technique** : [ ] 

- **Capacité non magique** : [effet]

  

*(Note : les bosses non lanceurs de sorts n'ont pas besoin d’une section “Magie”.)*

  

---

  

## Actions Bonus

- [ ] (mobilité, posture, invulnérabilité partielle, intimidation, rechargement…)

  

## Réactions

- [ ] (contre-attaque, réduction de dégâts, esquive instinctive…)

  

---

  

## Actions Légendaires (génériques)

*(Le boss a 3 actions légendaires dépensables à la fin du tour d’un autre.)*

  

- **Mouvement** : se déplace sans provoquer d’attaque d’opportunité. 

- **Frappe rapide** : une attaque simple. 

- **Action thématique** : [petit pouvoir lié au thème].

  

---

  

## Actions de Repaire (optionnel)

- **Effet environnemental** : [ ] 

- **Danger déclenché** : [ ] 

- **Renfort / perturbation** : [ ]

  

---

  

## Phases (optionnel)

- **Phase 1 (au-dessus de 50% PV)** : [ ] 

- **Phase 2 (≤ 50% PV)** : [ ] 

- **Phase 3 (optionnelle)** : [ ]

  

---

  

## Tactiques

1–3 lignes.

  

---

  

## Hooks & Intrigues associées

- Hook du monde : 

- Hook personnel : 

- Mystère ou conséquence :
```


### 2.5 Reference — Structure d’entrée
```markdown
## Notes

- Synthèse d’influence (Included only) :

- Zéro tolérance (Excluded) :

- Conseils d’injection :

```

### 2.6 Session Notes — Structure
```markdown
## Session Recap

- Nouveaux fichiers :

- Modifiés :

- Statuts changés :

- Diffs canon :

  

## Next Seeds (3–5)

- …
```

### 2.7 Quest Entry
```markdown
# Résumé

But de la quête en 2–3 phrases.

  

## Objectifs

- Objectif principal :

- Objectifs secondaires :

  

## Déroulé

- Étape 1 :

- Étape 2 :

- Étape 3 :

  

## PNJ & Factions Liées

- NPC : [[N-...]]

- Faction : [[F-...]]

  

## Obstacles

- Combat :

- Social :

- Exploration :

  

## Hooks

- Variante 1 :

- Variante 2 :

  

## Canon & Retcon

- Change Log :

```


### 2.8 Autre (mécanique maison, phénomène, système, règle locale...)
```markdown
## Description

1–3 paragraphes.

  

## Fonctionnement / Impact

- Effet :

- Limites :

- Coût / risque :

  

## Interactions

- Lieux : [[L-...]]

- Factions : [[F-...]]

  

## Hooks

- Scénario :

- Dérive potentielle :

  

## Canon & Retcon

- Change Log :
```
---

## 3) Commandes — Rappel (à utiliser dans la session)

- **CHARGEMENT — FICHIER UNIQUE**  
    `Charge ce fichier en tant que [Player Character | Lore | Reference | Session | Settings] (Validated|Pending).`
    
- **CHARGEMENT — BATCH DE FICHIERS**  
    `Charge tous les fichiers suivants en tant que [TYPE] : ...`
    
- **CHARGEMENT — DOSSIER**  
    `Charge tous les fichiers du dossier <URL/Drive> en tant que [TYPE].`
    
- **CHARGEMENT — URL**  
    `Charge ce fichier : <URL publique/Drive RAW> en tant que [TYPE].`
    
- **MISE À JOUR**  
    `MISE À JOUR — PLAYER CHARACTER: <champ>=<valeur> pour PC-XXXX.`  
    `MISE À JOUR — LORE ENTRY: <champ>=<valeur> pour L-XXXX.`
    
- **VALIDATION**  
    `VALIDE: <ID>`
    
- **RETCON**  
    `RETCON CHECK: <ID_A> vs <ID_B> (propose a/b/c + Change Log)`
    
- **EXPORT**  
    `MODE: EXPORT — Prépare Export Pack (bulk .md + index CSV + Session Summary).`
    
```markdown
---

## 4) Note d’usage (charger cet annexe)

Si Storyweaver t’indique :

> **>>> CHARGER ANNEXES — STRUCTURES & SCHEMAS**  
> Alors, attache ce fichier dans la session pour qu’il ait les formats exacts sous la main.

```

---

### ✅ Comment l’utiliser
1) **Colle le Master Prompt v4 (Core)** dans une nouvelle session.  
2) Si Storyweaver te renvoie la commande :
```

> > > CHARGER ANNEXES — STRUCTURES & SCHEMAS

```
**Joins l’annexe** ci‑dessus (2e bloc) ; à partir de là, il possède tous les **frontmatters** et **formats**.  
3) Travaille normalement (LORE ENGINE / DRAMATURGIE / REFERENCE FILTER / EXPORT).  

Si tu veux, je peux aussi te livrer une **“V4 Extended”** (Core + plus d’exemples guidés + protocoles détaillés) — mais **tu n’injecteras que le Core** dans Gemini, et tu chargeras l’annexe au besoin.

## 4 Liste des types d’éléments reconnus par le moteur Storyweaver (V4)

Tu peux les considérer comme “types officiels” :

| Préfixe                | Type                                           | Inclus dans Master Prompt ? | Présent dans Annexes ? |
| ---------------------- | ---------------------------------------------- | --------------------------- | ---------------------- |
| **PC-XXXX**            | Player Character                               | ✔ oui                       | ✔ oui                  |
| **N-XXXX**             | NPC                                            | ✔ oui                       | ✔ oui                  |
| **L-XXXX**             | Lore générique (fallback)                      | ✔ oui                       | ✔ oui                  |
| **Q-XXXX**             | Quest                                          | ❌                           | ✔ oui                  |
| **F-XXXX**             | Faction                                        | ❌                           | ❌ (ajouté sur demande) |
| **C-XXXX**             | Culture / Religion                             | ❌                           | ❌ (ajouté sur demande) |
| **M-XXXX**             | Magic Item / Object                            | ❌                           | ❌                      |
| **E-XXXX**             | Event / Événement                              | ❌                           | ❌                      |
| **O-XXXX**             | Other (phénomènes, règles locales, anomalies…) | ❌                           | ✔ oui                  |
| **SETTINGS-MECH-0001** | Settings mécaniques                            | ✔ oui                       | ✔ oui                  |
| **S-XXXX**             | Session Notes                                  | ✔ oui                       | ✔ oui                  |
| **R-XXXX**             | Reference                                      | ✔ oui                       | ✔ oui                  |
### 4.1 Ajouter un nouveau type dans le moteur

#### ✔ Étape 1 — Choisir un préfixe unique

Ex :

- F → Faction
- C → Culture ou Religion
- M → Objet / Artefact
- E → Événement
- O → Autre (catch‑all générique)

#### ✔ Étape 2 — Définir un **frontmatter YAML strict**

Comme ceux de PC/NPC mais adaptés à ton élément.

#### ✔ Étape 3 — Définir un **format interne** (sections de la note)

– Résumé  
– Détail  
– Interactions  
– Hooks  
– Canon & Retcon  
(et sections supplémentaires selon le type)

#### ✔ Étape 4 — Ajouter ces formats dans ton fichier :

👉 **ANNEXES — Storyweaver Structures & Schemas.md**

#### ✔ Étape 5 — Storyweaver les utilisera automatiquement

Car le Master Prompt V4 contient cette règle :

> Si une structure n’est pas dans le contexte :  
> **>>> CHARGER ANNEXES — STRUCTURES & SCHEMAS**