# Planning du projet – SAÉ S1.02 : Jeu de Grundy

**Formation :** BUT Informatique – IUT de Vannes  
**Année universitaire :** 2026-2027  
**Date limite du rendu :** vendredi 22 janvier 2027 à 23h55  
**Membres du projet :** à compléter

> Ce planning reprend les étapes demandées dans le sujet de la SAÉ. Les cases peuvent être cochées directement dans GitHub.

## Vue d'ensemble

- [x] Phase 1 – Préparation et compréhension du sujet
- [x] Phase 2 – Version 0 : algorithme brut
- [ ] Phase 3 – Version 1 : mémorisation des positions perdantes
- [ ] Phase 4 – Version 2 : mémorisation des positions gagnantes et perdantes
- [ ] Phase 5 – Version 3 : suppression des tas perdants
- [ ] Phase 6 – Version 4 : simplification des couples de tas gagnants
- [ ] Phase 7 – Rapport PDF et comparaison des résultats
- [ ] Phase 8 – Vérifications finales et dépôt sur Moodle

---

## 1. Préparation et compréhension du projet

**Objectif :** comprendre le jeu, le code de départ et les consignes avant de commencer les développements.

- [x] Lire entièrement le sujet de la SAÉ.
- [x] Comprendre les règles du jeu de Grundy.
- [x] Comprendre les notions de position gagnante et de position perdante.
- [ ] Comprendre le rôle de `playToWin()`.
- [ ] Comprendre le fonctionnement récursif de `isConfigALosingOne()`.
- [ ] Récupérer et étudier `GrundyRecBasic.java`.
- [x] Tester le programme fourni.
- [x] Créer et organiser le projet Java.
- [ ] Répartir les tâches si le projet est réalisé en binôme.

**Livrable / résultat attendu :** code de départ compris et environnement de travail prêt.

## 2. Version 0 – Algorithme brut

**Classe :** `GrundyRecBasicEff.java`

### 2.1 Développement du jeu

- [ ] Créer la classe `GrundyRecBasicEff`.
- [ ] Reprendre les méthodes nécessaires du programme de base.
- [ ] Programmer `theGame()` : jeu entre l'utilisateur et la machine.
- [ ] Utiliser `playToWin()` pour que la machine joue un coup gagnant lorsqu'il en existe un.
- [ ] Programmer un coup aléatoire lorsque `playToWin()` ne trouve pas de coup gagnant.
- [ ] Vérifier que le jeu se déroule correctement.
- [ ] Vérifier que l'IA choisit un coup gagnant lorsqu'elle le peut.

### 2.2 Mesures de performances

- [ ] Déclarer le compteur global `long cpt`.
- [ ] Incrémenter le compteur dans la boucle la plus imbriquée de la méthode récursive.
- [ ] Programmer `testConfigWinsEfficiency()`.
- [ ] Mesurer le nombre d'opérations pour chaque valeur de `n`.
- [ ] Mesurer le temps d'exécution de `configWins()`.
- [ ] Commencer les mesures à `n = 3`.
- [ ] Augmenter `n` de 1 à chaque expérience.
- [ ] Arrêter lorsque le temps de calcul devient excessif.
- [ ] Reporter les résultats dans un tableau en précisant l'unité de temps.

### 2.3 Présentation des résultats

- [ ] Tracer `cpt` en fonction de `n`.
- [ ] Tracer le temps d'exécution en fonction de `n`.
- [ ] Commenter les résultats obtenus.

**Résultat attendu :** une version fonctionnelle du jeu et une première étude des performances de l'algorithme brut.

## 3. Version 1 – Mémorisation des positions perdantes

**Classe :** `GrundyLosingPositions.java`

### 3.1 Développement

- [ ] Créer la nouvelle classe autonome.
- [ ] Reprendre les fonctionnalités nécessaires de la version 0.
- [ ] Créer le tableau global `ArrayList<ArrayList<Integer>> posPerdantes`.
- [ ] Programmer `isLosingConfig()`.
- [ ] Normaliser les configurations avant leur mémorisation.
- [ ] Supprimer les tas de 1 et de 2 lors de la normalisation.
- [ ] Trier les tas par ordre croissant.
- [ ] Vérifier si une configuration est déjà connue comme perdante avant de lancer les décompositions récursives.
- [ ] Ajouter les nouvelles configurations perdantes après normalisation.
- [ ] Éviter les doublons.

### 3.2 Tests et mesures

