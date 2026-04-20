<div align="center">

# Towards Intrinsic Interpretability of Large Language Models: <br> A Survey of Design Principles and Architectures

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re) 
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> **The first systematic review of intrinsic interpretability for LLMs, categorizing approaches into five design paradigms: functional transparency, concept alignment, representational decomposability, explicit modularization, and latent sparsity induction.**

[**[📄 Read the Paper]**](paper.pdf)

</div>

---

## 📖 Table of Contents

- [Overview](#-overview)
- [Taxonomy & Design Principles](#-taxonomy--design-principles)
- [Paper List](#-paper-list)
  - [1. Functional Transparency](#1-functional-transparency)
  - [2. Concept Alignment](#2-concept-alignment)
  - [3. Representational Decomposability](#3-representational-decomposability)
  - [4. Explicit Modularization (MoEs)](#4-explicit-modularization-moes)
    - [Intra-Expert Sparsity](#intra-expert-sparsity)
    - [Fine-Grained Decomposition](#fine-grained-decomposition)
    - [Semantically Aligned Routing](#semantically-aligned-routing)
  - [5. Latent Sparsity Induction](#5-latent-sparsity-induction)
- [Reference](#-reference)
- [Contact](#-contact)

---

## 📖 Overview

![Taxonomy Framework](intrinsicmethod.png)
*Figure: A taxonomy of intrinsic architectural designs for interpretable LLMs. We categorize existing approaches into five primary families based on their core mechanism for transparency.*

While Large Language Models (LLMs) have achieved strong performance, their opaque internal mechanisms hinder trustworthiness. Unlike post-hoc explanation methods that interpret trained models through external approximations, **Intrinsic Interpretability** builds transparency directly into model architectures and computations.

This survey presents the first systematic review of recent advances in intrinsic interpretability for LLMs. We distinguish intrinsic methods by their **structural fidelity**—ensuring that the model's internal computation is itself interpretable without relying on external surrogates. We categorize existing approaches into five core design paradigms and discuss open challenges in balancing interpretability with performance at scale.

## 🏷 Taxonomy & Design Principles

To help navigate the paper list, we organize studies around the **Five Core Design Principles** proposed in our survey:

### ⚙️ 1. Functional Transparency
*Advocates architectures whose computations are both structurally explicit and semantically meaningful (e.g., GAMs, KANs).*

### 🔗 2. Concept Alignment
*Aligns latent representations with human-understandable concepts to reduce polysemanticity (e.g., Concept Bottleneck Models).*

### 🧩 3. Representational Decomposability
*Structures the latent space to disentangle representations into independent subspaces (e.g., Backpack models).*

### 📦 4. Explicit Modularization
*Decomposes computation into distinct, independently functioning modules with traceable routing pathways (e.g., Mixture-of-Experts).*

### 📉 5. Latent Sparsity Induction
*Induces modularity and sparsity within standard dense architectures through regularization or gating (e.g., Sparse Training).*

---

## 📑 Paper List

### 1. Functional Transparency

| Paper | Venue | Year | Link |
| :--- | :---: | :---: | :---: |
| **Generalized Additive Models** | Statistical Science | 1986 | [Link](https://projecteuclid.org/journals/statistical-science/volume-1/issue-3/Generalized-Additive-Models/10.1214/ss/1177013604.full) |
| **Accurate Intelligible Models with Pairwise Interactions (GA²M)** | KDD | 2013 | [Link](https://www.cs.cornell.edu/~yinlou/papers/lou-kdd13.pdf) |
| **InterpretML: A Unified Framework for Machine Learning Interpretability (EBMs)** | NeurIPS | 2019 | [Link](https://arxiv.org/abs/1909.09223) |
| **GAMI-Net: An Explainable Neural Network Based on Generalized Additive Models (NAMs)** | Pattern Recog. | 2021 | [Link](https://arxiv.org/abs/2003.07132) |
| **KAN: Kolmogorov-Arnold Networks** | ICLR | 2025 | [Link](https://proceedings.iclr.cc/paper_files/paper/2025/file/afaed89642ea100935e39d39a4da602c-Paper-Conference.pdf) |
| **Bilinear MLPs Enable Weight-Based Mechanistic Interpretability** | ICLR | 2025 | [Link](https://proceedings.iclr.cc/paper_files/paper/2025/hash/7504142a20a3e1fe9dd7de42f475828c-Abstract-Conference.html) |

### 2. Concept Alignment

| Paper | Venue | Year | Link |
| :--- | :---: | :---: | :---: |
| **Concept Bottleneck Models (Standard CBMs)** | ICML | 2020 | [Link](https://arxiv.org/abs/2007.04612) |
| **Stochastic Concept Bottleneck Models (SCBMs)** | NeurIPS | 2024 | [Link](https://proceedings.neurips.cc/paper_files/paper/2024/file/5c7894ac8788555f1cecf536f1e0fd35-Paper-Conference.pdf) |
| **Addressing Leakage in Concept Bottleneck Models (Hybrid CBMs)** | NeurIPS | 2022 | [Link](https://proceedings.neurips.cc/paper_files/paper/2022/hash/944ecf65a46feb578a43abfd5cddd960-Abstract-Conference.html) |
| **CB-LLM: Concept Bottleneck Large Language Models** | ICLR | 2025 | [Link](https://openreview.net/forum?id=RC5FPYVQaH) |
| **Label-Free Concept Bottleneck Models** | ICLR | 2023 | [Link](https://openreview.net/forum?id=9YpbmkPmuT) |
| **Concept Embedding Models (CEMs / IntCEMs)** | NeurIPS | 2022 | [Link](https://proceedings.neurips.cc/paper_files/paper/2022/file/867c06823281e506e8059f5c13a57f75-Paper-Conference.pdf) |
| **Codebook Features: Sparse and Discrete Interpretability for Neural Networks** | ICML | 2024 | [Link](https://openreview.net/forum?id=LfhG5znxzR) |

### 3. Representational Decomposability

| Paper | Venue | Year | Link |
| :--- | :---: | :---: | :---: |
| **Backpack Language Models** | ACL | 2023 | [Link](https://aclanthology.org/2023.acl-long.506.pdf) |
| **Character-level Chinese Backpack Language Models** | BlackboxNLP | 2023 | [Link](https://aclanthology.org/2023.blackboxnlp-1.8/) |
| **LLM Pretraining with Continuous Concepts (CoCoMix)** | ArXiv | 2025 | [Link](https://openreview.net/forum?id=wTGcb3DxOn) |

### 4. Explicit Modularization (MoEs)

#### Intra-Expert Sparsity

| Paper | Venue | Year | Link |
| :--- | :---: | :---: | :---: |
| **Mixture of Experts Made Intrinsically Interpretable (MoE-X)** | ICML | 2025 | [Link](https://openreview.net/forum?id=6QERrXMLP2) |
| **Pushing Mixture of Experts to the Limit (MoV)** | ICLR | 2024 | [Link](https://arxiv.org/abs/2309.05444) |
| **Pushing Mixture of Experts to the Limit (MoLORA)** | ICLR | 2024 | [Link](https://arxiv.org/abs/2309.05444) |

#### Fine-Grained Decomposition

| Paper | Venue | Year | Link |
| :--- | :---: | :---: | :---: |
| **MONET: Mixture of Monosemantic Experts for Transformers** | ICLR | 2025 | [Link](https://arxiv.org/abs/2412.04139) |
| **Towards Interpretability Without Sacrifice (MxD)** | ArXiv | 2025 | [Link](https://arxiv.org/abs/2505.21364) |
| **Parameter-Efficient Mixture-of-Experts Architecture (MPO-MoE)** | COLING | 2022 | [Link](https://aclanthology.org/2022.coling-1.288/) |

#### Semantically Aligned Routing

| Paper | Venue | Year | Link |
| :--- | :---: | :---: | :---: |
| **Task-Based MoE for Multitask Multilingual Machine Translation** | ArXiv | 2023 | [Link](https://aclanthology.org/2023.mrl-1.13/) |
| **Sparse MoE with Language Guided Routing (Lingual-SMoE)** | ICLR | 2024 | [Link](https://openreview.net/forum?id=ySS7hH1smL) |
| **THOR-MoE: Hierarchical Task-Guided and Context-Responsive Routing** | ACL | 2025 | [Link](https://aclanthology.org/2025.acl-long.1040.pdf) |
| **Apollo-MoE: Large-Scale Communication-Efficient Training** | ArXiv | 2025 | [Link](https://arxiv.org/abs/2505.11432) |
| **Routing Manifold Alignment Improves Generalization (RoMA)** | ArXiv | 2025 | [Link](https://arxiv.org/abs/2511.07419) |
| **Unified Sparse Mixture of Experts (USMoE)** | ArXiv | 2025 | [Link](https://arxiv.org/html/2503.22996v2) |
| **Advancing Expert Specialization for Better MoE (Orthogonality)** | ArXiv | 2025 | [Link](https://arxiv.org/abs/2505.22323) |

### 5. Latent Sparsity Induction

| Paper | Venue | Year | Link |
| :--- | :---: | :---: | :---: |
| **Weight-Sparse Transformers Have Interpretable Circuits** | ArXiv | 2025 | [Link](https://arxiv.org/abs/2511.13653) |
| **Language Modeling with Gated Convolutional Networks (GLUs)** | ICML | 2017 | [Link](https://arxiv.org/abs/1612.08083) |

## 🌟 Reference

Please cite our paper if you find this survey useful for your research.

```bibtex
@misc{gao2026intrinsicinterpretabilitylargelanguage,
      title={Towards Intrinsic Interpretability of Large Language Models:A Survey of Design Principles and Architectures}, 
      author={Yutong Gao and Qinglin Meng and Yuan Zhou and Liangming Pan},
      year={2026},
      eprint={2604.16042},
      archivePrefix={arXiv},
      primaryClass={cs.CL},
      url={https://arxiv.org/abs/2604.16042}, 
}
