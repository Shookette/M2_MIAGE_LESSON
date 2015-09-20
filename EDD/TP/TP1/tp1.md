# TP1 - Fouille de données

## 1.1 Un premier ensemble d'exemples simples

### Iris
#### Naive Bayes :
Avec cet algorithme, nous remarquons que les types d'Iris peuvent être suffisamment différenciés par la longueur de leurs pétales. En effet, malgré quelques erreurs de prédiction entre les iris versicolor et virginica, les trois groupes d'iris sont definis.

On nous indique plus précisément que dans 95.3% des cas (soit 7 erreurs), Naive Bayes classifie correctement les iris.

Vous trouverez ci-dessous un détail des prédictions (sachant que chaque espéce était représentée 50 fois).

| | Setosa | Versicolor | Virginica |
|---|---|---|---|
| Setosa | 50 | 0 | 0 |
| Versicolor | 0 | 47 | 3 |
| Virginica | 0 | 4 | 46 |

#### k-NN :
Grâce à cet algorithme, on peut choisir le k. Avec des k comme 1, 3, 5 ou 9, on obtient le même pourcentage d'erreurs qu'avec Naive Bayes.  
Cepandant, avec un k=7, l'algorithme a pu correctement classer les iris dans 96,6% des cas (soit 5 erreurs).

| | Setosa | Versicolor | Virginica |
|---|---|---|---|
| Setosa | 50 | 0 | 0 |
| Versicolor | 0 | 49 | 1 |
| Virginica | 0 | 4 | 46 |

#### C4.5 :
Cet algorithme nous permet de décrire la classification des espèces d'iris grâce à un arbre de décision que vous trouverez ci-dessous.

![Image](Iris-C4.5.png)

Concernant le taux de bonne classification, il est égal aux autres à 95,3%.  
Vous trouverez ci-dessous la matrice de confusion.

| | Setosa | Versicolor | Virginica |
|---|---|---|---|
| Setosa | 49 | 1 | 0 |
| Versicolor | 0 | 47 | 3 |
| Virginica | 0 | 3 | 47 |

On remarque ici qu'un Setosa a été confondu pour un Versicolor alors qu'avec tous les autres algorithmes, nous ne trouvons aucune confusion concernant cette espèce.

#### SVMs :
Avec cette algorithme, nous obtenons le meilleur pourcentage de bonne classification avec 97,3% (soit 4 erreurs).

Voici la formule utilisée pour cet algorithme : weka.classifiers.functions.LibSVM -S 0 -K 2 -D 3 -G 0.0 -R 0.0 -N 0.5 -M 40.0 -C 1.0 -E 0.001 -P 0.1 -seed 1

Vous trouverez ci-dessous la matrice de confusion.

| | Setosa | Versicolor | Virginica |
|---|---|---|---|
| Setosa | 50 | 0 | 0 |
| Versicolor | 0 | 47 | 3 |
| Virginica | 0 | 1 | 49 |

### Olive (Zone)
#### Naive Bayes

#### k-NN

#### C4.5

#### SVMs

### Olive (Région)
#### Naive Bayes

#### k-NN

#### C4.5

#### SVMs

### Segment
#### Naive Bayes

#### k-NN

#### C4.5

#### SVMs
