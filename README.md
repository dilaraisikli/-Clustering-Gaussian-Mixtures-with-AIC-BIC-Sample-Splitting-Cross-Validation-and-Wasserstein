Gaussian Mixture Modelling & Sentiment Lexicon Construction

A collection of notebooks exploring text sentiment lexicons and statistical model selection using EM-based Gaussian Mixture Models.

Overview

This repository contains two independent yet complementary projects:

1. Sentiment Lexicon Construction (Python)

A complete pipeline for collecting and structuring negative sentiment words from multiple well-known dictionaries used in NLP:

AFINN-111

Harvard IV-4 General Inquirer

Loughran–McDonald Financial Sentiment Lexicon

The notebook filters, groups, and exports negative-polarity word lists across different semantic categories such as:

Hostile, Weak, Power, Active, Passive

Economic, Litigious, Constraining, Uncertainty, Modal verbs, etc.

This process is useful for:

classical NLP sentiment analysis

lexicon-based scoring

building domain-specific sentiment dictionaries

feature engineering for downstream ML models

The output includes structured CSV files containing vocabulary grouped by category and polarity.

2. Gaussian Mixture Modelling & Model Selection (R)

A full statistical simulation study built from scratch, including:

Custom EM Algorithm

Implemented a dynamic handmade EM algorithm for fitting K-component univariate Gaussian mixtures.

Learns mixture weights, means, and variances through iterative E–M updates.

Synthetic Data Generation

Generated complex mixture distributions using Bart’s NormMixture function.

Compared behavior with two sample sizes:

n₁ = 500 → non-asymptotic regime

n₂ = 2500 → asymptotic regime

Model Selection Experiments

Evaluated the optimal number of mixture components (k) using:

AIC

BIC

Sample Splitting (30%, 50%, 70%)

K-Fold Cross-Validation (5-fold & 10-fold)

1-Wasserstein Distance

Key observations:

Larger sample sizes consistently select k = kₘₐₓ, as expected in well-separated mixtures.

Smaller samples occasionally under-estimate k due to limited information—consistent with statistical theory.

Wasserstein-based selection behaves more conservatively for n₁, aligning with robustness properties.
