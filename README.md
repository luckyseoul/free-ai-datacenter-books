# Free High-Quality Books & Guides on AI Deployment, Data Centers, Rack Design & Optimal Layouts

Curated collection of free / open-access high-quality resources. Primary focus remains physical AI infrastructure (data centers, racks, liquid cooling, power, NVLink/Aquila, Chinese AIDC materials). Expanded software section for building AI from scratch.

## Core Full Books (Physical + Systems)
- The Data Center as a Computer 4th Ed (Barroso et al., Google) – https://datacenter-book.org/
- Energy Efficient Servers (Gough et al., Intel) – Springer OA
- Machine Learning Systems (mlsysbook.ai, Harvard)

## Energy / Layout / Rack / Interconnect
- LBNL/FEMP Best Practices Guide for Energy-Efficient Data Center Design (2024)
- Schneider WP 144: Establishing a Floor Plan
- OCP Open Rack V3 + Brazos / Mount Diablo liquid cooling
- NVIDIA GB200/GB300 NVL72 OCP contributions + reference architectures
- NVIDIA NVLink + 800 VDC blogs
- Google Aquila (NSDI’22) + Jupiter papers

## Chinese Free Resources
- CAICT 智算中心液冷产业全景研究报告（2025） + 冷板式液冷报告（2024）
- Huawei AI DC / AIDC 机房参考设计白皮书
- T/CECS 1903-2025 智能计算中心设计标准

## Building AI / LLMs from Scratch (Software)
High-quality free educational resources for implementing models, training pipelines, and systems from first principles:

- **Sebastian Raschka – Build a Large Language Model (From Scratch)**  
  Official free code repo: https://github.com/rasbt/LLMs-from-scratch (99k+ stars)  
  Step-by-step PyTorch implementation of a GPT-style LLM (data, embeddings, attention, pretraining, finetuning, instruction tuning). Companion to the book; free video course also available. Gold standard for understanding LLM internals.

- **Andrej Karpathy – Neural Networks: Zero to Hero**  
  Free YouTube series + code: https://karpathy.ai/zero-to-hero.html  
  Builds from scalar autograd (micrograd) → makemore → full GPT. Companion repos: nanoGPT (https://github.com/karpathy/nanoGPT), build-nanogpt. The most influential free “from scratch” curriculum.

- **Train LLM From Scratch** (user-added)  
  https://github.com/FareedKhan-dev/train-llm-from-scratch  
  Pure PyTorch Transformer + The Pile pipeline + full post-training (SFT → Reward Model → PPO/DPO/GRPO). Single-GPU friendly (13M–2B+).

- **The Annotated Transformer** (Harvard NLP)  
  Classic line-by-line annotated implementation of the original “Attention is All You Need” paper. Free online.

- **Neural Networks from Scratch** (Harrison Kinsley / Sentdex)  
  Builds neural nets in pure Python/NumPy with no frameworks. Free videos + accompanying materials at nnfs.io.

- Additional strong free materials: Hugging Face free NLP course, modern-llm-notebook collections, and various pure-PyTorch workshop repos (e.g. rasbt/LLM-workshop-2024).

These complement the physical infrastructure collection by covering how the models that run in those racks are actually built and trained.

Repo continuously updated. Chinese full translations in progress.

Last updated: July 2026
