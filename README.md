# Apriori-Algorithm-Markov-Chain
This repository contains the implementation and evaluation of a hybrid algorithm that mines sequential and dynamic association rules by combining the Apriori algorithm and the Markov Chain model. [**Read the full paper here**](./Final Project Paper.pdf)

## 🧠 Motivation

Traditional market basket analysis methods, such as Apriori and FP-Growth, capture **static** item associations but **fail to account for sequence** and **probabilistic transitions** in customer behavior. This project introduces an algorithm that:
- **Incorporates order and dependency** using Markov Chains,
- **Prunes candidates dynamically** using theoretical transition-based frequencies,
- Enables **real-time personalized recommendations** and **webpage layout optimization**.

## Highlights

- **99% computational savings**: Only 43 scans needed vs. 8,489 in brute-force search.
- **High accuracy**: 66.7% of the most frequent 3-item rules were successfully captured.
- **Scalable** to longer rules and larger datasets.
- **Interpretability** via probabilistic rule generation and threshold-based pruning.

## Algorithm Overview

1. Compute initial item probabilities and transition matrix.
2. Generate frequent 2-item rules using traditional Apriori.
3. Extend to candidate 3-item (and longer) rules.
4. Estimate **theoretical frequencies** using:
   \[
   P(A \rightarrow B \rightarrow C) = P(A) \cdot P(B|A) \cdot P(C|B)
   \]
5. Prune candidates below the dynamic threshold (e.g., \( p^{k-1} \) for k-item rules).
6. Validate retained rules against dataset scans.
7. Repeat for longer rules until no more candidates remain.

## Dataset

- **Source**: [Kaggle Grocery Dataset](https://www.kaggle.com/datasets/heeraldedhia/groceries-dataset/data)
- **Size**: ~38,000 transactions
- **Features**: `Member_number`, `Date`, `ItemDescription`
- Preprocessing involved grouping purchases by day and customer, generating co-occurrence statistics, and computing sequential confidences.


## 📦 Implementation

- Python-based.
- Includes modules for:
  - Apriori-based itemset mining
  - Markov transition modeling
  - Rule pruning and validation
  - Data preprocessing and visualization

## 🔧 Future Improvements

- Incorporate **higher-order Markov Chains**.
- Improve performance on **small datasets**.
- Implement **adaptive, rule-length-specific thresholds**.

## 👩‍💻 Authors

- **Yibin Wang** – ywang448@ur.rochester.edu  
- **Saruultugs Batbayar** – sbatbaya@ur.rochester.edu
