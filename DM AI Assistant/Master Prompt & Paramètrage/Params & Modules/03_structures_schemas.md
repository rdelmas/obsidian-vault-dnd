---
id: "SETTINGS-ANNEX-SCHEMAS"
title: "Structures & Schémas Storyweaver — v5.3.2"
category: "annex"
status: "validated"
last_updated: "2026-03-19"
file_role: "structures_schemas"
schemas_version: "1.3"
---

# 📘 Structures & Schémas — Catalogue complet (v5.3.2)

Ce fichier contient **tous les types reconnus** par Storyweaver, organisés **par type**, chacun avec :
- **YAML (frontmatter)**
- **Structure .md**
- **Exemple DATA neutre**

Un **sommaire** et un **tableau récapitulatif** facilitent la navigation.

---
# 📑 Sommaire
- [Tableau récapitulatif](#tableau-récapitulatif)
- [Player Character (PC)](#player-character-pc)
- [NPC](#npc)
- [Lore Entry](#lore-entry)
- [Faction](#faction)
- [Culture](#culture)
- [Item](#item)
- [Event](#event)
- [Organization](#organization)
- [Region](#region)
- [Ritual](#ritual)
- [Reference](#reference)
- [Session](#session)
- [Quest](#quest)
- [Other](#other)
- [Narrative Route](#narrative-route)

---
# 📋 Tableau récapitulatif
| Type | Préfixe | Catégorie | Lien |
|------|---------|-----------|------|
| Player Character | PC-XXXX | player | [→ PC](#player-character-pc) |
| NPC | N-XXXX | npc | [→ NPC](#npc) |
| Lore Entry | L-XXXX | lore | [→ Lore Entry](#lore-entry) |
| Faction | F-XXXX | lore/faction | [→ Faction](#faction) |
| Culture | C-XXXX | lore/culture | [→ Culture](#culture) |
| Item | M-XXXX | lore/item | [→ Item](#item) |
| Event | E-XXXX | lore/event | [→ Event](#event) |
| Organization | O-XXXX | lore/organization | [→ Organization](#organization) |
| Region | RGN-XXXX | lore/region | [→ Region](#region) |
| Ritual | RTL-XXXX | lore/ritual | [→ Ritual](#ritual) |
| Reference | R-XXXX | reference | [→ Reference](#reference) |
| Session | S-XXXX | session | [→ Session](#session) |
| Quest | Q-XXXX | quest | [→ Quest](#quest) |
| Other | OTH-XXXX | other | [→ Other](#other) |
| Narrative Route | NR-XXXX | narrative-route | [→ Narrative Route](#narrative-route) |

---
# 🧩 Player Character (PC)
## YAML
```yaml
---
id: "PC-XXXX"
title: "Nom du personnage"
category: "player"
status: "pending"
last_updated: "YYYY-MM-DD"
race: ""
class: ""
alignment: ""
background: ""
origin: ""
family_role: ""
speed: ""
size: ""
passive_perception: ""
hp_max: ""
ac: ""
tags:
  - "player"
---
```
## Structure
```markdown
## Résumé
## Profil & Personnalité
## Historique
## Mécaniques (caracs / maîtrises / équipement)
## Aptitudes
## Magie (optionnel)
## Actions
## Hooks
## Canon & Retcon
```
## Exemple DATA (neutre)
```markdown
---
id: "PC-1000"
title: "Personnage_A"
category: "player"
status: "pending"
last_updated: "2026-03-19"
race: "race_A"
class: "classe_A"
---

## Résumé
Brève description neutre.
```

---
# 🧩 NPC
## YAML
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
importance: ""
tags: ["npc"]
---
```
## Structure
```markdown
## Profil
## Motivations
## Secrets
## Liens
## Hooks
```
## Exemple DATA
```markdown
---
id: "N-2000"
title: "PNJ_A"
category: "npc"
status: "pending"
last_updated: "2026-03-19"
role: "fonction_A"
---

## Profil
PNJ neutre.
```

---
# 🧩 Lore Entry (L-XXXX)
## YAML
```yaml
---
id: "L-XXXX"
title: "Titre"
category: "lore"
type: "generic"
status: "pending"
last_updated: "YYYY-MM-DD"
tags: ["lore/generic"]
---
```
## Structure
```markdown
## Résumé
## Détail
## Hooks
## Canon & Retcon
```
## Exemple DATA
```markdown
---
id: "L-3000"
title: "Lore_A"
category: "lore"
status: "pending"
last_updated: "2026-03-19"
---

## Résumé
Résumé neutre.
```

---
# 🧩 Faction
## YAML
```yaml
---
id: "F-XXXX"
title: "Faction"
category: "lore"
type: "faction"
status: "pending"
last_updated: "YYYY-MM-DD"
tags: ["lore/faction"]
---
```
## Structure
```markdown
## Résumé
## Histoire & Intentions
## Actifs
## Relations
## Hooks
```
## Exemple DATA
```markdown
---
id: "F-4000"
title: "Faction_A"
category: "lore"
type: "faction"
status: "pending"
last_updated: "2026-03-19"
---

## Résumé
Faction neutre.
```

---
# 🧩 Culture
## YAML
```yaml
---
id: "C-XXXX"
title: "Culture"
category: "lore"
type: "culture"
status: "pending"
last_updated: "YYYY-MM-DD"
tags: ["lore/culture"]
---
```
## Structure
```markdown
## Aperçu
## Coutumes & Interdits
## Contacts
## Hooks
```
## Exemple DATA
```markdown
---
id: "C-5000"
title: "Culture_A"
category: "lore"
type: "culture"
status: "pending"
last_updated: "2026-03-19"
---
```

---
# 🧩 Item (Magic / mundane)
## YAML
```yaml
---
id: "M-XXXX"
title: "Item"
category: "lore"
type: "item"
status: "pending"
rarity: "common"
last_updated: "YYYY-MM-DD"
---
```
## Structure
```markdown
## Description
## Propriétés
## Origine
## Hooks
```
## Exemple DATA
```markdown
---
id: "M-6000"
title: "Item_A"
category: "lore"
type: "item"
status: "pending"
last_updated: "2026-03-19"
rarity: "common"
---
```

---
# 🧩 Event
## YAML
```yaml
---
id: "E-XXXX"
title: "Événement"
category: "event"
status: "pending"
last_updated: "YYYY-MM-DD"
date_in_world: "YYYY-MM-DD"
---
```
## Structure
```markdown
## Description
## Conséquences
## Backlinks
```
## Exemple DATA
```markdown
---
id: "E-7000"
title: "Evenement_A"
category: "event"
status: "pending"
last_updated: "2026-03-19"
---
```

---
# 🧩 Organization
## YAML
```yaml
---
id: "O-XXXX"
title: "Organisation"
category: "lore"
type: "organization"
status: "pending"
last_updated: "YYYY-MM-DD"
---
```
## Structure
```markdown
## Doctrine
## Membres clés
## Ressources
## Hooks
```
## Exemple DATA
```markdown
---
id: "O-8000"
title: "Organisation_A"
category: "lore"
type: "organization"
status: "pending"
last_updated: "2026-03-19"
---
```

---
# 🧩 Region
## YAML
```yaml
---
id: "RGN-XXXX"
title: "Région"
category: "lore"
type: "region"
status: "pending"
last_updated: "YYYY-MM-DD"
---
```
## Structure
```markdown
## Aperçu
## Points notables
## Risques
```
## Exemple DATA
```markdown
---
id: "RGN-9000"
title: "Region_A"
category: "lore"
type: "region"
status: "pending"
last_updated: "2026-03-19"
---
```

---
# 🧩 Ritual
## YAML
```yaml
---
id: "RTL-XXXX"
title: "Rituel"
category: "lore"
type: "ritual"
status: "pending"
last_updated: "YYYY-MM-DD"
cost: ""
risk: ""
---
```
## Structure
```markdown
## Procédure
## Effets
## Contreparties
```
## Exemple DATA
```markdown
---
id: "RTL-9100"
title: "Rituel_A"
category: "lore"
type: "ritual"
status: "pending"
last_updated: "2026-03-19"
cost: ""
risk: ""
---
```

---
# 🧩 Reference
## YAML
```yaml
---
id: "R-XXXX"
title: "Référence"
category: "reference"
status: "pending"
last_updated: "YYYY-MM-DD"
influence_mode: "SOFT"
---
```
## Structure
```markdown
## Profil
## INCLUDED
## EXCLUDED
## Exemples d'utilisation
```
## Exemple DATA
```markdown
---
id: "R-9200"
title: "Reference_A"
category: "reference"
status: "pending"
last_updated: "2026-03-19"
influence_mode: "SOFT"
---
```

---
# 🧩 Session
## YAML
```yaml
---
id: "S-XXXX"
title: "Session"
category: "session"
status: "active"
last_updated: "YYYY-MM-DD"
---
```
## Structure
```markdown
## Agenda
## Changements
## Créations/Modifs
## Résumé fin de session
## Seeds (3–5)
```
## Exemple DATA
```markdown
---
id: "S-9300"
title: "Session Initiale"
category: "session"
status: "active"
last_updated: "2026-03-19"
---
```

---
# 🧩 Quest
## YAML
```yaml
---
id: "Q-XXXX"
title: "Quête"
category: "quest"
status: "pending"
last_updated: "YYYY-MM-DD"
scope: "moyen"
---
```
## Structure
```markdown
## Objectif
## Jalons
## Récompenses / changements d'état
## Backlinks
```
## Exemple DATA
```markdown
---
id: "Q-9400"
title: "Quete_A"
category: "quest"
status: "pending"
last_updated: "2026-03-19"
---
```

---
# 🧩 Other
## YAML
```yaml
---
id: "OTH-XXXX"
title: "Autre"
category: "other"
status: "pending"
last_updated: "YYYY-MM-DD"
---
```
## Structure
```markdown
## Description
## Fonctionnement
## Interactions
## Hooks
```
## Exemple DATA
```markdown
---
id: "OTH-9500"
title: "Autre_A"
category: "other"
status: "pending"
last_updated: "2026-03-19"
---
```

---
# 🧩 Narrative Route (NR)
## YAML
```yaml
---
id: "NR-XXXX"
title: "Trajet narratif"
category: "narrative-route"
status: "pending"
last_updated: "YYYY-MM-DD"
start: ""
destination: ""
scope: ""
beats_target: 5
constraints:
  must_include: []
  must_avoid: []
  themes: []
  tone: "mix"
  risk: "moyen"
---
```
## Structure
```markdown
## Waypoints
## Beats
## Branches
## États modifiés
## À préparer
```
## Exemple DATA
```markdown
---
id: "NR-9600"
title: "Route_A"
category: "narrative-route"
status: "pending"
last_updated: "2026-03-19"
start: ""
destination: ""
beats_target: 5
---
```
