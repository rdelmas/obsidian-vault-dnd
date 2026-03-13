
```statblock
image: [[Soeur Emeline.jpg]]
name: Soeur Emeline
size: Medium
type: Humanoide
alignment: Chaotic Neutre
ac: 14
hp: 28
hit_dice: 5d8+5
speed: 9m
stats: [10, 14, 12, 13, 15, 13]
saves:
  - Sagesse: 4
  - Charisme: 3
skillsaves:
  - Intuition: 4
  - Medecine: 4
  - Discretion: 3
  - Religion: 3
senses: Perception passive 12
languages: Commun, Argot des voleurs, Celeste
cr: 1
spells:
  - Injonction (2/jour) : Sort de contrôle, portée 18 m, une cible doit réussir un JS Sagesse DD12. Si echec la cible doit obéir à un ordre d'un mot à son prochain tour (Fuis, Tombe, Assis)
    
  - Flame sacrée (mineure) : Portée 18 m. La cible doit réussir un **JS Dextérité DD 12**. *Échec :* 4 (1d8) dégâts radiants. Aucun bénéfice des abris.

actions:
  - name: Dague Empoisonnée.
    desc: Attaque d'arme au corps à corps :* +4 au toucher, portée 1.5 m. Si touché inflige 4 (1d4+2) + JS Constitution, si echec la cible subit Empoisonnée
  
bonus_actions:
  - name: Mot de guérison (2/jour)
    desc: Emeline murmure une prière. Une créature à moins de 18 m récupère 4 (1d4 + 2) PV.

reactions:
  - name: Réprimandes du silence
    desc: Lorsqu'une créature à moins de 18 m lance un sort, Emeline tente de l'interrompre. La cible doit réussir un **JS Sagesse DD 12** ou perdre l'usage de sa voix jusqu'à la fin de son tour (ce qui fait échouer les sorts avec une composante verbale).
```