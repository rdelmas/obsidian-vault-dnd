# ✅1. Le système de notation : L‑0234, R‑0033 

Le système de notation est un **système d’identifiants courts, uniques et permanents** assignés à chaque entrée de lore ou de référence.

### 🎯 Pourquoi utiliser des ID ?

- Pour que l’assistant puisse **référencer précisément** un élément sans ambiguïté.
- Pour faciliter les **backlinks Obsidian**.
- Pour identifier facilement les fichiers lors des **EXPORT PACKS**.
- Pour garantir la **pérennité du canon** (un ID ne change jamais).

---

# 🔢 1.1. La structure d’un ID

Un ID est composé de trois parties :

```
[Prefix]-[Numéro séquentiel à 4 chiffres]
```

Exemples :

- `L-0234` → Lore Entry n°234
- `R-0033` → Reference Entry n°33
- `N-0191` → NPC Entry n°191
- `Q-0007` → Quest Entry n°7

---

# 🔤 1.2. Le préfixe

|Préfixe|Signification|Exemple|
|---|---|---|
|**L**|Lore générique (lieux, factions, événements, objets, concepts)|L-0234|
|**N**|PNJ (NPC)|N-0191|
|**R**|Référence externe (œuvres inspirantes)|R-0033|
|**Q**|Quête (Quest)|Q-0007|
|**E**|Événement majeur/historique|E-0044|
|**F**|Faction|F-0022|
|**M**|Magie, sort, objet magique|M-0068|
|**C**|Culture ou cosmologie|C-0101|

> 🧠 _Le modèle ne génère pas les IDs de façon aléatoire._  
> Il suit un **compteur interne par catégorie**, incrémenté à chaque création.

---

# 🔁 1.3. Le numéro séquentiel

- **Toujours à 4 chiffres**  
    → Pour garder l’ordre dans Obsidian et dans Drive.
- **Incrémental par catégorie**
    - N-0191 est le 191e PNJ
    - L-0234 est le 234e élément de lore générique
- **Jamais réutilisé**, même si une entrée est “Dismissed”.

---

# 🗂 1.4. Exemple réel

### Lieu : Temple des Brumes

```
id: L-0234
```

### PNJ : Prêtresse Myra

```
id: N-0191
```

### Référence : Expedition 33

```
id: R-0033
```

---

# 🏷 1.5. Convention de nommage des fichiers Obsidian

Format standard :

```
LORE_[Category]_[slug]_[ID].md
```

Exemples :

- `LORE_Location_temple-des-brumes_L-0234.md`
- `LORE_NPC_myra_L-0191.md`
- `REFERENCE_Expedition-33_R-0033.md`
- `LORE_Quest_les-cloches-silencieuses_Q-0007.md`