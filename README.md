## ML Foundations -- applications & theories

Machine-learning methods built **from first principles** -- algorithms alongside with the hand-written mathematical derivations of the concepts.

These are based on my graduate machine-learning coursework (Rice University). I've reorganized the work by topic, keeping the original scripts I created during my ML training. I also included my class notes and theories related to each topic.

### Structure
The pattern throughout is **math → code → result**.

**The `theory/` folders** demonstrate the derivations and math behind each machine learning topic demonstrated here. 

**Code**  `.Rmd` (R Markdown) for the R topics, `.ipynb` (Jupyter) for
  the Python topics.

**[Course notes](notes/)** a downloadable PDF — 57 pages hand-written notes across the whole course (derivations, geometry, explanations).


### Contents

| # | Topic | What I implemented | Lang | Hand-written derivations |
|---|-------|--------------------|------|--------------------------|
| [01](01-knn-from-scratch/) | **KNN from scratch** | k-NN classification *and* regression written from scratch, benchmarked against library implementations; effect of *k* | R | convexity, MLE & eigen foundations |
| [02](02-regularization-and-feature-selection/) | **Regularization & feature selection** | Best-subsets, forward/backward stepwise, Lasso, Elastic Net, Ridge; regularization paths; empirical demos of regression theory (intercept ≡ centering, p > n zero training error, MSE-existence) | R | Lasso / ADMM solver |
| [03](03-cross-validation-and-classification/) | **Cross-validation & classification** | k-fold CV written from scratch to tune sparse logistic regression & linear SVM (digits 3 vs 8); multinomial logistic, naïve Bayes, LDA, linear & kernel SVM | Python | SVM primal → dual (hinge + ridge) |
| [04](04-clustering-pca-and-graphical-models/) | **Clustering, PCA & graphical models** | PCA, t-SNE, k-means, hierarchical & consensus clustering, graphical Lasso on an authorship dataset | Python | classical MDS ≡ PCA; graphical-Lasso conditional independence |
| [05](05-neural-nets-and-tree-ensembles/) | **Neural nets & tree ensembles** | Feed-forward nets (activation-function & network-size studies, MLP, CNN, max-pooling) on Fashion-MNIST; decision trees, bagging, random forests, AdaBoost, gradient boosting on the Adult dataset | Python | — |

  
### Running the code

- **R (topics 01–02):** `install.packages(c("ISLR2","caret","glmnet","kknn","leaps","tidyverse"))`

- **Python (topics 03–05):** see [`requirements.txt`](requirements.txt).

- **Datasets** MNIST `.idx*-ubyte` (topic 03), `authors.csv` (topic 04), and Fashion-MNIST + Adult (topic 05).
