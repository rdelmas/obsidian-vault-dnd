---
id: "SPINE-CONTREPOINT-ACT1-v4.0"
title: "SPINE — Contrepoint – Les Coutures du Monde (Acte I)"
category: "spine"
status: "active"
last_updated: "2026-03-22"
file_role: "spine"
placeholders:
  VILLAGE_CIBLE: "⚑_A définir"
  SITE_CEREMONIE: "⚑_A définir"
  PRETEXTE_CEREMONIE: "⚑_A définir"
  BARON_A: "⚑_A définir"
  BARON_B: "⚑_A définir"
  MARTEAU_LARME: "⚑_A définir"
  FORME_AUDIENCE: "⚑_A définir"
  RELAI_ENTREPOT_NOM: "⚑_A définir"
  TEMOIN_BATELIER_NOM: "⚑_A définir"
  CAPITAINE_PATROUILLE_NOM: "⚑_A définir"
  CLERC_SUBALTERNE_NOM: "⚑_A définir"
runtime_state:
  last_checkpoint: "ARC-01.SCENE-01"
  last_user: "⚑_A définir"
  last_update: "2026-03-22"
---

# SPINE — Contrepoint – Les Coutures du Monde (Acte I)

## TL;DR (campagne)
- [1] ⚑

## Arcs
- **ARC-01** — Titre : Les Coutures du Monde (Acte I)
  **beats_hint** : [Beat1 ouverture, Beat2 incident, Beat3 pression, Beat4 fracture, Beat5 arbitrage]

## Scènes (format canon)

### ARC-01.SCENE-01 — Parade & Audience (installer la Guerre Froide)
- - **Cadre :** Halle / Quais de Beaulys — Émissaire d’Edelmark ; marchands furieux. 
- - **Objectifs MJ :** feeling **conflit larvé** ; Ysandre **ferme** mais **sous pression**. 
- - **Déclencheurs :** plaintes de péages ; escorte lourde ; protocole cassant. 
- - **Éléments concrets (preuves/effets/témoins) :** discours martiaux ; regards glacés ; promesse d’Ysandre de **renforcer** les routes. 
- - **Orientations MJ (fail-forward) :** prévôt → **[VILLAGE_CIBLE]** ou **convoi suspect** (ouvre Sc.2). 
- - **Complications :** duel rhétorique ; guilde hostile. 
- - **Sorties (états narratifs) :** incident majeur imminent ; tout est politique. 
- - **Flash 10s :** *« Les bannières claquent, les marchands crient, Ysandre promet des renforts — l’air sent la guerre froide. »*

<!-- STORYWEAVER_STOP: ARC-01.SCENE-01 -->

### ARC-01.SCENE-02 — Désastre spectaculaire (incidents extraordinaires)
- - **Cadre :** environs de **[VILLAGE_CIBLE]**. 
- - **Objectifs MJ :** montrer **le danger** sans expliquer la cause. 
- - **Déclencheurs :** cloches ; affrontements ; bêtes paniquées. 
- - **Éléments concrets (preuves/effets/témoins) :** **cages bâchées** vides ; chariots grillagés ; batelier **[TEMOIN_BATELIER_NOM]** paniqué. 
- - **Orientations MJ (fail-forward) :** **[RELAI_ENTREPOT_NOM]** (piste **Larme**) **ou** **[SITE_CEREMONIE]** (piste cérémonie). 
- - **Complications :** milice nerveuse ; bêtes résiduelles. 
- - **Sorties (états narratifs) :** 2 routes : **relais Larme** (Sc.4 amont) **ou** **cérémonie** (Sc.4). 
- - **Flash 10s :** *« Le village est vide. Des cages renversées, du sang, un batelier tremble : “On m’a payé triple pour ces caisses…” »*

### ARC-01.SCENE-03 — Secours sabordé (promesse → contre‑ordre)
- - **Cadre :** cour de chancellerie ; route de patrouille. 
- - **Objectifs MJ :** **visualiser** le sabotage interne (sans nommer). 
- - **Déclencheurs :** ordre public d’Ysandre ; **[CAPITAINE_PATROUILLE_NOM]** prêt à partir. 
- - **Éléments concrets (preuves/effets/témoins) :** capitaine renvoyé “par prudence” ; troupe **fait demi‑tour** à une borne ; sous‑officiers répètent **la même formule**. 
- - **Orientations MJ (fail-forward) :** **voir** la **[PRETEXTE_CEREMONIE]** sur **[SITE_CEREMONIE]** ou **perquisitionner [RELAI_ENTREPOT_NOM]**. 
- - **Complications :** **[BARON_A]** veut prendre la main ; embuscade d’hommes de main. 
- - **Sorties (états narratifs) :** suspicion **saboteur interne**. 
- - **Flash 10s :** *« Le capitaine broie sa gantelet : “On nous a fait tourner ! Ordre de prudence…” »*

