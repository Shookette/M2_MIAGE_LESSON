# Partie I - Classification supervisée

## I.1 - Un premier ensemble d'exemples simples

### Iris
#### Naive Bayes :
Avec cet algorithme, nous remarquons que les types d'Iris peuvent être suffisamment différenciés par la longueur de leurs pétales. En effet, malgré quelques erreurs de prédiction entre les iris versicolor et virginica, les trois groupes d'iris sont definis.

On nous indique plus précisément que dans 95.3% des cas (soit 7 erreurs), Naive Bayes classifie correctement les iris.

Vous trouverez ci-dessous un détail des prédictions (sachant que chaque espèce était représentée 50 fois).

| | Setosa | Versicolor | Virginica |
|---|---|---|---|
| Setosa | **50** | 0 | 0 |
| Versicolor | 0 | **47** | 3 |
| Virginica | 0 | 4 | **46** |

#### k-NN :
Grâce à cet algorithme, on peut choisir le k. Avec des k comme 1, 3, 5 ou 9, on obtient le même pourcentage d'erreurs qu'avec Naive Bayes.  
Cepandant, avec un k=7, l'algorithme a pu correctement classer les iris dans 96,6% des cas (soit 5 erreurs).

| | Setosa | Versicolor | Virginica |
|---|---|---|---|
| Setosa | **50** | 0 | 0 |
| Versicolor | 0 | **49** | 1 |
| Virginica | 0 | 4 | **46** |

#### C4.5 :
Cet algorithme nous permet de décrire la classification des espèces d'iris grâce à un arbre de décision que vous trouverez ci-dessous.

![Image](Iris-C4.5.png)

Nous observons sur l'arbre de décision que l'algorithme sépare d'abord les iris Setosa des deux autres espèces par la largeur de leurs pétales puis qu'il sépare ensuite les deux espèces par la largeur et la longueur de leur pétales.

Concernant le taux de bonne classification, il est égal aux autres à 95,3%.  
Vous trouverez ci-dessous la matrice de confusion.

| | Setosa | Versicolor | Virginica |
|---|---|---|---|
| Setosa | **49** | 1 | 0 |
| Versicolor | 0 | **47** | 3 |
| Virginica | 0 | 3 | **47** |

On remarque ici qu'un Setosa a été confondu pour un Versicolor alors qu'avec tous les autres algorithmes, nous ne trouvons aucune confusion concernant cette espèce.

#### SVMs :
Pour cet algorithme, nous utiliserons à chaque fois dans Weka la fonction libSVM.

Avec cette algorithme, nous obtenons le meilleur pourcentage de bonne classification avec 97,3% (soit 4 erreurs).

Voici la formule utilisée pour cet algorithme : weka.classifiers.functions.LibSVM -S 0 -K 2 -D 3 -G 0.0 -R 0.0 -N 0.5 -M 40.0 -C 1.0 -E 0.001 -P 0.1 -seed 1

Vous trouverez ci-dessous la matrice de confusion.

| | Setosa | Versicolor | Virginica |
|---|---|---|---|
| Setosa | **50** | 0 | 0 |
| Versicolor | 0 | **47** | 3 |
| Virginica | 0 | 1 | **49** |

### Olive (Zone)
Nous allons d'abord essayer de classer les huiles dans les 9 zones différentes.

#### Naive Bayes
Avec la classification Naive Bayes, nous obtenons une classification des éléments correcte à 95,58% (soit 6 erreurs).  

Voici la formule utilisée pour trouver ce résulat :  
weka.classifiers.bayes.NaiveBayes

Ci-dessous vous trouverez la matrice de confusion.

