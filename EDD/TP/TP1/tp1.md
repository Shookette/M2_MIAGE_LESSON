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

Correctly Classified Instances         130               95.5882 %
Incorrectly Classified Instances         6                4.4118 %

  a  b  c  d  e  f  g  h  i   <-- classified as
  5  0  0  1  0  0  0  0  0 |  a = North-Apulia
  0 12  2  0  0  0  0  0  0 |  b = Calabria
  0  0 47  1  0  0  0  0  0 |  c = South-Apulia
  0  1  0  8  0  0  0  0  0 |  d = Sicily
  0  0  0  0 16  0  0  0  0 |  e = Inland-Sardinia
  0  0  0  0  0  8  0  0  0 |  f = Coast-Sardinia
  0  0  0  0  0  0 11  0  1 |  g = East-Liguria
  0  0  0  0  0  0  0 12  0 |  h = West-Liguria
  0  0  0  0  0  0  0  0 11 |  i = Umbria
#### k-NN

Correctly Classified Instances         130               95.5882 %
Incorrectly Classified Instances         6                4.4118 %

à partir de K >= diminution progressive du % correct

  a  b  c  d  e  f  g  h  i   <-- classified as
  5  0  0  1  0  0  0  0  0 |  a = North-Apulia
  0 12  2  0  0  0  0  0  0 |  b = Calabria
  0  0 48  0  0  0  0  0  0 |  c = South-Apulia
  0  0  2  7  0  0  0  0  0 |  d = Sicily
  0  0  0  0 16  0  0  0  0 |  e = Inland-Sardinia
  0  0  0  0  0  8  0  0  0 |  f = Coast-Sardinia
  0  0  0  0  0  0 11  0  1 |  g = East-Liguria
  0  0  0  0  0  0  0 12  0 |  h = West-Liguria
  0  0  0  0  0  0  0  0 11 |  i = Umbria

#### C4.5

Correctly Classified Instances         119               87.5    %
Incorrectly Classified Instances        17               12.5    %

a  b  c  d  e  f  g  h  i   <-- classified as
4  0  1  1  0  0  0  0  0 |  a = North-Apulia
0  8  3  3  0  0  0  0  0 |  b = Calabria
0  0 47  1  0  0  0  0  0 |  c = South-Apulia
0  1  3  5  0  0  0  0  0 |  d = Sicily
0  0  0  0 15  1  0  0  0 |  e = Inland-Sardinia
0  0  0  0  0  8  0  0  0 |  f = Coast-Sardinia
0  0  0  0  0  0 10  1  1 |  g = East-Liguria
0  0  0  0  1  0  0 11  0 |  h = West-Liguria
0  0  0  0  0  0  0  0 11 |  i = Umbria

![Image](olive_area_j48.png)

#### SVMs

Correctly Classified Instances          49               36.0294 %
Incorrectly Classified Instances        87               63.9706 %

a  b  c  d  e  f  g  h  i   <-- classified as
0  0  6  0  0  0  0  0  0 |  a = North-Apulia
0  0 14  0  0  0  0  0  0 |  b = Calabria
0  0 48  0  0  0  0  0  0 |  c = South-Apulia
0  0  9  0  0  0  0  0  0 |  d = Sicily
0  0 16  0  0  0  0  0  0 |  e = Inland-Sardinia
0  0  8  0  0  0  0  0  0 |  f = Coast-Sardinia
0  0 12  0  0  0  0  0  0 |  g = East-Liguria
0  0 12  0  0  0  0  0  0 |  h = West-Liguria
0  0 10  0  0  0  0  0  1 |  i = Umbria

### Olive (Région)
#### Naive Bayes

Correctly Classified Instances         135               99.2647 %
Incorrectly Classified Instances         1                0.7353 %

a  b  c   <-- classified as
77  0  0 |  a = South
0 23  1 |  b = Sardinia
0  0 35 |  c = North

#### k-NN

weka.classifiers.lazy.IBk -K 1 -W 0 -A "weka.core.neighboursearch.LinearNNSearch -A \"weka.core.EuclideanDistance -R first-last\""

Correctly Classified Instances         136              100      %
Incorrectly Classified Instances         0                0      %

a  b  c   <-- classified as
77  0  0 |  a = South
0 24  0 |  b = Sardinia
0  0 35 |  c = North

#### C4.5

Correctly Classified Instances         135               99.2647 %
Incorrectly Classified Instances         1                0.7353 %

  a  b  c   <-- classified as
 77  0  0 |  a = South
  0 24  0 |  b = Sardinia
  0  1 34 |  c = North

![Image](olive_region_j48.png)
#### SVMs

Correctly Classified Instances          78               57.3529 %
Incorrectly Classified Instances        58               42.6471 %

a  b  c   <-- classified as
77  0  0 |  a = South
24  0  0 |  b = Sardinia
34  0  1 |  c = North

### Segment
#### Naive Bayes

#### k-NN

#### C4.5

#### SVMs
