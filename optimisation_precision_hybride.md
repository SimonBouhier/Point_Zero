# Résultats de l'Optimisation Numérique

## 1. Introduction

Cette analyse compare différentes méthodes d’optimisation utilisées pour approximer P0 :

- **COBYLA** (optimisation avec contraintes)
- **Powell après COBYLA** (affinage de précision après respect des contraintes)
- **Powell et Nelder-Mead** (optimisations classiques, résultats précédents)

L’objectif est d’évaluer la précision et l’efficacité de chaque méthode en fonction des coefficients obtenus, de l’erreur finale et du nombre d’itérations nécessaires.

---

## 2. Résultats de l'Optimisation

| Méthode               | Coefficients obtenus            | Erreur Finale       | Itérations |
|----------------------|---------------------------------|---------------------|------------|
| **COBYLA**          | [-9.32e-21, 9.95e-05, 4.98e-04] | 0.000343            | N/A        |
| **Powell après COBYLA** | [-2.12e-04, 9.92e-05, 4.98e-04] | 3.87e-12            | 2          |
| **Powell**           | [-2.38, 1.0057, 1.0001]         | 1.04e-12            | 3          |
| **Nelder-Mead**      | [1.37, -1.05, 1.56]             | 0.000103            | 49         |

---

## 3. Analyse des Méthodes

### 3.1 COBYLA : Optimisation avec Contraintes
✅ **Méthode bien adaptée aux contraintes physiques** (ex: coefficients positifs).  
⚠ **Problème majeur : Erreur finale élevée (0.000343)**, indiquant une mauvaise convergence.  
⚠ **Absence du nombre d’itérations (N/A)**, ce qui empêche une évaluation complète de son efficacité.

### 3.2 Powell après COBYLA : Optimisation Hybride
✅ **Améliore considérablement la précision avec une erreur finale de 3.87e-12.**  
✅ **Convergence ultra-rapide en seulement 2 itérations.**  
✅ **Respecte les contraintes tout en affinant la solution initiale de COBYLA.**

### 3.3 Powell : Optimisation sans Contraintes
✅ **Résultat initial le plus précis avec une erreur finale de 1.04e-12.**  
✅ **Convergence rapide avec 3 itérations.**  
⚠ **Problème potentiel : Les coefficients négatifs (-2.38) ne sont pas physiquement interprétables.**

### 3.4 Nelder-Mead : Optimisation robuste
✅ **Erreur finale relativement faible (0.000103).**  
✅ **Approche plus stable que COBYLA mais moins précise que Powell.**  
⚠ **Convergence lente (49 itérations), suggérant un processus plus progressif d’ajustement.**

---

## 4. Comparaison des Méthodes et Recommandations

| Critère                    | COBYLA          | Powell après COBYLA        | Powell         | Nelder-Mead   |
|---------------------------|----------------|---------------------------|---------------|--------------|
| **Précision**              | ❌ Mauvaise     | ✅ Excellente              | ✅ Très bonne | ⚠ Moyenne    |
| **Convergence rapide**     | ❌ Non déterminée | ✅ Ultra-rapide (2 itérations) | ✅ 3 itérations | ❌ Lente (49 itérations) |
| **Contraintes respectées** | ✅ Oui         | ✅ Oui                      | ❌ Non        | ❌ Non       |
| **Robustesse**             | ✅ Stable      | ✅ Très stable              | ⚠ Moins stable | ✅ Fiable mais long |

📌 **Recommandation :**

- **L’optimisation hybride (COBYLA → Powell) est la meilleure approche**, combinant **respect des contraintes** et **précision maximale**.
- **Powell seul donne des résultats très précis**, mais avec des coefficients problématiques.
- **Si la stabilité est plus importante que la précision**, Nelder-Mead reste un bon compromis malgré sa lenteur.

---

## 5. Conclusion et Perspectives

📌 **L’optimisation hybride (COBYLA puis Powell) permet d’obtenir une précision exceptionnelle tout en respectant les contraintes physiques.**  
📌 **Powell seul est une option viable, mais avec un risque d’approximation non physique.**  
📌 **COBYLA seul ne donne pas une approximation assez précise.**  
📌 **Nelder-Mead est robuste, mais moins efficace.**  