| | North-Apulia | Calabria | South-Apulia | Sicily | Inland-Sardinia | Coast-Sardinia | East-Liguria | West-Liguria | Umbria |
|---|---|---|---|---|---|---|---|---|---|
| North-Apulia | **5** | 0 | 0 | 1 | 0 | 0 | 0 | 0 | 0 |
| Calabria | 0 | **12** | 2 | 0 | 0 | 0 | 0 | 0 | 0 |
| South-Apulia | 0 | 0 | **47** | 1 | 0 | 0 | 0 | 0 | 0 |
| Sicily | 0 | 1 | 0 | **8** | 0 | 0 | 0 | 0 | 0 |
| Inland-Sardinia | 0 | 0 | 0 | 0 | **16** | 0 | 0 | 0 | 0 |
| Coast-Sardinia | 0 | 0 | 0 | 0 | 0 | **8** | 0 | 0 | 0 |
| East-Liguria | 0 | 0 | 0 | 0 | 0 | 0 | **11** | 0 | 1 |
| West-Liguria | 0 | 0 | 0 | 0 | 0 | 0 | 0 | **12** | 0 |
| Umbria | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | **11** |


#### k-NN
Avec l'algorithme des plus proches voisins, nous trouvons le même taux de bonne classification que précedemment, soit 95,58% (soit 6 erreurs) pour k=1 ou k=3. Cependant, si k est supérieur ou égal à 5, le taux de bonne classification diminue au fur et à mesure que k augmente.

Voici ci-dessous la formule qui nous a permis d'obtenir le meilleur résultat :  
weka.classifiers.lazy.IBk -K 3 -W 0 -A "weka.core.neighboursearch.LinearNNSearch -A \"weka.core.EuclideanDistance -R first-last\""

Vous trouverez également ci-dessous la matrice de confusion :

| | North-Apulia | Calabria | South-Apulia | Sicily | Inland-Sardinia | Coast-Sardinia | East-Liguria | West-Liguria | Umbria |
|---|---|---|---|---|---|---|---|---|---|
| North-Apulia | **5** | 0 | 0 | 1 | 0 | 0 | 0 | 0 | 0 |
| Calabria | 0 | **12** | 2 | 0 | 0 | 0 | 0 | 0 | 0 |
| South-Apulia | 0 | 0 | **48** | 0 | 0 | 0 | 0 | 0 | 0 |
| Sicily | 0 | 0 | 2 | **7** | 0 | 0 | 0 | 0 | 0 |
| Inland-Sardinia | 0 | 0 | 0 | 0 | **16** | 0 | 0 | 0 | 0 |
| Coast-Sardinia | 0 | 0 | 0 | 0 | 0 | **8** | 0 | 0 | 0 |
| East-Liguria | 0 | 0 | 0 | 0 | 0 | 0 | **11** | 0 | 1 |
| West-Liguria | 0 | 0 | 0 | 0 | 0 | 0 | 0 | **12** | 0 |
| Umbria | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | **11** |

#### C4.5
Avec l'algorithme C4.5, on trouve un taux de bonne classification de 87,5%, ce qui est nettement inférieur au deux algorithmes testés précédemment.

Vous trouverez ci-dessous l'arbre de décision qui a permis de classer les huiles d'olives en fonction des zones.
![Image](olive-area-j48.png)

#### SVMs
Pour la classification SVM, nous obtenons le taux le plus bas de bonne classification : 36,02% soit plus de la moitié des huiles qui ont mal été classées.

### Olive (Région)
Ici, nous voulons classer les huiles en 3 régions différentes.

#### Naive Bayes
Avec ce premier algorithme, nous obtenons déjà un très bon taux de classification à 99,26%, soit une erreur seulement.

Vous trouverez ci-dessous la matrice de confusion.

| | South | Sardinia | North |
|---|---|---|---|
| South | **77** | 0 | 0 |
| Sardinia | 0 | **23** | 1 |
| North | 0 | 0 | **35** |

