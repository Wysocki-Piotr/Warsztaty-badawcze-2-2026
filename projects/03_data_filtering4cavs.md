# Can we exclude information to make concepts more robust?

Datasets are often labelled poorly due to their size and complexity. e.g., in CelebA, there are over 800 samples annotated as "having no beard" and "having a goatee". Because of that, the idea of "concept" might be much more ambiguous for capture. This is specifically true for concepts on which we can put constraints (e.g., goatee implies beard). **This project aims to verify whether removing noisy samples from concept detection methods can increase their quality**.

## Qualitative evaluation

While it's reasonable to remove samples of low quality to create CAVs, it makes the evaluation problematic. If we remove low-quality samples from the test set, we basically cheat by removing troublesome examples. On the other hand, if we don't alter the test set, our CAVs may ignore the distribution of the data in CelebA and consequently, perform worse even if it's better on high-quality data.

So quantitative results are still interesting, but we should focus more on qualitative results. How can we do it? For example, we can use [LRP](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0130140) to show where the CAV actually "looks" when it captures the concept.

## CelebA

CelebA is a perfect dataset for this project, as it's noisy, poorly labelled, and has a lot of samples. Moreover, hypotheses about concepts can be easily formulated, as the concepts describe persons' appearance.

## Project structure and problem statement

During this project, we would like to find a clever way to filter out noisy data to verify whether CAVs created on it will have better properties, specifically presenting quantitative results. The project can be divided into the following parts:

1. Designing filtering-out methods
2. Training CAVs (potentially several versions)
3. Assessing the difference before and after filtering out noise data by:
    - quantitative metrics
    - qualitative visualisations

## Technical notes

This project is probably the most basic one, so I encourage you to take it only if you're interested in easy passing of the course, or if you have interesting ideas on how to implement it in a more advanced way.
