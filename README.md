# TP 2 - Statistical Learning (2025)

M2 EI2D & MATD - Université Paris 13, Institut Galilée

**Noms :** ELIE Kouldjim

## Description

On compare deux modèles de classification à 3 classes (A, B, C) à partir de leurs matrices de confusion : loi de Y,
accuracy, risque empirique pour la perte 0-1 et pour une perte $\ell_2$, et fiabilité de la comparaison. On écrit ensuite une
fonction Python générale qui trouve le meilleur de deux modèles, quelle que soit la dimension $m$ des matrices.

## Fichiers

| Fichier | Contenu |
|---|---|
| `TP2_Apprentissage_Statistique.ipynb` | Notebook avec le code, les calculs et les explications |
| `TP2_Apprentissage_Statistique.pdf` | Rapport (notebook exporté en PDF) |
| `README_TP2.md` | Ce fichier |

## Exécution

```bash
pip install numpy pandas matplotlib notebook
jupyter notebook TP2_Apprentissage_Statistique.ipynb
```

Puis *Kernel → Restart & Run All*.

## Principaux résultats

| | g1 | g2 |
|---|---|---|
| Accuracy | 91.43 % | 88.57 % |
| Risque empirique (perte 0-1) | 0.0857 | 0.1143 |
| Risque empirique (perte $\ell_2$) | 0.0914 | 0.1600 |

- Loi estimée de Y sur D' (175 individus) : P(A) ≈ 0.286, P(B) = 0.400, P(C) ≈ 0.314.
- g1 est le meilleur modèle selon le risque empirique, pour les deux fonctions de perte.
- On ne peut pas affirmer que g1 est meilleur pour le vrai risque : les intervalles de confiance se chevauchent.

## Fonctions principales

| Fonction | Rôle |
|---|---|
| `loi_de_Y(M)` | Estime P(Y = y) à partir des sommes de colonnes |
| `accuracy(M)` | Taux de bonnes classifications |
| `risque_empirique(M, L)` | Risque empirique pour une matrice de perte L quelconque |
| `meilleur_modele(M1, M2, L=None)` | Exercice 2 : compare deux modèles (perte 0-1 par défaut), pour toute dimension m |
