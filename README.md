# Jeu de Grundy – SAÉ S1.02

**Comparaison d'approches algorithmiques – BUT Informatique**

Année universitaire : 2026-2027  
Établissement : IUT de Vannes – Université Bretagne Sud  
Langage utilisé : Java  
Projet réalisé dans le cadre de la SAÉ 1.02.

---

## Présentation du projet

Ce projet consiste à développer un programme Java permettant de jouer au **jeu de Grundy** contre une intelligence artificielle.

L'objectif principal est de développer plusieurs approches algorithmiques permettant de résoudre un même problème, puis de comparer leurs performances en termes de nombre d'opérations et de temps d'exécution.

Le projet repose sur une approche récursive, progressivement améliorée grâce à différentes techniques d'optimisation et de mémorisation des positions gagnantes et perdantes.

## Règles du jeu

Le jeu de Grundy se joue à deux joueurs.

Au début de la partie, un unique tas d'allumettes est présent.

À chaque tour, le joueur doit :
- Choisir un tas contenant au moins 3 allumettes.
- Le séparer en deux tas de tailles différentes.
- Passer la main au joueur suivant.

La partie continue jusqu'à ce qu'un joueur ne puisse plus effectuer de séparation.

**Le joueur qui ne peut plus jouer perd la partie.**

## Objectifs

Les objectifs du projet sont :

- Implémenter différentes stratégies algorithmiques.
- Développer une intelligence artificielle capable de choisir des coups gagnants lorsqu'ils existent.
- Étudier le fonctionnement de la récursivité.
- Optimiser progressivement les algorithmes.
- Mesurer le nombre d'opérations élémentaires.
- Mesurer les temps d'exécution.
- Comparer les performances des différentes versions à l'aide de tableaux et de graphiques.

---

## Les différentes versions

Le projet comporte cinq versions de l'algorithme.

### Version 0 – Algorithme brut

**Classe :** `GrundyRecBasicEff.java`

Première implémentation de l'algorithme récursif.

- Exploration des différentes décompositions possibles.
- Recherche d'une position perdante pour l'adversaire.
- Choix d'un coup aléatoire lorsqu'aucun coup gagnant n'est trouvé.
- Première étude des performances.

### Version 1 – Mémorisation des positions perdantes

**Classe :** `GrundyLosingPositions.java`

Cette version améliore la version 0 en conservant les positions perdantes déjà découvertes.

- Création d'un tableau de positions perdantes.
- Vérification des positions déjà mémorisées.
- Suppression des tas de 1 et de 2 lors de la normalisation.
- Tri des configurations pour faciliter les comparaisons.
- Réduction des calculs récursifs inutiles.

### Version 2 – Mémorisation des positions gagnantes et perdantes

**Classe :** `GrundyRecLosingAndWinning.java`

Cette version ajoute la mémorisation des positions gagnantes.

- Conservation des positions perdantes.
- Création d'un tableau de positions gagnantes.
- Consultation des deux tableaux avant les calculs récursifs.
- Réduction supplémentaire du nombre de calculs.

### Version 3 – Suppression des tas perdants

**Classe :** `GrundyRecNeutralLoser.java`

Cette version utilise le principe du tas perdant neutre.

Les règles appliquées sont :

- P + P = P
- G + P = G

Les tas perdants connus peuvent ainsi être supprimés d'une configuration sans modifier sa nature.

Cette simplification permet d'éviter certains calculs inutiles.

### Version 4 – Simplification des couples de tas gagnants

**Classe :** `GrundyRecWplusWequalsL.java`

Dernière version du projet. Elle reprend les améliorations précédentes et ajoute la notion de types de tas.

Les tas sont répartis en six types : T0, T1, T2, T3, T4 et T5.

Les règles supplémentaires sont :

- Deux tas gagnants de types différents donnent une position gagnante.
- Deux tas gagnants de même type donnent une position perdante.

Cette méthode permet de simplifier davantage les configurations et d'améliorer les performances de l'algorithme.

---

## Étude des performances

Pour chaque version, une étude de l'efficacité de la méthode `configWins()` est réalisée.

Deux indicateurs sont mesurés :

**1. Nombre d'opérations élémentaires**

Un compteur global `long cpt` permet de comptabiliser le nombre d'opérations effectuées dans la boucle la plus imbriquée de la méthode récursive.

**2. Temps d'exécution**

Le temps nécessaire à l'exécution de la méthode `configWins()` est mesuré pour différentes valeurs de n, correspondant au nombre initial d'allumettes.

Les expériences commencent avec n = 3, puis n augmente de 1 à chaque mesure, jusqu'à ce que le temps de calcul devienne excessif.

Pour chaque version, les résultats sont présentés sous forme de :
- Tableaux de mesures.
- Graphiques du nombre d'opérations en fonction de n.
- Graphiques du temps d'exécution en fonction de n.
- Commentaires et comparaisons avec la version précédente.

**Attention :** les tableaux de mémorisation doivent être réinitialisés avant chaque nouvelle expérience afin de garantir la fiabilité des mesures.

---

## Technologies utilisées

- **Java** : développement du jeu et des algorithmes.
- **Git** : gestion des versions du projet.
- **GitHub** : hébergement et suivi du code source.
- **Tableurs et graphiques** : présentation et comparaison des résultats expérimentaux.

---

## Organisation du projet

```text
SAE-1.02-Grundy/
│
├── README.md
│
├── src/
│   ├── GrundyRecBasicEff.java
│   ├── GrundyLosingPositions.java
│   ├── GrundyRecLosingAndWinning.java
│   ├── GrundyRecNeutralLoser.java
│   └── GrundyRecWplusWequalsL.java
│
└── documents/
    └── Rapport.pdf
```

*Cette arborescence représente l'organisation prévue du dépôt.*

---

## Installation et exécution

### Prérequis

- Disposer d'un environnement Java.
- Disposer des fichiers sources du projet.

### Récupérer le projet

```bash
git clone URL_DU_DEPOT
```

### Accéder au projet

```bash
cd SAE-1.02-Grundy
```

### Compilation

Les fichiers Java peuvent être compilés avec `javac` depuis le répertoire contenant les sources.

Exemple :

```bash
javac -d out src/GrundyRecBasicEff.java
```

Les commandes exactes d'exécution dépendent du point d'entrée défini dans chaque classe.

---

## Auteurs

Projet réalisé dans le cadre de la SAÉ S1.02 – Comparaison d'approches algorithmiques.

**Membres du projet :**
- Nom Prénom
- Nom Prénom

**Formation :** BUT Informatique  
**Établissement :** IUT de Vannes – Université Bretagne Sud  
**Année :** 2026-2027

---

## Licence

Projet pédagogique réalisé dans le cadre de la formation BUT Informatique.

