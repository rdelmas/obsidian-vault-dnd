
```statblock
image: [[grabuge.png]]
name: Grabuge
size: Medium
type: Humanoide
subtype: Gobelinoide
alignment: Chaotic Mauvais
ac: 16
hp: 50
hit_dice: 9d8+5
speed: 9m
stats: [15, 14, 13, 8, 11, 9]
saves:
  - Pas de bonus
skillsaves:
  - Discrétion: 6
  - Survie: 2
senses: Vision nocturne 18m, Perception passive 10
languages: Commun, Gobelin
cr: 1

traits:
  - name: Bras-longs.
    desc: une attaque au corps à corps lors de son tour, son allonge est augmentée de 1,5m (total 3m)
  - name: Vibration de la réalité.
    desc: Les attaques à distance (flèches, sorts à jet d'attaque) ont un **Désavantage** contre Grabuge.
  - ...
actions:
  - name: Masse d'arme.
    desc: Attaque d'arme au corps à corps :* +4 au toucher, portée 3 m (pendant son tour). Si touché inflige 9 (2d6+2) + Echo
  - name: Echo.
    desc: La cible subit 2 (1d4) dégâts de force supplémentaires au début de son prochain tour.
  - name: Cri de l'origine. (recharge 5-6)
    desc: Grabuge émet un hurlement qui semble se répercuter contre les murs d'une réalité invisible. Chaque créature dans un rayon de **6 m** (4 cases) doit réussir un JS Constitution DD 12.
     **Échec :** La vitesse de la cible est réduite de moitié et elle ne peut plus utiliser de Réaction jusqu’à la fin de son prochain tour.
legendary_actions:
  - name: Dephasage (1/round)
    desc: Grabuge se déplace de 4,5 m sans provoquer d'attaques d'opportunité. Il semble "glisser" dans la réalité.
  - ...
```