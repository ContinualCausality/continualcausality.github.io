---
permalink: /challenge/
title: "ConCon Challenge"
layout: splash
classes: wide 

---

# ConCon Challenge

*We provide initial information on the ConCon Challenge here. Details on the exact submission and evaluation procedure will follow soon.*

### **Overview**

A well-known problem encountered by typical machine learning methods is that confounders only present in the training data prevent the model from **generalizing to unseen data**. If a model is trained on datasets one after another in the **continual setting**, certain task-specific confounders could negatively affect model performance more severely compared to a joint setup. This **"continual confounding"** problem is represented by **[ConCon](https://arxiv.org/abs/2402.06434)**, an image dataset based on CLEVR where confounders differ across tasks. It has been shown that joint training on ConCon is less sensitive to confounding compared to the continual learning setup. In this challenge, we invite participants to submit solutions for overcoming the challenges posed by continual confounding.

Solutions can be submitted **until January 7, 2025**. Note that we also offer an **early deadline on December 6, 2024**. Any entries submitted until this date will be reviewed in time for people to register with the early registration and to give more time to deal with possible visa issues.

### **Dataset Information**

ConCon represents a learning task of two classes: **positive and negative**. All data instances are images based on the **CLEVR** framework. A **ground truth rule** can be used to determine the class affiliation of any image (green star in the attached figure). In order to correctly classify any image, learning this ground truth rule is sufficient. Since ConCon is a continual learning dataset, there are three tasks that are learned after one another. Each task is confounded by a **task-specific confounder** (spiral in the attached figure), i.e., a feature that is present in the positive but not in the negative images of that task. The task-specific confounder changes across tasks.

As can be seen in the attached figure, there are two dataset variants. There is the

- **Disjoint** dataset, where task-specific confounders **never appear in other tasks**, and the
- **Strict** dataset, where task-specific confounders **may appear in other tasks** as random features in both positive and negative samples.

We hypothesize that the main challenge of the disjoint dataset will be to identify that the actual ground truth features are not the ones that are easiest to learn. For the strict dataset, storing information from previous tasks such that the ground truth feature can be learned in new tasks appears to be important.

**We accept submissions on either dataset**, i.e., a submission is not required to perform well on both tasks. Submissions proposing solutions for both datasets are allowed but not required.

### **Goals and Evaluation**

Submitted approaches should aim to make correct predictions on  unconfounded data while only being trained on confounded tasks in a  continual learning setup. We will evaluate submissions based on their  effectiveness and novelty.

*Details will follow soon*.

### **Submission Instructions**

*Details will follow soon*.

### **Bridge Inclusion Criteria**

Authors of accepted submissions are invited to present their work at the bridge. 

*Details will follow soon*.

### **How to Start**

*Details will follow soon*.

### **FAQ**

**Where can I get more information on ConCon and continual confounding?** The paper "Where is the Truth? The Risk of Getting Confounded in a Continual World" introduces ConCon and discusses continual confounding in detail. There, you can get more information and discussions of the problems posed by this challenge. You can find it on [arXiv](https://arxiv.org/abs/2402.06434).

**What is the difference between the disjoint and the strict scenario?** In the disjoint dataset, task-specific confounders never appear in other tasks, and in the strict dataset, task-specific confounders may appear in other tasks as random features in both positive and negative samples. Note that this means that the disjunction of all confounding features is a valid solution for solving all confounded tasks in the disjoint case but not in the strict case.

**Does my method need to work for both disjoint and strict scenarios?** No, it is sufficient if a submission only considers one scenario. Of course, it is also allowed to propose solutions that perform well on both.