- [ ] Vérifier le fonctionnement du jeu et de l'IA.
- [ ] Programmer `testConfigWinsEfficiency()`.
- [ ] Vider `posPerdantes` avant chaque nouvelle expérience.
- [ ] Mesurer le nombre d'opérations et le temps d'exécution.
- [ ] Réaliser les deux graphiques.
- [ ] Comparer les résultats avec la version 0.
- [ ] Rédiger un commentaire comparatif.

**Résultat attendu :** éviter de recalculer les configurations perdantes déjà mémorisées.

## 4. Version 2 – Mémorisation des positions gagnantes et perdantes

**Classe :** `GrundyRecLosingAndWinning.java`

### 4.1 Développement

- [ ] Créer la nouvelle classe autonome.
- [ ] Reprendre le principe de mémorisation de la version 1.
- [ ] Conserver le tableau des positions perdantes.
- [ ] Créer un tableau des positions gagnantes.
- [ ] Modifier les vérifications pour consulter les deux tableaux avant de poursuivre les calculs récursifs.
- [ ] Ajouter les configurations gagnantes et perdantes découvertes dans les tableaux correspondants.
- [ ] Éviter les calculs déjà effectués lorsque la configuration est connue.

### 4.2 Tests et mesures

- [ ] Vérifier le fonctionnement du jeu et de l'IA.
- [ ] Programmer `testConfigWinsEfficiency()`.
- [ ] Vider les deux tableaux avant chaque nouvelle expérience.
- [ ] Mesurer le nombre d'opérations et le temps d'exécution.
- [ ] Réaliser les deux graphiques.
- [ ] Comparer les résultats avec la version 1.
- [ ] Rédiger un commentaire comparatif.

**Résultat attendu :** exploiter la mémorisation des deux catégories de positions pour réduire les calculs.

## 5. Version 3 – Conservation des positions et suppression des tas perdants

**Classe :** `GrundyRecNeutralLoser.java`

### 5.1 Développement

- [ ] Créer la nouvelle classe autonome.
- [ ] Reprendre les tableaux de positions gagnantes et perdantes de la version 2.
- [ ] Comprendre le principe du tas perdant neutre.
- [ ] Appliquer les règles `P + P = P` et `G + P = G`.
- [ ] Modifier l'algorithme pour supprimer les tas perdants connus des configurations lorsque cela est possible.
- [ ] Simplifier les configurations avant de poursuivre les calculs.
- [ ] Vérifier que la simplification conserve la nature gagnante ou perdante de la position.

### 5.2 Tests et mesures

- [ ] Vérifier le fonctionnement du jeu et de l'IA.
- [ ] Programmer `testConfigWinsEfficiency()`.
- [ ] Vider les deux tableaux avant chaque nouvelle expérience.
- [ ] Mesurer le nombre d'opérations et le temps d'exécution.
- [ ] Réaliser les deux graphiques.
- [ ] Comparer les résultats avec la version 2.
- [ ] Rédiger un commentaire comparatif.

**Résultat attendu :** réduire les configurations en supprimant les tas perdants neutres connus.

## 6. Version 4 – Simplification des couples de tas gagnants

**Classe :** `GrundyRecWplusWequalsL.java`

### 6.1 Développement

- [ ] Créer la nouvelle classe autonome.
- [ ] Reprendre les améliorations de la version 3.
- [ ] Étudier le tableau des types `T0` à `T5` fourni à la page 7 du sujet.
- [ ] Créer le tableau `int[] type`.
- [ ] Associer chaque nombre d'allumettes à son type.
- [ ] Programmer la détection de deux tas gagnants de même type.
- [ ] Appliquer les règles du sujet :
  - Deux tas gagnants de types différents donnent une position gagnante.
  - Deux tas gagnants de même type donnent une position perdante.
- [ ] Supprimer les couples de tas gagnants de même type lorsqu'ils forment une position perdante.
- [ ] Vérifier les simplifications des configurations.

### 6.2 Tests et mesures

- [ ] Vérifier le fonctionnement du jeu et de l'IA.
- [ ] Programmer `testConfigWinsEfficiency()`.
- [ ] Vider les tableaux gagnants et perdants avant chaque nouvelle expérience.
- [ ] Mesurer le nombre d'opérations et le temps d'exécution.
- [ ] Réaliser les deux graphiques.
- [ ] Comparer les résultats avec la version 3.
- [ ] Rédiger un commentaire comparatif.

