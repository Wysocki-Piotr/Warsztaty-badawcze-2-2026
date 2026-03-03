# Can we find real hierarchies in the wild? Semantic and empirical approach

While training CAVs, we often ignore any internal structure of the data. For example, we measure orthogonality of different concepts in latent space, even if we *really shouldn't*. The arising question is: can we use the internal structure of the dataset to create better CAVs? In particular, we can consider hierarchies of concepts in the data. E.g., hierarchy $A \rightarrow B$ means that the existence of A implies the existence of B (here, $\rightarrow$ is used as implication, not dependence). **This project aims to find real hierarchies in the data, using both the knowledge about semantic relations and empirically found hierarchies**.

## Hierarchy

The hierarchies in data can be found in two ways: 1) hierarchy might be obvious from our point of view (e.g., if someone has a goatee, they also have a beard), but also 2) hierarchies might be found empirically (e.g., if only men have a beard in the dataset, beard implies man).

In fact, semantic hierarchies should be, in most cases, easy to find empirically. So why should we distinguish between them? When we talk about task-specific models, like ResNet trained to classify CelebA, this shouldn't matter. However, when we switch to big pretrained models like CLIP or DINO, we can assume that they already have prior knowledge about some hierarchies that exist "in the wild"; thus, the "obvious" hierarchies can be better models for these models.

Sometimes hierarchies can be approximate, e.g., if a bird has a yellow belly, it *almost* always has yellow wings as well. The problem is how to define when "*almost*" changes to "*sometimes*". The answer to this question is to be found during the project.

## Datasets

Inevitably, hierarchies are everywhere, but it's not necessarily true for the dataset we can use. There are some, e.g., type of beards, makeup, gender in CelebA, type of beaks and colors in CUB-200, or whatever is done with WordNet and ImageNet. However, to set up this experiment, at least 2-3 datasets should be evaluated.

## Better CAVs (?)

One approach to hierarchical concepts was proposed in recent weeks in [HCEP](https://arxiv.org/pdf/2602.11448). TL;DR, this work suggest that if $A\rightarrow B$, then $SV(A) - SV(B) \perp SV(A)$. Another possible approach is to filter out unnecessary data. E.g., if $A\rightarrow B$ then SV(A) doesn't have to be trained on $\lnot B$, but rather only on B. Next, for inference and testing, B needs to be determined before testing A.

## Project structure and problem statement

During this project, we would like to find concepts that form hierarchies and evaluate two CAVs that are mentioned in the previous section. The project can be divided into the following parts:

1. Dataset selection
2. Search for hierarchical concepts
3. Creating and evaluating CAVs for hierarchical data
4. Comparing hierarchies built upon semantic relations and empirical analysis, potentially on both models like ResNet and CLIP
