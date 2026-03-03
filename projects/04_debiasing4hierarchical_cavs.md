# How to debias hierarchical CAVs?

Most debiasing methods for computer vision models require two elements: (1) the CAV, as a direction in a latent space, and (2) a debiasing procedure. There are many approaches to (2): starting from simple orthogonalisation of the latent space to the CAV, ending on methods from the CLARC family ([A-CLARC](https://arxiv.org/abs/1912.11425), [P-CLARC](https://arxiv.org/abs/1912.11425), [R-CLARC](https://arxiv.org/pdf/2404.09601)). However, all existing CAVs are working in the context of the full latent space, so the natural question arises - should hierarchical CAVs be treated differently by existing debiasing procedures? **This project aims to verify whether existing debiasing methods work for hierarchical CAVs and how we can improve them to incorporate hierarchies.**

## Debiasing methods

Debiasing methods are designed to remove some information from the model when it's misused. For example, a model may learn to classify each person with long hair as a woman, which is obviously incorrect. Why can't we just train a model so it does not contain bias?

- Bias is created via data distribution, and sometimes filtering out observations that can create some bias means removing all data.
- the (re)training is costly and time-consuming,
- The original volume of data might not be accessible.

At the same time, removing bias via latent space is fast and does not require much data. A-CLARC adds random bias to each observation, so the model cannot generalise knowledge from it. P-CLARC subtracts a vector from each observation, so in the context of a specific concept, all examples "look like" they don't have it.

The important thing in debiasing models is to define bias and model it in latent space. For this, CAVs are just perfect.

## Project structure and problem statement

During this project, we would like to evaluate existing debiasing methods on concepts that are hierarchical and verify whether they perform better when CAVs are created to incorporate these hierarchies. Then, we will try to find better alternatives for debiasing these CAVs. Notably, we will verify if using debiasing on one concept will affect other concepts in the hierarchy. The project can be divided into the following parts:

1. Creating CAVs and hierarchical CAVs
2. Performing debiasing
3. Creating hierarchical debiasing
4. Analysis of the results (cross-concepts effects and accuracy metrics)