**Résultat attendu :** dernière version de l'algorithme, intégrant les optimisations précédentes et la simplification par types.

## 7. Rapport PDF

**Contrainte :** 15 pages maximum.

### 7.1 Introduction

- [ ] Présenter les objectifs du projet.
- [ ] Expliquer brièvement le jeu de Grundy.
- [ ] Présenter l'objectif de comparaison des algorithmes.

### 7.2 Résultats des versions

Pour chacune des versions 0 à 4 :

- [ ] Expliquer le principe de l'algorithme et l'amélioration apportée.
- [ ] Insérer le tableau des mesures (`n`, `cpt`, temps d'exécution).
- [ ] Insérer le graphique de `cpt` en fonction de `n`.
- [ ] Insérer le graphique du temps d'exécution en fonction de `n`.
- [ ] Commenter les résultats.
- [ ] Comparer avec la version précédente.

### 7.3 Conclusion

- [ ] Comparer les performances des cinq versions.
- [ ] Identifier la version la plus efficace au regard des mesures.
- [ ] Expliquer les apports des différentes optimisations.
- [ ] Rédiger une conclusion générale.

## 8. Vérifications finales et rendu

### 8.1 Vérification des sources Java

- [ ] Les cinq classes Java sont présentes.
- [ ] Chaque classe est autonome et ne dépend pas des autres classes développées.
- [ ] Chaque classe contient `principal()`.
- [ ] Chaque classe contient `playToWin(ArrayList<Integer> jeu)`.
- [ ] Chaque classe contient `isConfigALosingOne(ArrayList<Integer> jeu)`.
- [ ] Chaque classe contient `configWins(ArrayList<Integer> jeu)`.
- [ ] Chaque classe contient `theGame()`.
- [ ] Chaque classe contient `testConfigWinsEfficiency()`.
- [ ] Les méthodes ajoutées sont testées.
- [ ] Les sources sont soignées et documentées en JavaDoc.
- [ ] La JavaDoc est rédigée en anglais.

### 8.2 Vérification du rapport

- [ ] Les cinq versions sont présentées.
- [ ] Les tableaux de mesures sont présents.
- [ ] Les graphiques sont présents.
- [ ] Les comparaisons entre versions sont commentées.
- [ ] L'introduction et la conclusion sont présentes.
- [ ] Le rapport ne dépasse pas 15 pages.
- [ ] Le rapport est exporté au format PDF.

### 8.3 Archive et dépôt

Créer une archive nommée :

`nomBinôme1_nomBinôme2.zip`

Elle doit contenir les cinq sources Java et le rapport PDF :

- [ ] `GrundyRecBasicEff.java`
- [ ] `GrundyLosingPositions.java`
- [ ] `GrundyRecLosingAndWinning.java`
- [ ] `GrundyRecNeutralLoser.java`
- [ ] `GrundyRecWplusWequalsL.java`
- [ ] `nomBinôme1_nomBinôme2.pdf`
- [ ] Vérifier que l'archive est au format `.zip` (pas `.rar`).
- [ ] Déposer l'archive sur Moodle.

**Date limite : vendredi 22 janvier 2027 à 23h55.**

---

## 9. Répartition indicative par semaine

| Période | Travail prévu |
|---|---|
| Semaine 48 | Compréhension du sujet, préparation du projet et début de la version 0 |
| Semaine 49 | Terminer la version 0 et réaliser la version 1 |
| Semaine 50 | Terminer la version 1 et réaliser la version 2 |
| Semaine 51 | Séance de soutien, questions et corrections |
| Semaine 01 | Réaliser la version 3 |
| Semaine 03 | Réaliser la version 4, terminer les mesures, finaliser le rapport et préparer le rendu |

Cette répartition est indicative et reprend les périodes de travail mentionnées dans le sujet.

## 10. Méthode de travail à appliquer à chaque version

Suivre systématiquement cet ordre :

1. Comprendre l'amélioration demandée.
2. Développer le code Java.
3. Tester le fonctionnement du programme.
4. Vérifier les décisions de l'intelligence artificielle.
5. Réaliser les mesures de performances.
6. Construire les tableaux et graphiques.
7. Rédiger le commentaire comparatif.
8. Vérifier que la version est terminée.
9. Passer à la version suivante.

> **Conseil :** ne pas attendre la fin du projet pour réaliser les mesures et les commentaires. Terminer chaque version avant de passer à la suivante permet de limiter les oublis et les retours en arrière.
