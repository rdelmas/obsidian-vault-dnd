## Workflow de travail (résumé opérationnel)

1. **Initialisation (une fois)**
    
    - Colle le **Master Prompt v2** ci‑dessus.
    - Donne (optionnel) **MECHANICS CONFIG** (style 5e).
    - Si tu as déjà des références : lance **MODE: REFERENCE FILTER** et fournis la liste à valider.
2. **Démarrage de session**
    
    - Dis : `SESSION START — Agenda: [1) Lieux, 2) Histoire PNJ X, 3) Hook principal]`
    - Le Storyweaver renverra un **Session Recap** (si continuation) + reprendra l’agenda.
3. **Création de contenu**
    
    - Pour **un lieu** :  
        `MODE: LORE ENGINE — Crée un lieu "Temple des Brumes" (mots-clés: deuil, brume, résonance), liens: PNJ Myra (si existe).` → Il doit livrer directement un **fichier .md** complet + liens/backlinks + hooks + dramaturgie.
    - Pour **de l’histoire/arc** :  
        `MODE: DRAMATURGIE — Étend l’arc “Cicatrices du monde” avec 1 foreshadowing et 2 hooks liés au Temple.`
4. **Validation & statut**
    
    - Quand un bloc te convient :  
        `VALIDE: L-0234` (ou “Valide ce fichier et prépare la version status: validated”)  
        → Le modèle renvoie **le même fichier** avec `status: validated`, `validation_source` rempli, `last_updated` rafraîchi.
    - Si tu hésites :  
        `Garde en pending et propose 2 variantes légères.`
5. **Retcon / conflits**
    
    - Si une contradiction apparaît :  
        `RETCON CHECK pour L-0234 vs N-0191`  
        → Le modèle propose (a) retcon ciblé, (b) coexistence, (c) dismiss + **Change Log**.
6. **Sauvegarde / Export**
    
    - En fin de session :  
        `MODE: EXPORT — Prépare l’EXPORT PACK (bulk .md + index CSV + session summary). Dossier cible: Worldbuilding/Exports/2026-03-16/`
    - Dans Gemini (si autorisé), demande ensuite :  
        _“Crée les fichiers du pack dans le dossier Drive ci‑dessus et génère un Google Doc ‘Session Recap — 2026‑03‑16’ avec le résumé et le Change Log.”_
7. **Régénération (si besoin)**
    
    - Dossier Bootstrap (Drive) : Master Prompt, Mechanics, Reference Ledger, Lore Validated, Lore Pending, Session Summaries, Index.csv.
    - Dans une nouvelle conversation :  
        `Charge Master Prompt. Charge Reference Ledger (validated), puis Lore Validated/*.md. Traite Lore Pending comme pending. Applique 5e Mechanics.`  
        `Canon Check — Résume en 10–15 points le canon actuel.`



--- 




## 🔁 Flux de travail recommandé 

1. **Tu donnes** : paramètres mécaniques (si besoin), références à valider, objectifs de session.
2. **Le Storyweaver** :
    - Valide les références (filtres),
    - Propose du lore **directement au format Obsidian**,
    - Ajoute dramaturgie (hooks, foreshadowing),
    - Maintient Canon/Retcon (change log),
    - Donne un **Export Pack** (liste des fichiers + contenu `.md`).
3. **Tu colles** dans Drive/Obsidian.
4. **Régénération** : tu repars du Master Prompt + dossier Bootstrap.

---

## ❓À propos du “Player Intent Detector”

Tu demandais ce que c’est : c’est un **mini-moteur d’interprétation** qui lit ce que tu viens d’écrire (la consigne juste avant) pour **estimer ta direction souhaitée** et **donner 1 prochain pas concret** (2–3 lignes).  
→ C’est **diagnostique**, pas intrusif : ça évite que le modèle parte dans la mauvaise direction, et ça te permet de dire rapidement “Oui c’est ça / non, corrige”.


## 🧩 Exemples de commandes utiles