#### k-NN
Ici, pour k=1, on obtient un taux de bonne classification parfait à 0%. En effet, toutes les huiles ont correctement été classées.  
Voici la commande qui nous a permis d'obtenir ce résultat :  
weka.classifiers.lazy.IBk -K 1 -W 0 -A "weka.core.neighboursearch.LinearNNSearch -A \"weka.core.EuclideanDistance -R first-last\""

Vous trouverez ci-dessous la matrice de confusion.

| | South | Sardinia | North |
|---|---|---|---|
| South | **77** | 0 | 0 |
| Sardinia | 0 | **24** | 0 |
| North | 0 | 0 | **35** |

#### C4.5
Avec l'algorithme C4.5, nous trouvons le même taux de bonne classification qu'avec Naive Bayes soit 99,26% (1 erreur).

Vous trouverez ci-dessous la matrice de confusion.

| | South | Sardinia | North |
|---|---|---|---|
| South | **77** | 0 | 0 |
| Sardinia | 0 | **24** | 0 |
| North | 0 | 1 | **34** |

Vous trouverez également l'abre de décision ci-dessous.
![Image](olive-region-j48.png)

#### SVMs
Cet algorithme nous offre le plus grand nombre d'erreurs puisque le taux de bonne classification est de 57,35% seulement.

En effet, comme nous pouvons le constater avec la matrice de décision ci-dessous, toutes les huiles exceptée une ont été classées comme appartenant à la région Sud.

| | South | Sardinia | North |
|---|---|---|---|
| South | **77** | 0 | 0 |
| Sardinia | 24 | **0** | 0 |
| North | 34 | 0 | **1** |

### Segment
#### Naive Bayes
Pour ce nouveau jeu de données plus important que les autres (2310 éléments), nous allons d'abord appliquer Naive Bayes. Nous obtenons un taux de bonne classification de 80,04% (soit 461 erreurs).

#### k-NN
Grâce à cet algorithme, notre taux de bonne classification augmente significativement puisque nous avons 94,40% de données qui ont été classifiées correctement (soit 60 erreurs seulement).

Vous trouverez ci-dessous la formule qui nous a permis d'obtenir ce résultat, avec k=1 :  
weka.classifiers.lazy.IBk -K 1 -W 0 -A "weka.core.neighboursearch.LinearNNSearch -A \"weka.core.EuclideanDistance -R first-last\""

Voici la matrice de confusion que nous obtenons.

|| Brickface | Sky | Foliage | Cement | Window | Path | Grass |
|---|---|---|---|---|---|---|---|
| Brickface | **328** | 0 | 0 | 0 | 2 | 0 | 0 |
| Sky | 0 | **330** | 0 | 0 | 0 | 0 | 0 |
| Foliage | 0 | 0 | **319** | 0 | 11 | 0 | 0 |
| Cement | 2 | 0 | 2 | **315** | 9 | 2 | 0 |
| Window | 3 | 0 | 18 | 8 | **301** | 0 | 0 |
| Path | 0 | 0 | 0 | 0 | 0 | **330** | 0 |
| Grass | 0 | 0 | 0 | 1 | 1 | 1 | **327** |

#### C4.5
Avec l'algorithme C4.5 sur ce jeu de données, le taux de bonne classication est égal à 96,71% (soit 76 erreurs).

Vous trouverez ci-dessous l'arbre de décision obtenu.
![Image](segment-j48.png)

Cependant, l'exécution de cet algorithme est assez long, comparé aux précédents jeux de données qui etaient plus petits.

#### SVMs
L'éxécution de cet algorithme était très long en cross-validation à 2310 éléments, nous avons donc modifié ce paramètre en cross-validation à 10 éléments.

Avec ce paramètre, nous obtenons un taux de bonne classification de 65,36% (soit 800 erreurs).

## I.2 - Classification des ensembles de données Diabetes et Satimage

### Diabetes
#### Naive Bayes

#### k-NN

#### C4.5

#### SVMs

### Satimage
#### Naive Bayes

#### k-NN

#### C4.5

#### SVMs
