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


---

> `Remplissage du Fichier par IA`

# 🧭 **Étape 1 — Définir tes préférences mécaniques générales**

Je te pose quelques questions simples. Tu peux répondre point par point.

Je t’explique ce que chaque réglage implique dans ton workflow.

---

## 🎲 1. Composition du groupe

Même si l’assistant n'est pas ton DM, connaître ce paramètre lui permet :

- d’adapter subtilement la **dramaturgie** (enjeux plausibles à ce niveau)
- de calibrer les **propositions mécaniques** quand tu les demandes

👉 **Quel est ton groupe habituel ?**  
(par exemple : “4 joueurs niveau 3”, ou “5 joueurs niveau 7”, etc.)

---

## 📘 2. Style de règles souhaité

Cela définit comment l’assistant te proposera des éléments mécaniques lorsqu’il doit en générer (stat-blocks, difficultés, actions, effets).

### Choix possibles :

- **RAW** (Rules As Written) : fidèle strictement aux règles officielles.
- **Rule‑of‑Cool** : priorité au fun, mécanique simplifiée.
- **Mix (par défaut)** : RAW pour les points techniques, Rule‑of‑Cool pour le reste.

👉 **Quel style veux-tu ?**

---

## 📚 3. Sources autorisées

Cela définit ce que l’assistant peut référencer sans violer le canon.

### Options :

- **SRD only** (par défaut : 100% légal et safe)
- **PHB + SRD**
- **PHB + X + Homebrew OK**
- **Homebrew étendu** (beaucoup de créations originales)

👉 **Quelles sources veux-tu autoriser ?**

---

## ⚔️ 4. Niveau de précision mécanique (stat‑blocking)

Comment veux-tu que l’assistant génère les créatures, objets, capacités, etc. ?

- **Précis** : stat-block complet (long)
- **Abstrait** : description générale + suggestions mécaniques
- **Suggestion** (par défaut) : quelques éléments précis si nécessaire, mais pas plus

👉 **Quel niveau ?**

---

## 🎲 5. Gestion des jets de dés

Veux-tu que l’assistant résolve des jets ?

- **simulate** : l’IA lance les dés pour les PNJ
- **never** (par défaut) : jamais de jets automatiques
- **on request** : uniquement quand tu le demandes explicitement

👉 **Quelle option préfères-tu ?**

---

## 🧩 6. Contexte mécanique hors-session

L’assistant peut faire deux choses :

1. **Analyser les mécaniques** quand tu le demandes (ex : “équilibre-moi cette créature”)
2. **Ne jamais proposer de mécanique de lui-même** sauf si tu le sollicites.

👉 Veux-tu garder ce comportement par défaut ?  
(**Oui** = il reste focalisé worldbuilding  
**Non** = il pourra te proposer parfois des options mécaniques spontanées)