- **Mettre à jour une référence existante**  
    `MODE: REFERENCE FILTER — Mets à jour R-0033: influence_mode=SOFT → HARD, ajoute "structure chorale" dans Included, renvoie l'entrée .md complète.`
    
- **Créer 2 lieux liés + 1 pont dramaturgique**  
    `MODE: LORE ENGINE — Crée "Clocher Fêlé" (relique) et "Crypte d’Écho" (lieu), chacun en .md, avec 1 backlink vers L-0234. Puis MODE: DRAMATURGIE — Propose un battement narratif qui relie les deux via un foreshadowing concret.`
    
- **Valider en lot**  
    `VALIDE: L-0234, N-0191, R-0033 — renvoie les .md finalisés (status: validated, validation_source rempli).`
    
- **Export pack**  
    `MODE: EXPORT — Prépare un EXPORT PACK nommé "2026-03-16" avec bulk .md (---FILEBREAK---), index CSV, session summary.`


---

# 🧩 **Workflow complet 

Voici ta pipeline de travail complète, avec l'étape d’intégration PJ ajoutée.

---

## 🟦 **1. Master Prompt v3 → Chargé en premier**

Copie-colle ton Master Prompt dans une nouvelle conversation.

---

## 🟥 **2. Charger les mécaniques (02_Settings_Mechanics.md)**

Commande type :

```
Charge le fichier 02_Settings_Mechanics.md
```

Storyweaver récapitule les paramètres.

---

## 🟧 **3. Charger les références validées (03_Reference_Ledger.md)**

```
Charge le Reference Ledger (validated seulement)
```

Storyweaver recharge la liste des influences.

---

## 🟨 **4. Charger le Lore Validé (04_Lore_Validated)**

Tu peux fournir :

- soit les fichiers `.md`
- soit un **bulk export**
- soit demander au Storyweaver :
    
    ```
    Charge tous les fichiers de 04_Lore_Validated/
    ```
    

🔥 **C’est ici que le canon se charge.**

---

## 🟩 **5. ➤ CHARGER LES PERSONNAGES (05_Players)**

C’est ici que tu dois intégrer les PJ.

### 🔥 C’est l’étape idéale parce que :

- Elle se fait **après** le canon général
- Elle se fait **avant** toute génération de contenu
- Le Storyweaver peut :
    - générer des arcs narratifs dédiés
    - intégrer les PJ dans les motifs récurrents
    - calibrer les tensions
    - proposer des lieux/PNJ liés aux backgrounds
    - stocker les fiches comme Validated Lore (avec ID PC-xxxx)

### Commande type :

```
Charge les fiches PJ suivantes en tant que Validated Lore :
- Fenryx.md
- Ouka.md
- Tyron.md
- Xar.md
- Van Elflin.md
```

Ou :

```
Voici les 5 fiches de personnages au format .md – charge-les comme Validated Lore.
```

Le Storyweaver les parse et les intègre dans la mémoire du canon.

---

## 🟦 **6. Charger le Pending Lore (06_Lore_Pending)**

Facultatif — utile si tu travailles sur des éléments non encore figés.

---

## 🟪 **7. Canon Check**

Commande :

```
Canon Check — résume en 10–15 puces les éléments centraux du canon.
```

C’est ta validation manuelle que tout a bien été chargé.

---

## 🟫 **8. SESSION START**

**Maintenant** tu peux commencer à créer ton monde / ton histoire.

```
SESSION START — Agenda: [1) Lieux, 2) Histoire Myra, 3) Première menace]
```

---

# 🧠 **Pourquoi NE PAS charger les PJ plus tard ?**

### ❌ Mauvaise idée de les charger après le début du worldbuilding

→ Le Storyweaver aura commencé à créer des arcs sans connaître les personnages.

### ❌ Mauvaise idée de les charger en même temps que le lore

→ Les PJ influencent fortement la dramaturgie.  
→ Mélanger leur import avec d’autres fichiers peut provoquer des priorités mal gérées.

### ❌ Mauvaise idée de les charger “au fil de l’eau”

→ Tu veux les inclure **dès la première génération de lieux, factions, arcs**.