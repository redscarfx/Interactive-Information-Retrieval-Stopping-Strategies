#  Projet RITAL – Reproduction de l’article *"Searching and Stopping: An Analysis of Stopping Rules and Strategies"*

##  Contexte
Ce projet a été réalisé dans le cadre du cours **4IN0813 – Recherche d’Information (RITAL), Sorbonne Université, 2024–2025**.  
L’objectif était de **reproduire et analyser les expériences** du papier de Maxwell et al. (*CIKM 2015*), qui étudie les **règles et stratégies d’arrêt** dans les sessions de recherche d’information :

> Maxwell, D., Azzopardi, L., Järvelin, K., & Keskustalo, H. (2015).  
> *Searching and Stopping: An Analysis of Stopping Rules and Strategies*.  
> Proceedings of the 24th ACM International on Conference on Information and Knowledge Management (CIKM).  
> [DOI: 10.1145/2806416.2806476](https://doi.org/10.1145/2806416.2806476)

## Objectifs
- Comprendre et réimplémenter plusieurs **stratégies d’arrêt** lors de la recherche d’information (Fixed Depth, Frustration/Disgust, etc.).
- Reproduire les expériences menées par les auteurs.
- Explorer et comparer les résultats avec de nouveaux jeux de données et scénarios.
- Identifier les **requêtes difficiles/faciles** et évaluer l’impact des règles d’arrêt sur la performance.

##  Organisation du projet
Le projet est implémenté dans un notebook Jupyter : [`projet.ipynb`](projet/projet.ipynb).

### Structure principale
- **A – Préparation et indexation**
  - Réduction du corpus pour accélérer l’indexation.
  - Mise à jour des qrels et queries.
- **B – Stratégies d’arrêt**
  - Détection des requêtes difficiles/faciles.
  - Classement initial avec BM25.
  - Implémentation des règles d’arrêt et calcul du **gain cumulatif moyen (CG)**.
  - Comparaison des performances sur différentes catégories de requêtes.
- **C – Interaction utilisateur**
  - Simulation et analyse des comportements d’arrêt en lien avec l’étude originale.

##  Résultats
- Les stratégies basées sur le **frustration/disgust rule** reproduisent globalement les meilleures performances, comme dans le papier.
- La règle **Fixed Depth** constitue un bon baseline et reste robuste.
- L’analyse des requêtes difficiles vs faciles permet de mieux comprendre les limites des stratégies statiques.

## Installation et exécution
### Prérequis
- Python 3.9+
- Jupyter Notebook
- Librairies principales :
  ```bash
  pip install pandas matplotlib pyterrier
