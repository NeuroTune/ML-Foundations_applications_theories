# ML Foundations — implementations & derivations

A working portfolio of machine-learning methods built **from first principles** — algorithms
coded from scratch, paired with the hand-written mathematical derivations behind them.

These grew out of my graduate machine-learning coursework (**ELEC 478/578, Rice University,
Fall 2023**). I've reorganized the work by *topic* rather than by assignment, kept only the
code and the math, and put each derivation next to the code that implements it.

## Why this repo looks the way it does

Anyone can now generate working ML code in seconds. So the code here isn't the point — the
**understanding** is. What doesn't come for free is being able to *derive* the method: to show
that Gaussian-process regression is kernel ridge regression, that Newton's method for logistic
regression is iteratively reweighted least squares, that classical MDS is PCA, or why a zero in
the graphical-lasso precision matrix means conditional independence. That's what the
`theory/` folders and my [course notes](notes/) are for. The pattern throughout is
**math → code → result**.

## Contents

| # | Topic | What I implemented | Lang | Hand-written derivations |
|---|-------|--------------------|------|--------------------------|
| [01](01-knn-from-scratch/) | **KNN from scratch** | k-NN classification *and* regression written from scratch, benchmarked against library implementations; effect of *k* | R | convexity, MLE & eigen foundations |
| [02](02-regularization-and-feature-selection/) | **Regularization & feature selection** | Best-subsets, forward/backward stepwise, Lasso, Elastic Net, Ridge; regularization paths; empirical demos of regression theory (intercept ≡ centering, p > n zero training error, MSE-existence) | R | Lasso / ADMM solver |
| [03](03-cross-validation-and-classification/) | **Cross-validation & classification** | k-fold CV written from scratch to tune sparse logistic regression & linear SVM (digits 3 vs 8); multinomial logistic, naïve Bayes, LDA, linear & kernel SVM | Python | SVM primal → dual (hinge + ridge) |
| [04](04-clustering-pca-and-graphical-models/) | **Clustering, PCA & graphical models** | PCA, t-SNE, k-means, hierarchical & consensus clustering, graphical Lasso on an authorship dataset | Python | classical MDS ≡ PCA; graphical-Lasso conditional independence |
| [05](05-neural-nets-and-tree-ensembles/) | **Neural nets & tree ensembles** | Feed-forward nets (activation-function & network-size studies, MLP, CNN, max-pooling) on Fashion-MNIST; decision trees, bagging, random forests, AdaBoost, gradient boosting on the Adult dataset | Python | — |

**[Course notes](notes/)** — 57 pages of color-coded hand-written notes across the whole
course (derivations, geometry, intuition), with featured pages and a full PDF.

## How each topic folder is organized

- **Code, in its native format** — `.Rmd` (R Markdown) for the R topics, `.ipynb` (Jupyter) for
  the Python topics. The Jupyter notebooks are the **executed** versions, so their plots and
  outputs render inline on GitHub. The R code is verbatim what I submitted.
- **`theory/`** (topics 01–04) — the hand-written derivations as a downloadable PDF, with a key
  page embedded in that topic's README.
- A short **README** per topic tying the math to the code to the result.

## Running the code

- **R (topics 01–02):** `install.packages(c("ISLR2","caret","glmnet","kknn","leaps","tidyverse"))`
  (plus `class`, `MASS` which ship with R).
- **Python (topics 03–05):** see [`requirements.txt`](requirements.txt).
  Topic 05's notebook was written for the **Keras 2** API (`tf.keras.optimizers.legacy.*`); to
  run it, use `tensorflow==2.15` on Python ≤ 3.11, or `tensorflow==2.19` + `tf-keras` with
  `TF_USE_LEGACY_KERAS=1`.
- **Datasets are not included** (they belong to their sources): MNIST `.idx*-ubyte` (topic 03),
  `authors.csv` (topic 04), and Fashion-MNIST + Adult (topic 05).

## Provenance

This is my own coursework, cleaned up and reorganized for sharing. It grew out of ELEC 478/578
(Rice University, Fall 2023); I've credited the course, not any individual. The problem *topics*
(KNN, Lasso, cross-validation, …) are standard; the implementations, derivations, and notes are
mine.
