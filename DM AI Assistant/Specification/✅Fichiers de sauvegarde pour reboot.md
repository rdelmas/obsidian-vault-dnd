# ✅ **C’est à toi de générer les fichier s
Exemple :! `02_Settings_Mechanics.md`…

… MAIS le Storyweaver peut le générer automatiquement pour toi, sur demande.**

Autrement dit :

- **Tu fournis les paramètres mécaniques (une seule fois, ou quand tu veux les changer).**
- **Le Storyweaver te renvoie automatiquement un fichier `.md` propre, formaté et prêt pour Obsidian**, que tu sauvegardes ensuite dans ton Drive/Workspace.

Donc tu n’as **pas besoin de l’écrire toi-même** : tu fais une commande d’invocation, et il le produit.

---

# 🧩 Comment générer `02_Settings_Mechanics.md` ?

Très simple : tu utilises **MODE: MECHANICS CONFIG**.

## 👉 Exemple concret 
Ecrire : 

```
MODE: MECHANICS CONFIG
Party: 4 joueurs niv. 5
Style: Mix (RAW majoritaire)
Sources: PHB + SRD
Stat-blocking: suggestion
Dice: never
Action: Génère le fichier 02_Settings_Mechanics.md
```

Et le Storyweaver doit répondre comme :

> `id: SETTINGS-MECH-0001`
> 
> `title: "Paramètres mécaniques DnD 5e"`
> 
> `category: settings`
> 
> `status: validated`
> 
> `last_updated: 2026-03-16`
> 
> `source: conversation`
> 
> `tags: ["settings/mechanics","status/validated"]`
> 
> # Paramètres mécaniques DnD 5e
> 
> 
> ## Composition du groupe
> 
> - 4 joueurs, niveau 5
>   
> 
> ## Style de jeu
> 
> - Mix (RAW majoritaire)
> 
> ## Sources autorisées
> 
> - SRD
> 
> - Player’s Handbook
> 
> ## Stat-blocking
> 
> - Suggestion (non strict, précis si demandé)
> 
> ## Jets de dés
> 
> - Aucune simulation (never)
> 
> ## Notes
> 
> - Ces paramètres s’appliquent uniquement quand la mécanique est explicitement demandée.
> 
> - Par défaut, Storyweaver reste 100% orienté worldbuilding.


Et tu n’as plus qu’à :

- soit **copier/coller** dans ton fichier `02_Settings_Mechanics.md` dans Drive
- soit demander à Gemini (si connecté à Drive Workspace) de **créer le fichier** pour toi.

---



# 🧭 Et si on veut les modifier plus tard ?

Tu écris par exemple :

```
MODE: MECHANICS CONFIG
Update: Jets de dés = on request
Action: Mets à jour 02_Settings_Mechanics.md et renvoie la nouvelle version .md
```

→ Le Storyweaver renverra le fichier complet mis à jour  
→ Tu le colles à la place de l’ancien dans ton Drive/Obsidian

---

# 🧱 Où se place ce fichier dans le workflow ?

Dans ton dossier Bootstrap :

```
01_Master_Prompt.md
02_Settings_Mechanics.md     ← celui dont tu parles
03_Reference_Ledger.md
04_Lore_Validated/
05_Lore_Pending/
06_Session_Summaries/
07_Index.csv
```

Le `02_Settings_Mechanics.md` fait partie des **fichiers permanents** que tu recharges si tu dois régénérer l’assistant.


# 🤖 Résumé simple

### ❓ Est-ce que Storyweaver sauvegarde les mécaniques automatiquement ?

➡️ **Oui**, mais **sur demande**, via un fichier `.md`.

### ❓ Est-ce que c’est toi qui dois "écrire" le fichier ?

➡️ **Non, Storyweaver l’écrit entièrement à ta place.**

### ❓ Comment déclencher la génération ?

➡️ Avec une commande `MODE: MECHANICS CONFIG` + `Action: Génère le fichier`.