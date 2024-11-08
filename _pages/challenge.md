---
permalink: /challenge/
title: "ConCon Challenge"
layout: splash
classes: wide
---

# ConCon Challenge

### Overview

A well-known problem encountered by typical machine learning methods is that confounders which are only present in the training data prevent the model from **generalizing to unseen (test) data**. However, if a model is trained on datasets sequentially in a **continual setting**, task-specific confounders may additionally exacerbate the challenge and adversely affect performance. This problem of **"continual confounding"** has been studied in **[ConCon](https://arxiv.org/abs/2402.06434)**, an image dataset based on CLEVR, where confounders differ across tasks. It has been shown that joint training on ConCon is less sensitive to confounding compared to the continual learning setup. 

In this challenge, we invite participants to submit solutions for overcoming the challenges posed by continual confounding. All solutions can be submitted **until January 7, 2025**. Note that we also offer an **early deadline on December 6, 2024**. Any entries submitted until this date will be reviewed in time for people to register with the early registration and to give more time to deal with possible visa issues.

We are hosting the competition on [**Kaggle**](https://www.kaggle.com/competitions/concon) where participants can evaluate the performance of their approach on a held-out test set. In order to qualify for presentation at the bridge, a **short report** needs to be submitted via [**Google Forms**](https://forms.gle/vrwmCYT32TTZ7Eor8).

If there are any open questions, please contact us at info[at]continualcausality[dot]org.

### Dataset Information

![ConCon strict](/assets/images/ConCon_both.png){: .align-right style="width:350px;"}

ConCon represents a learning task of two classes: **positive and negative**. All data instances are images based on the **CLEVR** framework. A **ground truth rule** can be used to determine the binary class affiliation of any image (green star in the shown figure). In order to correctly classify any image, learning this ground truth rule is sufficient. Since ConCon is a continual learning dataset, there are three tasks that are learned sequentially. Each task is confounded by a **task-specific confounder** (spiral in the shown figure), i.e., a feature that is present in the positive but not in the negative images of that task. The continual confounding challenge arises from the fact that task-specific confounders change across tasks.

As depicted in the figure, there are two dataset variants. There is the

- **Disjoint** dataset, where task-specific confounders **never appear in other tasks**, and the
- **Strict** dataset, where task-specific confounders **may appear in other tasks** as random features in both positive and negative samples.

We hypothesize that the main challenge of the disjoint dataset will be to identify that the actual ground truth features are not the ones that are easiest to learn. For the strict dataset, an important challenge will be to remember or store information from previous tasks in such a way that the ground truth rule can be identified in later tasks.

**We accept submissions on either dataset**, i.e., a submission is not required to perform well on both tasks. Submissions proposing solutions for both datasets are allowed but not required.

To avoid overfitting on the original ConCon dataset, we have generated a **new continually confounded dataset** for this challenge (the original ConCon dataset first introduced in [this paper](https://arxiv.org/abs/2402.06434) is **not** the target of this challenge). This new dataset can be found on the [Kaggle challenge page](https://www.kaggle.com/competitions/concon/data) and implements the following confounding features over time: *large*, *metal*, and *red*. We do not publicize the ground truth rule that can be used to successfully classify all images.

### Goals and Evaluation

In this challenge, the goal is to train a model that learns the ground truth rule and, thus, performs well on unconfounded data. To this end, it must avoid only learning the easy solution that is given by the task-specific confounders. To this end, in addition to the data for the confounded tasks, we publish an unconfounded dataset without labels. The goal is to **maximize the performance on this unconfounded dataset**. Specifically, the accuracy is to be calculated as

$$\text{acc} = \sum_{i=1}^{n}\frac{\mathbb{I}(\hat{y}_i = y_i)}{n},$$

where \( n=1500 \) is the number of samples in the unconfounded dataset, \( \hat{y}_i \) is the prediction for sample \( i \), and \( y_i \) is the ground truth label for sample \( i \). Out of these 1500 images, 450 (30%) images are used for evaluation for the public leaderboard and the other 1050 (70%) images are used for evaluation for a private leaderboard.

**Training instructions:** Training should be conducted one step at a time, following the continual learning order given by the dataset. This means a model should first be trained on data from Task 0, then updated using data from Task 1, and after that, updated using data from Task 2. Data used to train and update the model may not simply be accumulated fully, however using a small amount of memory as a memory buffer is in principle permitted. The size of the buffer should be justified and generally as small as possible.

### Submission Instructions

Submissions should propose an approach that helps overcome continual confounding. Their success in doing so can be measured by their performance on the confounded tasks and, more importantly, the unconfounded dataset.

For the submission to be presented at the bridge, participants should write a 3-page report (excluding references, acknowledgments, and an optional appendix including figures) detailing their approach and reporting the results on the public dataset. Submission will be reviewed in a single blind review process (author names included, reviewer names anonymous). In addition, a repository of the code used to train the model should be included as part of this submission.

There is an **early deadline on December 6, 2024 11:59pm (Anywhere on Earth, AoE)** and the **final deadline on January 7, 2025 11:59pm (Anywhere on Earth, AoE)**. Entries submitted until the early deadline will be reviewed in time for people to register with the early registration and to give more time to deal with possible visa issues.

### Bridge Inclusion Criteria

We accept submissions that propose an effective or innovative strategy for overcoming continual confounding. All accepted submissions get the **possibility to present a poster** at the bridge. However, this participation is not mandatory. 

Out of all accepted submissions, we will highlight a select subset of papers, inviting them for **long presentation in person at the bridge**. Papers can either be highlighted based on their effectiveness of the proposed strategy on the unconfounded dataset or for their innovativeness and novelty in methodology. Additionally, highlighted papers will get a **free Tutorial/Lab/Bridge Program Only Registration**.

### How to Start

You can find the dataset on the [Kaggle website](https://www.kaggle.com/competitions/concon/data). While we do not require any specific programming language or environment to be used for running the experiments, we offer a Docker container implementing the training and evaluation setup in Python [here](https://github.com/ContinualCausality/concon_challenge). By using this container, one can easily make changes and implement new approaches without setting up the entire environment.

### FAQ

**Where can I get more information on ConCon and continual confounding?** The paper "Where is the Truth? The Risk of Getting Confounded in a Continual World" introduces ConCon and discusses continual confounding in detail. There, you can get more information and discussions of the problems posed by this challenge. You can find it on [arXiv](https://arxiv.org/abs/2402.06434).

**Which dataset should I use?** Please use the dataset on the Kaggle webpage. Do not use the original ConCon dataset used in the paper.

**How should I submit?** Please submit a 3-page report on Google Forms, along with a link to your code repository if you wish to present your challenge submission at the bridge. 

**What should I evaluate?** The Kaggle competition measures the performance on the unconfounded dataset. In the report, please also include model performance on all confounded task for transparency. 

**How should I train the model?** First, choose a scenario (strict or disjoint) on which to run the experiments. Then, the model should be trained in a Continual Learning setting, i.e., starting by training on Task 0, then on Task 1, and, lastly, on Task 2. The datasets should not be accumulated, but using a small number of samples is permitted (for example, for replay techniques).

**What is the difference between the disjoint and the strict scenario?** In the disjoint dataset, task-specific confounders never appear in other tasks, and in the strict dataset, task-specific confounders may appear in other tasks as random features in both positive and negative samples. Note that this means that the disjunction of all confounding features is a valid solution for solving all confounded tasks in the disjoint case but not in the strict case.

**Does my method need to work for both disjoint and strict scenarios?** No, it is sufficient if a submission only considers one scenario. Of course, it is also allowed to propose solutions that perform well on both.

**Can we use pre-trained weights?** No, using pre-trained weights is not allowed. The model should be trained from scratch using only the ConCon dataset.

**Will my report be published in proceedings?** No, this competition is non-archival, but we will host a list of all accepted papers on our website, along with a leaderboard that will be published after the bridge takes place. You are free to resubmit to any future venue.