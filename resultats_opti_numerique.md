Résultats de l'Optimisation Numérique

## 1. Introduction

Cette analyse compare différentes méthodes d’optimisation utilisées pour approximer P0 :

- **COBYLA** (optimisation avec contraintes)
- **Powell après COBYLA** (affinage de précision après respect des contraintes)
- **Trust-Constr et L-BFGS-B** (méthodes avancées testées récemment)
- **Powell et Nelder-Mead** (optimisations classiques, résultats précédents)

L’objectif est d’évaluer la précision et l’efficacité de chaque méthode en fonction des coefficients obtenus, de l’erreur finale et du nombre d’itérations nécessaires.

---

## 2. Résultats de l'Optimisation

| Méthode               | Coefficients obtenus            | Erreur Finale       | Itérations |
|----------------------|---------------------------------|---------------------|------------|
| **COBYLA**          | [-9.32e-21, 9.95e-05, 4.98e-04] | 0.000343            | N/A        |
| **Powell après COBYLA** | [-2.12e-04, 9.92e-05, 4.98e-04] | 3.87e-12            | 2          |
| **Trust-Constr**     | [7.28e-05, 8.46e-05, ...]       | 2.21e-04            | 18         |
| **L-BFGS-B**        | [0.0, 0.0, 0.0004536]           | 3.46e-09            | 6          |
| **Powell**           | [-2.38, 1.0057, 1.0001]         | 1.04e-12            | 3          |
| **Nelder-Mead**      | [1.37, -1.05, 1.56]             | 0.000103            | 49         |

---

## 3. Validation Finale de P0

🔹 **M0 sous forme fractionnaire** : \( \frac{19240741}{19980} \) = 963.00005005005  
🔹 **P0 recalculé à partir de sin(2πM0)** : \( 0.0003144737335981597132518461368277939982363022863864898681640625 \)  
🔹 **P0 utilisé précédemment** : \( 0.0003144737335981597132518461368277939982363022863864898681640625 \)  
🔹 **Erreur absolue** : \( 0E-64 \)  
🔹 **Erreur relative** : \( 0 \)  

✅ **Aucune différence significative, la valeur de P0 est rigoureusement stable.**

---

## 4. Décision Finale et Mise à Jour du Dépôt GitHub

📌 **L’optimisation hybride (COBYLA puis Powell) est confirmée comme la meilleure approche, garantissant une précision exceptionnelle et un respect des contraintes.**  
📌 **Trust-Constr et L-BFGS-B n’ont pas surpassé Powell après COBYLA, bien qu’ils offrent des alternatives intéressantes.**  
📌 **Les valeurs de P0 sont rigoureusement stables, validant ainsi l’ensemble des calculs effectués.**  

🚀 **Prochaine étape : Mise à jour du dépôt GitHub `Point_Zero` avec les fichiers suivants :**  
✅ `Analyse_P0_Numerique.py` avec l’optimisation validée.  
✅ `analysis_P0_results.csv` et `optimisation_numerique_P0.csv` avec les nouvelles valeurs.  
✅ `README.md` mis à jour pour documenter la méthodologie et les résultats.  
✅ `BILAN_08_02_25.txt` et `Interactions_P0_strc_frac.txt` révisés pour refléter les dernières avancées.  

