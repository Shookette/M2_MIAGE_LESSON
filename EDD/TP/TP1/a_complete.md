### Olive (Zone)
#### Naive Bayes

weka.classifiers.bayes.NaiveBayes

#### k-NN

weka.classifiers.lazy.IBk -K 3 -W 0 -A "weka.core.neighboursearch.LinearNNSearch -A \"weka.core.EuclideanDistance -R first-last\""

### Segment
#### Naive Bayes

Correctly Classified Instances        1849               80.0433 %
Incorrectly Classified Instances       461               19.9567 %

weka.classifiers.bayes.NaiveBayes

a   b   c   d   e   f   g   <-- classified as
321   0   0   6   3   0   0 |   a = 1
0 328   0   2   0   0   0 |   b = 2
6   0  50   8 266   0   0 |   c = 3
24   0   6 281  12   7   0 |   d = 4
62   0  12  26 230   0   0 |   e = 5
0   0   4  11   0 315   0 |   f = 6
0   0   1   0   5   0 324 |   g = 7

#### k-NN

Correctly Classified Instances        2250               97.4026 %
Incorrectly Classified Instances        60                2.5974 %

weka.classifiers.lazy.IBk -K 1 -W 0 -A "weka.core.neighboursearch.LinearNNSearch -A \"weka.core.EuclideanDistance -R first-last\""

a   b   c   d   e   f   g   <-- classified as
328   0   0   0   2   0   0 |   a = 1
0 330   0   0   0   0   0 |   b = 2
0   0 319   0  11   0   0 |   c = 3
2   0   2 315   9   2   0 |   d = 4
3   0  18   8 301   0   0 |   e = 5
0   0   0   0   0 330   0 |   f = 6
0   0   0   1   1   1 327 |   g = 7

#### C4.5

Correctly Classified Instances        2234               96.71   %
Incorrectly Classified Instances        76                3.29   %

weka.classifiers.trees.J48 -C 0.25 -M 2

a   b   c   d   e   f   g   <-- classified as
327   0   1   0   2   0   0 |   a = 1
0 330   0   0   0   0   0 |   b = 2
1   1 310   2  16   0   0 |   c = 3
2   0   2 306  19   0   1 |   d = 4
2   0  18   8 302   0   0 |   e = 5
0   0   0   0   0 330   0 |   f = 6
0   0   0   0   0   1 329 |   g = 7

![Image](segment_j48.png)

long

#### SVMs
SUPER MEGA TROP LONG (1 element / seconde)

Alors cross-validation passage de 2310 elements à 10 elements

Correctly Classified Instances        1510               65.368  %
Incorrectly Classified Instances       800               34.632  %

weka.classifiers.functions.LibSVM -S 0 -K 2 -D 3 -G 0.0 -R 0.0 -N 0.5 -M 40.0 -C 1.0 -E 0.001 -P 0.1 -seed 1

a   b   c   d   e   f   g   <-- classified as
241   0   0  59   0   0  30 |   a = 1
0 169   0 111   0   0  50 |   b = 2
0   0 181  98   8   0  43 |   c = 3
1   0   0 278   0   0  51 |   d = 4
0   0   9  89 188   0  44 |   e = 5
0   0   0  77   0 221  32 |   f = 6
0   0   0  98   0   0 232 |   g = 7
