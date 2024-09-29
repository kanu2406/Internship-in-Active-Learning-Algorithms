# Study of Active Learning Algorithms

## Internship Report by:
**Kanupriya Jain**  
Institut Polytechnique de Paris

## Supervisor:
**Prof. Christophe Denis**  
LPSM, Sorbonne Université

---

## Overview
This internship report focuses on the study and implementation of various **Active Learning Algorithms** for binary classification problems. Active learning aims to minimize the amount of labeled data needed for training machine learning models by strategically selecting the most informative data points for labeling. The report explores three main active learning methods:

1. **Active Learning with Rejection**
2. **Uncertainty Sampling**
3. **Query By Committee (QBC)**

The above algorithms were implemented from scratch based on a paper published by the supervisor. These algorithms are tested on both synthetic and real-world datasets, with comparisons made to passive learning classifiers and the Bayes classifier. Additionally, the report provides theoretical insights into the **Empirical Risk Minimization** framework in both passive and active settings.

---

## Table of Contents
1. [Binary Classification](#binary-classification)
2. [Empirical Risk Minimization](#empirical-risk-minimization)
3. [Active Learning Algorithms](#active-learning-algorithms)
   - [Active Learning with Rejection](#active-learning-with-rejection)
   - [Uncertainty Sampling](#uncertainty-sampling)
   - [Query By Committee (QBC)](#query-by-committee-qbc)
4. [Numerical Experiments](#numerical-experiments)
   - [Synthetic Dataset](#synthetic-dataset)
   - [Non-Synthetic Dataset (Stroke Prediction)](#non-synthetic-dataset-stroke-prediction)
5. [Comparison of Active Learning Approaches](#comparison-of-active-learning-approaches)
6. [Active Learning for Imbalanced Datasets](#active-learning-for-imbalanced-datasets)
7. [Conclusion](#conclusion)

---

## 1. Binary Classification
Binary classification is a supervised learning task that assigns one of two labels (0 or 1) to each observation. The report covers several binary classifiers, both linear (e.g., Logistic Regression) and non-linear (e.g., K-Nearest Neighbors, Random Forest). The objective is to minimize **Misclassification Risk**, and comparisons are made to the **Bayes Classifier**.

---

## 2. Empirical Risk Minimization
The concept of **Empirical Risk Minimization (ERM)** is studied in detail, where the goal is to minimize the misclassification risk using a set of classifiers and labeled data. The theoretical guarantees for both passive and active learning frameworks are presented, including **Theorem 1** and **Theorem 2** for the passive learning framework.

---

## 3. Active Learning Algorithms

### 3.1 Active Learning with Rejection
In this method, the model actively selects uncertain regions and rejects points with low prediction confidence. This rejection-based active learning is particularly useful in applications where misclassification carries high costs, such as medical diagnosis.

### 3.2 Uncertainty Sampling
Uncertainty sampling involves selecting the data points where the model is least confident (i.e., closest to a 0.5 probability). The algorithm iteratively selects the most uncertain points for labeling, improving the model’s performance with fewer labeled samples.

### 3.3 Query By Committee (QBC)
The QBC method involves maintaining a "committee" of classifiers, where the committee's members vote on the class labels of unlabeled data points. Points with the most disagreement (highest entropy) are selected for labeling. This method leverages multiple models to find the most informative samples.

---

## 4. Numerical Experiments

### 4.1 Synthetic Dataset
The report presents results from a synthetic binary classification dataset. Several classifiers are tested, including Logistic Regression, K-Nearest Neighbors, and Decision Trees. The performance of each classifier is compared across **Active Learning**, **Passive Learning**, and **Uncertainty Sampling** frameworks.

**Results**:  
- QBC achieved an accuracy of **91.58%**, with other classifiers (Logistic Regression, SVM, Decision Tree) showing similar performance across the frameworks.

### 4.2 Non-Synthetic Dataset (Stroke Prediction)
A real-world dataset is used to predict whether a patient is at risk of stroke. The same active learning algorithms are employed, and the results are compared.

**Results**:  
- QBC achieved an accuracy of **95.11%** on the stroke dataset, with other classifiers performing similarly.

---

## 5. Comparison of Active Learning Approaches
The report compares two popular Python libraries for active learning, **modAL** and **Alipy**, using both synthetic and non-synthetic datasets. The libraries implement different active learning strategies like uncertainty sampling and query-by-committee.

---

## 6. Active Learning for Imbalanced Datasets
A specialized active learning approach for imbalanced datasets is discussed, addressing the challenge of minority class representation in datasets. Several sampling strategies are evaluated, including **Random Sampling**, **Margin Sampling**, and **Uncertainty Diversity Sampling**.

---

## 7. Conclusion
The internship successfully explored the following:
- Theoretical foundations of empirical risk minimization for both passive and active learning.
- Implementation of three active learning strategies: **Rejection**, **Uncertainty Sampling**, and **Query By Committee**.
- Performance evaluation of active learning algorithms on synthetic and real-world datasets.

## Dataset
Non-synthetic dataset (Stroke Prediction Dataset) used for testing was sourced from [Kaggle](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset)

**Future Work**: The report concludes by suggesting future improvements, such as further refining active learning for imbalanced datasets and exploring other sampling strategies.

