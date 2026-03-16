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