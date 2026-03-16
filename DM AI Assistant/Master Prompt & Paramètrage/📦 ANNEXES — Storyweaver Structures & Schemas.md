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

quest_type: main | side | faction  

state: active | completed | failed | dormant  

related: ["[[L-0234]]","[[N-0191]]"]  

tags: ["lore/quest","status/pending"]  
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

### 2.3 Player Character — Structure narrative légère (en plus du frontmatter)
```markdown
## Résumé

2–4 phrases sur l’identité, l’origine, l’intention.

  

## Personnalité

- Traits :

- Idéaux :

- Liens :

- Défauts :

  

## En attente (Pending)

- Éléments à demander au joueur :

  

## Hooks

- Personnel :

- Monde :

- Mystère :

```

### 2.4 Reference — Structure d’entrée
```markdown
## Notes

- Synthèse d’influence (Included only) :

- Zéro tolérance (Excluded) :

- Conseils d’injection :

```

### 2.5 Session Notes — Structure
```markdown
## Session Recap

- Nouveaux fichiers :

- Modifiés :

- Statuts changés :

- Diffs canon :

  

## Next Seeds (3–5)

- …
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
```