### ARC-01.SCENE-04 — Cérémonie‑piège (débordement différé)
- - **Cadre :** **[SITE_CEREMONIE]** ; bannières et tribunes. 
- - **Objectifs MJ :** spectacle + **accusation publique**. 
- - **Déclencheurs :** étendards levés ; serments ; cloches. 
- - **Action :** **lâcher** de **retombées** capturées J‑10/J‑7 → carnage localisé. 
- - **Éléments concrets (preuves/effets/témoins) :** bâches déchirées ; loquets ; attelages ; nervis portant la **goutte de fer**. 
- - **Orientations MJ (fail-forward) :** **poursuite** des nervis vers **[RELAI_ENTREPOT_NOM]** **ou** **audience** pour contester l’accusation (Sc.6). 
- - **Complications :** émeute ; chevaliers d’Edelmark accusent les PJ ; foule. 
- - **Sorties (états narratifs) :** “Valdorian = **nouvelle arme**” devient **narratif public**. 
- - **Flash 10s :** *« Au juron des tambours, les cages cèdent — des bêtes fracassent la haie d’honneur. Les étendards tombent, l’accusation fuse. »*

### ARC-01.SCENE-05 — Courant de destitution (Osmard “solution neutre”)
- - **Cadre :** salon de **[BARON_A]**/**[BARON_B]** ; marché ; tribune. 
- - **Objectifs MJ :** montrer **le bénéficiaire**. 
- - **Déclencheurs :** motion symbolique ; “Ysandre nous laisse périr !”. 
- - **Éléments concrets (preuves/effets/témoins) :** réunions cadrées ; mêmes éléments de langage (“stabilité”, “prudence”) ; cartes de “sécurité” **inefficaces**. 
- - **Orientations MJ (fail-forward) :** intendant **cite** le Sous‑Chancelier adjoint (→ Sc.6) ; marchand dévoile un **calendrier** aligné avec les coups de **[MARTEAU_LARME]** (→ Sc.4 bis relai). 
- - **Complications :** duel d’arguments ; pression pour l’intérim **Osmard**. 
- - **Sorties (états narratifs) :** “**Osmard**” devient **intérim plausible**. 
- - **Flash 10s :** *« “L’ordre ! la stabilité !” — et un nom tombe, raisonnable : Osmard. »*

### ARC-01.SCENE-06 — Audience finale (**[FORME_AUDIENCE]**) — Deux voies de victoire
- - **Cadre :** salle d’audience (**[FORME_AUDIENCE]**). 
- - **Objectifs MJ :** **choix** du dénouement. 
- **VOIE A — Démanteler la Larme** : produire **cages**, **attelages**, **nervis**, **[RELAI_ENTREPOT_NOM]** → la Larme **déplace** des **retombées** d’un incident **antérieur**. 
- **VOIE B — Exposer la chaîne** : **témoins** (**[TEMOIN_BATELIER_NOM]**, **[CAPITAINE_PATROUILLE_NOM]**, **[CLERC_SUBALTERNE_NOM]**), **objets** (goutte, bâches), **calendriers** (convocations, cérémonies) → **Edelmark** avait **prétexte** (**[PRETEXTE_CEREMONIE]**) et **intérêt** ; **Osmard** a **saboté** la défense ; la **Larme** a **orchestré**. 
- - **Orientations MJ (fail-forward) :** si une pièce manque, **légat** accepte **1 témoin** supplémentaire (au choix du MJ). 
- - **Complications :** rhétorique agressive ; barons menacent. 
- - **Sorties (états narratifs) :** A) incidents taris → destitution échoue. B) saisine royale → **Osmard** & complices **pris en charge** ; Edelmark **désavoué**. 
- - **Flash 10s :** *« Sur la table : cages, bâches, jeton, témoins. Le légat pèse le politique : la salle retient son souffle. »*

---
## Beats → Scènes (mapping)
- Beat 1 : ARC-01.SCENE-01
- Beat 2 : ARC-01.SCENE-02
- Beat 3 : ARC-01.SCENE-04 (cérémonie) **ou** ARC-01.SCENE-03 (secours sabordé), selon choix PJ
- Beat 4 : ARC-01.SCENE-05 (destitution) + retour ARC-01.SCENE-04 (relai)
- Beat 5 : ARC-01.SCENE-06 (audience finale)

---
## Références chargées (Lore / PNJ / Lieux)
- [[L‑000X_…]]  

---
## Index Global (VALIDÉ uniquement)
> Ne lister ici **que** les éléments validés (nom — type — date_validation — lien).
- ⚑