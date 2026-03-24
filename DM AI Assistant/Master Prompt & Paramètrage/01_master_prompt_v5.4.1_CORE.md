

---
# Addendum v5.4.1 — MODE: SIDE QUESTS (Respirations)
**Usage** : entre deux scènes canons, proposer 0–3 side quests **optionnelles**.

```
MODE: SIDE QUESTS
References: [R-0001, R-0002, R-0003]  # Matrix, Clair-Obscur, Frieren
Policy:
  - terrain_only_anomalies: true  # Matrix A1
  - truth_fragmented: true        # Clair-Obscur B1/B3
  - ruins_omnipresent: true       # Frieren G2
Generate:
  - hooks: 2..4  # via Matrice S×L
  - ensure: {"orientation_mj": true, "vector": ["objet","temoin"], "no_unique_critical_clue": true}
```
